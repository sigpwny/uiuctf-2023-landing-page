<svelte:head>
    <title>UIUCTF 2023</title>
    <meta name="description" content="Experience the next era of CTFing">
    <meta property="og:site_name" content="UIUCTF 2023">
    <meta property="og:title" content="Information">
    <meta property="og:description" content="Experience the next era of CTFing">
    <meta property="og:type" content="website">
    <meta property="twitter:card" content="summary">
    <meta property="twitter:site" content="@sigpwny">
    <meta property="twitter:image" content="https://raw.githubusercontent.com/sigpwny/uiuctf-2023-landing-page/main/static/images/UIUCTF-2023-Pwny-Sky-512px.png">
    <meta property="twitter:title" content="Information">
    <meta property="twitter:description" content="Experience the next era of CTFing">
    <meta name="robots" content="index, follow">
    <meta name="theme-color" content="#000000">
</svelte:head>
<script>
    import { draggable } from '@neodrag/svelte'
    import Person from '../lib/components/Person.svelte'
    let time = new Date().toLocaleTimeString('en-US', { 
        hour: "numeric", 
        minute: "numeric"
    });

    $: selected = "about"
</script>
<style>
    a:hover, .text-action {
        color: #800080;
    }
    a, .text-action {
        text-decoration: underline;
    }
    .info-panel {
        background: #feffd1;
        max-height: 300px;
        overflow: auto;
    }
    .close-icon {
        cursor: pointer;
        padding: 2px 6px 4px 5px;
    }

