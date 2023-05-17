<script lang="ts">
    import Accordion from "./lib/Accordion.svelte";
    import AccordionItem from "./lib/AccordionItem.svelte";

    import lh_img from "./assets/lighthouse.png";
    import lh_canny_img from "./assets/lh_canny.png";
    import passpls_sample from "./assets/passpls_sample.png";
    import wpm_sample from "./assets/wpm_sample.gif";
    import fs_sample from "./assets/fs_sample.mp4";
    import stoneng_sample from "./assets/stoneng_sample.mp4";
    import gocook_sample from "./assets/GoCook_sample.mp4";

    let stonEngOpened = false;
    let goCookOpened = false;
    let fsOpened = false;
    $: goCookOpened, stonEngOpened, fsOpened;

</script>

<main>
<div class="flex sm:justify-center my-[15vh]">
  <div class="max-w-2xl w-full">
    <div class="text-3xl flex flex-col">
      <span class="">Jayden Dumouchel</span>
      <div>
        <a class="bg-base-content grow-0 text-base-300 hover:text-primary-content hover:bg-primary"
           href="https://github.com/RottenFishbone">
          //RottenFishbone
        </a>
      </div>
    </div>

    <Accordion class="my-5">
      <AccordionItem title="About Me">
        <div class="break-words">
          <p class="indent-4">
          I'm a software developer who enjoys the challenge of making things 
          from scratch just to learn new things along the way.
          </p>
          <br>
          <p class="indent-4">
          I gravitate towards low level programming in C and Rust 
          but I believe its important to be familiar with as many paradigms and
          styles as possible. The diversity of my projects is a pursuit in that
          endeavour. Even if it usually isn't practical to re-invent the wheel,
          it never fails to teach me something new.
          </p>
        </div>
      </AccordionItem>
      <AccordionItem title="Projects">
        <Accordion>
          <AccordionItem bind:opened={stonEngOpened} title="StonEng" subtitle="2D Game Engine">
            <a class="link link-primary" href="https://github.com/RottenFishbone/StonEng">StonEng</a> is a custom and general 2D game
            engine written in Rust, completely from scratch (minus the ECS which I felt was 
            out of scope).<br>
            <br>
            In its current state, it features text rendering, sprite rendering with
            a custom animation system/markup, an original/custom-built dithered lighting
            system, camera and movement controllers and a limited sound system.
            {#if stonEngOpened}
              <video class="w-full mt-5" controls>
              <track kind="captions"/>
              <source src={stoneng_sample} type="video/mp4"/>
            </video>
            {/if} 
          </AccordionItem>
          
          <AccordionItem bind:opened={goCookOpened} title="GoCook" subtitle="Recipe Manager">
            <div class="break-words">
              <a class="link link-primary" href="https://github.com/RottenFishbone/go-cook">GoCook</a> 
              is a 
              <a class="link link-primary" href="https://cooklang.org/">Cooklang</a> 
              Parser/API server written in Go, paired with a webapp written in 
              Svelte, hosted by the Go server.<br><br>
              It seeks to provide a slim but full featured personal recipe manager
              offering searching, rendering, editing and directory management all from
              a mobile-friendly web interface. In addition to a CLI parser/viewer<br><br>
              The parser is implemented as a parser-combinator and exported for use
              as a canonical cooklang parser package.
            </div>
            {#if goCookOpened}
              <video class="w-full mt-5" controls>
                <track kind="captions"/>
                <source src={gocook_sample} type="video/mp4"/>
              </video>
            {/if}
          </AccordionItem>
          
          <AccordionItem bind:opened={fsOpened} title="Cascadia" subtitle="Sand Simulation">
            <div class="break-words">
              <a class="link link-primary" href="https://github.com/RottenFishbone/game-of-sand">Cascadia</a> 
              is a completely custom-built, high-performance falling sand 
              simulation written in C, using raw OpenGL for rendering
              and GLFW for windowing.<br>
              <br>
              I've spent an obscene amount of time creating algorithms to handle
              falling "sand" in a robust way that simulates particle density and buoyancy
              in a system that simulates each pixel based on its properties. While
              I unfortunately hard-paused this project due to a lack of time (full-time
              university while working ~20-hours/week) I am extremely proud of my
              progress and believe this concept has incredible potential.
            </div>
            {#if fsOpened}
              <video class="w-full mt-5" controls>
                <track kind="captions"/>
                <source src={fs_sample} type="video/mp4"/>
              </video>
            {/if}
          </AccordionItem>
          
          <AccordionItem title="QRQuest" subtitle="Android App">
           <div class="break-words">
             <a class="link link-primary" href="https://github.com/CMPUT301W22T35/QRcode-Quest">
             QRCode-Quest</a> is a university
             project and a collaboration <span class="italic">primarily</span> with
             <a class="link link-primary" href="https://github.com/KarlHanEdn">Tianming Han</a>. 
             It is an Android App written in Java that gamifies finding arbitrary QR codes. <br>
             <br>
             My role in the project was the styling, UI implementation and data linking. 
             Tianming primarily handled the data layer abstraction and database interaction.<br>
             <br>
             While I don't consider this project a point of personal pride (it was a university project)
             it was certainly an exercise in teamwork, as well as a demonstration of App and Java
             knowledge.<br>
             <br>
             <a class="link link-primary" 
                href="https://www.youtube.com/watch?v=Tvy3v0vWhqk&feature=youtu.be">
                The Demo is available on Youtube
             </a>
            </div>
          </AccordionItem>
          
          <AccordionItem title="edgedetect" subtitle="Img Processing">
            <div class="break-words">
              <a class="link link-primary" href="https://github.com/RottenFishbone/edgedetect">
                edgedetect</a> is a tiny image processing tool written from scratch in C. 
              It provides various image detection methods, including the popular Canny method.<br>
                <br>
                I processed the image as 1D byte arrays, applying convolution 2D kernels by using
                Moore neighbourhood offsets. Edge detection methods include basic filters/operators 
                such as Sobel, Scharr, Roberts Cross. As well as complex methods such as Laplacian
                of Gaussian and Canny.<br>
                <br>
                Many techniques used in this edge detector are fairly mathematically complex or use
                poorly documented techniques such as edge thinning through threshold-hysteresis. I
                believe this project serves as an execellent reference for how these are performed at 
                low level, due to its simplicity in design.<br>
                <br>
                Below is an example of its output (Canny).
            </div>
            <div class="flex mt-5">
              <img src={lh_img} class="w-full" alt="Original"/>
              <img src={lh_canny_img} class="w-full" alt="Edge detected"/>
            </div>
         </AccordionItem>

          <AccordionItem title="passpls" subtitle="Passphrase gen">
            <div class="break-words">
              <a class="link link-primary" href="https://github.com/RottenFishbone/passpls">
                passpls</a> is an extremely lightweight passphrase generator, based off of the 
              popular 
              <a class="link link-primary" href="https://xkcd.com/936/">XKCD comic</a>, 
              written in Rust.<br>
              <br>
              It aims to be a <a class="link link-primary" href="https://suckless.org/">suckless</a>
              -style passphrase generator, providing cryptographically
              secure passphrases in a CLI following the Unix "do one thing well" philosophy.
              While designed for Linux, I aimed to provide a platform agnostic experience to CLI.<br>
              <br>
              It's motivation for existence was to avoid using heavy (and possibly online) password
              managers to simply generate a passphrase, as I believe that an option should be available
              that is immediately readable as to how your password was made AND displayed.
            </div>
            <img src={passpls_sample} class="w-full mt-5" alt="program sample"/>
         </AccordionItem>
          
          <AccordionItem title="wpm" subtitle="Typing Speed Test">
            <div class="break-words">
             <a class="link link-primary" href="https://github.com/RottenFishbone/wpm">
               wpm</a> 
             is terminal user interface (TUI)-based typing speed evaluator
             written in Rust. This was my first complete project written in a TUI.<br>
              <br>
             It uses an open source dictionary generator (SCOWL) to provide a 
             list of common english words, loosely filtered by regex to exclude
             certain punctuations. 
             <br>
             The final score is displayed based on a commonly used formula of a
             word being defined as a number of characters per time unit elapsed,
             presented as 'wpm'.
            </div>      
            <img src={wpm_sample} class="w-full mt-5" alt="sample video"/>
          </AccordionItem>
        </Accordion>
      </AccordionItem>
    </Accordion>
  </div>
</div>

<footer class="footer footer-center">
  <div class="text-xs">
    Copyright 2023 Jayden Dumouchel<br>
    <a class="link" href="https://github.com/RottenFishbone/fishbone">Source Code</a>
  </div>
</footer>
</main>

