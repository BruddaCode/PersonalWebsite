<script setup>
import headshot from '../media/home/headshot.jpg'
import hr from '../media/home/HR.png'
import tcr from '../media/home/TCR.webp'
import scs from '../media/home/SCS.webp'
import html from '../media/home/HTML.png'
import css from '../media/home/CSS.png'
import javascript from '../media/home/JS.svg'
import php from '../media/home/php.svg'
import mysql from '../media/home/MySQL.png'
import python from '../media/home/Python.svg'
import java from '../media/home/Java.svg'
import cpp from '../media/home/CPlusPlus.svg'
import csharp from '../media/home/CSharp.svg'
import go from '../media/home/Go.svg'
import haskell from '../media/home/Haskell.svg'
import git from '../media/home/Git.svg'
import linux from '../media/home/Linux.svg'
import usa from '../media/home/USA.svg'
import nl from '../media/home/NL.svg'
</script>

<template>
    <br>
    <div class="home-content">
        <div class="intro-item">
            <div class="intro-text">   
                <h3>Technische Informatica Student | Zoekt naar stage</h3>
                <h2>Introductie</h2>
                <p>Ik ben Fabio en woon in Pernis-Rotterdam. Als hobby houd ik mij bezig met elektronica, computers en mechanica. Ik ben altijd zeer nieuwsgierig hoe alles werkt en met elkaar samenwerkt, welke techniek ergens achter schuil gaat, hoe het aangestuurd wordt en of het ook anders kan. Daarom heb ik gekozen voor de opleiding Technische Informatica aan de Hogeschool Rotterdam
                    Ik vind het leuk om nieuwe dingen te leren en nieuwe uitdagingen aan te gaan, proberen of iets juist wel kan.
                    Ik werk graag in teamverband en help mensen als ze vast lopen en ik hun daarbij kan ondersteunen om te zoeken naar een oplossing. Ik kan mij goed uitdrukken what mij en mijn omgeving helpt als ik iets moet uitleggen of overbrengen maar ook bij discussies waar ik al snel de rol pak van bemiddelaar om de rust te bewaren.
                </p>
            </div>
            <img :src="headshot" alt="Home Image">
        </div>

        <div class="skills-item">
            <h2>Vaardigheden</h2>
            <div class="skill-icons">
                <div><img :src="html" alt="Skill Image"><p>HTML</p></div>
                <div><img :src="css" alt="Skill Image"><p>CSS</p></div>
                <div><img :src="javascript" alt="Skill Image"><p>JavaScript</p></div>
                <div><img :src="php" alt="Skill Image"><p>PHP</p></div>
                <div><img :src="mysql" alt="Skill Image"><p>MySQL</p></div>
                <div><img :src="python" alt="Skill Image"><p>Python</p></div>
                <div><img :src="java" alt="Skill Image"><p>Java</p></div>
                <div><img :src="cpp" alt="Skill Image"><p>C++</p></div>
                <div><img :src="csharp" alt="Skill Image"><p>C#</p></div>
                <div><img :src="go" alt="Skill Image"><p>Go</p></div>
                <div><img :src="haskell" alt="Skill Image"><p>Haskell</p></div>
                <div><img :src="git" alt="Skill Image"><p>Git</p></div>
                <div><img :src="linux" alt="Skill Image"><p>Linux</p></div>
            </div>
        </div>

        <div class="schools-item">
            <h2>Opleidingen</h2>
            <div class="school-icons">
                <div><img :src="hr" alt="School Image"><p>HBO Technische Informatica</p></div>
                <div><img :src="tcr" alt="School Image"><p>MBO4 Software Development</p></div>
                <div><img :src="scs" alt="School Image"><p>VMBO TL Techniek</p></div>
            </div>
        </div>

        <div class="languages-item">
            <h2>Talen</h2>
            <div class="language-icons">
                <div><img :src="nl" alt="Language Image"><p>Nederlands</p></div>
                <div><img :src="usa" alt="Language Image"><p>Engels</p></div>
            </div>
        </div>
        
    </div>
</template>