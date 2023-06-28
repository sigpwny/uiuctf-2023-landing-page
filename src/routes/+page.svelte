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
                                        <div class="d-flex flex-row align-items-center">
                                            <img src="images/windows-95-tip.png" alt="">
                                            <p class="font-weight-bold ml-2 mt-2">Did you know...</p>
                                        </div>
                                        <div>
                                            <p>
                                                UIUCTF 2023 will be held Sat, 01 July 2023, 00:00 UTC — Mon, 03 July 2023, 00:00 UTC.<br>
                                                You can learn more about UIUCTF 2023 by heading straight to the CTFd, and hitting "Info"!
                                            </p>
                                            
                                            <button class="btn btn-sm mb-1 btn-primary" type="button" on:click={() => window.location.href = 'https://2023.uiuc.tf'}>CTFd</button>
                                            <button class="btn btn-sm mb-1 btn-primary" type="button" on:click={() => window.location.href = 'https://discord.gg/9x2DBQXf96'}>Discord</button>

                                        </div>
                                    </div>
                                <div class="d-flex flex-column pl-2">
                                    <button class={`btn btn-sm mb-1 btn-primary border-dark`} type="button"><span
                                        class="btn-text">About</span>
                                    </button>
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
