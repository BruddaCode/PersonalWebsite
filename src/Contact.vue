<template>
    <br>
    <div class="contact-content">

        <div class="contact-form">
            <h2>Intresse? Stuur mij een bericht, en dan reageer ik zo snel mogelijk!</h2>

            <form @submit.prevent="onSubmit" novalidate>
                <label for="name">Name</label>
                <input id="name" v-model="name" type="text" placeholder="Your name" required>

                <label for="email">Email</label>
                <input id="email" v-model="email" type="email" placeholder="Your email" required>

                <label for="message">Message</label>
                <textarea
                    id="message"
                    v-model="message"
                    rows="6"
                    placeholder="Write your message..."
                    required
                ></textarea>

                <div style="margin-top:.75rem">
                    <button type="submit" :disabled="sending">{{ sending ? 'Sending…' : 'Send Message' }}</button>
                    <span v-if="status" :class="statusClass" style="margin-left:1rem">{{ status }}</span>
                </div>
            </form>
        </div>

        <div class="contact-info">
            <h2>Contact Information</h2>

            <div class="info-card">
                <img src="/media/contact/github.png" alt="GitHub">
                <a href="https://github.com/BruddaCode" target="_blank">github.com/BruddaCode</a>
            </div>

            <div class="info-card">
                <img src="/media/contact/linkedin.svg" alt="LinkedIn">
                <a href="https://www.linkedin.com/in/fabio-wolthuis-a16878243" target="_blank">linkedin.com/in/fabio-wolthuis</a>
            </div>
        </div>

    </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// EmailJS config — set these with your EmailJS values
// e.g. SERVICE_ID = 'service_xxx', TEMPLATE_ID = 'template_xxx', PUBLIC_KEY = 'user_xxx'
const EMAILJS_SERVICE_ID = 'service_iu9qo95'
const EMAILJS_TEMPLATE_ID = 'template_w06vn1j'
const EMAILJS_PUBLIC_KEY = 'UQHcFajtYdp9QlVpu'

import { send } from '@emailjs/browser'

const name = ref('')
const email = ref('')
const message = ref('')
const sending = ref(false)
const status = ref('')

const statusClass = computed(() => status.value.includes('error') ? 'error' : 'success')

function validate() {
    if (!name.value.trim()) return 'Please enter your name.'
    if (!email.value.trim()) return 'Please enter your email.'
    // basic email check
    if (!/^[^@\s]+@[^@\s]+\.[^@\s]+$/.test(email.value)) return 'Please enter a valid email.'
    if (!message.value.trim()) return 'Please enter a message.'
    return ''
}

async function onSubmit() {
    status.value = ''
    const err = validate()
    if (err) { status.value = err; return }

    sending.value = true
        try {
            if (EMAILJS_SERVICE_ID && EMAILJS_TEMPLATE_ID && EMAILJS_PUBLIC_KEY) {
                // send via EmailJS
                const templateParams = {
                    // include both sets of keys so the EmailJS template variables match
                    name: name.value,
                    email: email.value,
                    from_name: name.value,
                    from_email: email.value,
                    message: message.value
                }
                await send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID, templateParams, EMAILJS_PUBLIC_KEY)
                status.value = 'Message sent — bedankt!'
                name.value = email.value = message.value = ''
            } else {
                // fallback: open mail client with prefilled values
                const subject = encodeURIComponent(`Contact via website from ${name.value}`)
                const body = encodeURIComponent(`Name: ${name.value}\nEmail: ${email.value}\n\n${message.value}`)
                window.location.href = `mailto:?subject=${subject}&body=${body}`
                status.value = 'Opening your mail client…'
            }
    } catch (e) {
        status.value = 'Error sending message — probeer het later opnieuw (error)'
        console.error(e)
    } finally {
        sending.value = false
    }
}
</script>

<style scoped>
.success { color: #8EE7A7 }
.error { color: #FFB4A2 }
</style>