</style>
<div class="min-vh-100 d-flex flex-column">
    <main class="d-flex flex-grow-1 w-100">
        <!-- Home screen -->
        <section class="d-flex bg-secondary w-100">
            <div class="d-flex flex-column mt-3 ml-3 position-fixed">
                <div class="d-flex flex-column">
                    <img src="images/windows-95-my-computer.png" width="32" height="32" alt="">
                    <span class="font-xsmall text-neutral mt-2 mb-4">My Computer</span>
                </div>
                <div class="d-flex flex-column">
                    <img src="images/windows-95-network-neighborhood.png" width="32" height="32" alt="">
                    <span class="font-xsmall text-neutral mt-2 mb-4">Network <br> Neighborhood</span>
                </div>
                <div class="d-flex flex-column">
                    <img src="images/windows-95-inbox.png" width="32" height="32" alt="">
                    <span class="font-xsmall text-neutral mt-2 mb-4">Inbox</span>
                </div>
                <div class="d-flex flex-column">
                    <img src="images/windows-95-recycle-bin.png" width="32" height="32" alt="">
                    <span class="font-xsmall text-neutral mt-2 mb-4">Recycle Bin</span>
                </div>
                <div class="d-flex flex-column">
                    <img src="images/windows-95-msn.png" width="32" height="32" alt="">
                    <span class="font-xsmall text-neutral mt-2 mb-4">Set up the <br> SIGPwny <br> Network</span>
                </div>
            </div>
            <div class="d-flex container align-self-center justify-content-center">
                <div class="col-12 col-md-6 col-lg-8 mb-4 mb-lg-0">
                    <div class="card card-tertiary" use:draggable >
                        <div class="card-header d-flex flex-row justify-content-between align-items-center">
                            <span>Welcome</span>
                            <span class="close-icon btn btn-primary">
                                <img src="images/windows-95-close-icon.png" alt="">
                            </span>
                        </div>
                        <div class="card-body">
                            <h5>Welcome to <b>UIUCTF 2023</b></h5>
                            <div class="d-flex mt-3 flex-column">
                                <div class="d-flex flex-row">
                                    
                                    <div class="info-panel d-flex flex-column p-3 w-100">
                                        {#if selected == "about"}
                                            <div class="d-flex flex-row align-items-center">
                                                <img src="images/windows-95-tip.png" alt="">
                                                <p class="font-weight-bold ml-2 mt-2">Did you know...</p>
                                            </div>
                                            <p>
                                                You can use the buttons on the right to learn more about UIUCTF! You can also head right to the <a href="https://2023.uiuc.tf/">CTFd</a>.
                                            </p>
                                            <p><a href="https://discord.gg/9x2DBQXf96" target="_blank" rel="noopener noreferrer">Join the Discord server!</a></p>
                                        {:else if selected == "when"}
                                            <p>
                                            UIUCTF 2023 will be held Sat, 01 July 2023, 00:00 UTC — Mon, 03 July 2023, 00:00 UTC.
                                            </p>
                                        {:else if selected == "prizes"}
                                            <p>
                                                Prizes TBD.
                                            </p>
                                        {:else if selected == "sponsors"}
                                            <p>
                                                SIGPwny thanks its UIUCTF 2023 sponsors:
                                            </p>
                                            <div class="row">
                                                <div class="">
                                                    <img src="images/battelle-blue.png" class="img-fluid" alt="">
                                                </div>
                                                <div class="col-8 mb-2">
                                                    <img src="images/trail-of-bits.png" class="img-fluid" alt="">
                                                </div>
                                                <div class="col-8">
                                                    <a href="https://davidan.dev"><img src="https://davidan.dev/logo.png" class="img-fluid" alt=""></a>
                                                </div>
                                                <div class="col-8 mb-2">
                                                    <img src="images/google-cloud.png" class="img-fluid" alt="">
                                                    <p>Infra sponsored by <a href="https://goo.gle/ctfsponsorship" target="_blank" rel="noopener noreferrer">goo.gle/ctfsponsorship</a></p>
                                                </div>
                                            </div>
                                        {:else if selected == "team"}
                                            <div class="d-flex flex-column">
                                                <p>Meet the UIUCTF 2023 Team</p>
                                                <div class="row">
                                                    <Person name="Pete Stenger" img="https://avatars.githubusercontent.com/u/13869303" href="https://github.com/reteps" />
                                                    <Person name="Richard Liu" img="https://avatars.githubusercontent.com/u/9328196" href="https://github.com/richyliu" />
                                                    <Person name="Hassam Uddin" img="https://avatars.githubusercontent.com/u/13320947" href="https://hassamuddin.com" />
                                                    <Person name="YiFei Zhu" img="https://lh3.googleusercontent.com/a-/ACB-R5SiFvHe6qP5yi3wJVNMUQqolSc-SRIl_ncQvhC_" href="https://github.com/zhuyifei1999" />
                                                    <Person name="kuilin" img="https://kuilin.net/profile_upscaled.png" href="https://kuilin.net/" />
                                                    <Person name="David An" img="https://davidan.dev/dave.jpeg" href="https://davidan.dev" />
                                                    <Person name="Ellie Popoca" img="https://i.imgur.com/jVsQDUP.gif" href="https://www.linkedin.com/in/elliepopoca" />
                                                    <Person name="Pomona Carrington-Hoekstra" img="https://avatars.githubusercontent.com/u/86129353" />
                                                    <Person name="George Huebner" img="https://avatars.githubusercontent.com/u/44840644" href="https://github.com/Feyorsh" />
                                                    <Person name="Joseph Ravichandran" img="https://i.imgur.com/XOk7y7X.jpg" href="https://twitter.com/0xjprx" />
                                                    <Person name="Minh Duong" img="https://avatars.githubusercontent.com/u/35712968" href="https://whitehoodhacker.net/" />
                                                    <Person name="Anakin Dey" img="https://avatars.githubusercontent.com/spamakin" href="https://www.anakin-dey.com/" />
                                                    <Person name="Nitya Sunkad" img="https://avatars.githubusercontent.com/u/52294194?v=4" href="https://www.linkedin.com/in/nsunkad" />
                                                    <Person name="Anusha Ghosh" img="https://avatars.githubusercontent.com/u/35054976" />
                                                </div>
                                            </div>
                                        {/if}
                                            
                                    </div>
                                <div class="d-flex flex-column pl-2">
                                    <button class={`btn btn-sm mb-1 btn-primary ${selected == 'about' ? 'border-dark' : ''}`} type="button" on:click={() => {selected = 'about'}}><span
                                        class="btn-text">About</span></button>
                                    <button class={`btn btn-sm mb-1 btn-primary ${selected == 'when' ? 'border-dark' : ''}`} type="button" on:click={() => {selected = 'when'}}><span
                                        class="btn-text">When</span></button>
                                        <button class={`btn btn-sm mb-1 btn-primary ${selected == 'prizes' ? 'border-dark' : ''}`} type="button" on:click={() => {selected = 'prizes'}}><span
                                            class="btn-text">Prizes</span></button>
                                    <button class={`btn btn-sm mb-1 btn-primary ${selected == 'sponsors' ? 'border-dark' : ''}`} type="button" on:click={() => {selected = 'sponsors'}}><span
                                        class="btn-text">Sponsors</span></button>
                                        <button class={`btn btn-sm mb-1 btn-primary ${selected == 'team' ? 'border-dark' : ''}`} type="button" on:click={() => {selected = 'team'}}><span
                                            class="btn-text">Team</span></button>
                                        </div>
                                    </div>
                                <div class="d-flex flex-row mt-2">
                                    <div class="form-check">
                                    <label class="form-check-label">
                                        <input class="form-check-input" type="checkbox">
                                        <span class="form-check-x"></span>
                                        <span class="form-check-sign"></span>
                                        <span class="font-xsmall">
                                            Show this Welcome Screen next time you start Windows
                                        </span>
                                    </label>
                                </div>
                            </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>
    <footer class="d-flex">
        <nav id="navbar-footer" class="navbar navbar-main navbar-expand-lg navbar-dark justify-content-between navbar-footer">
            <ul class="navbar-nav navbar-nav-hover">
                <li class="nav-item">
                    <div class="nav-link">
                        <img src="/images/windows-95-start.png" alt="" style="opacity: 100% !important; padding-bottom: 2px;">
                    </div>
                </li>
            </ul>
            <div class="time text-center">
                <img src="/images/windows-95-speaker.png" alt="">
                {time}
            </div>
        </nav>
    </footer>
</div>
