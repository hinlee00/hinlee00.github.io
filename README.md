# hinlee00.github.io
week1
html>
<html class="">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Home</title>

    <script src="https://cdn.tailwindcss.com"></script>
    <script src="/Components/tailwind.config.js"></script>
    <link rel="stylesheet" href="/Components/tailwindstyles.css" />

    <!-- FONTS -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap"
      rel="stylesheet"
    />
    <script src="https://unpkg.com/ionicons@4.5.10-0/dist/ionicons.js"></script>
  </head>

  <body>
    <header class="bg-gray-700/50 absolute z-10 w-full">
      <nav class="flex items-center w-[92%] w-full mx-auto">
        <div
          class="w-64 transition-all duration-150 hover:translate-y-2 hover:border hover:rounded-md cursor-pointer"
        >
        <a href="index.html"><img src="/Assets/theme/jungle/logo.png" alt="" class="logo" /></a>
        </div>
        <div
          class="nav-links duration-500 md:static absolute md:min-h-fit min-h-[30vh] left-0 top-[-700%] md:bg-transparent md:w-auto w-full flex items-center px-5 ml-auto"
        >
          <ul
            class="grid grid-rows-2 grid-flow-col md:flex mx-auto md:space-y-0 gap-6 py-10"
          >
            <li>
              <div 
                class="button w-40 h-16 bg-skin-fill cursor-pointer select-none hover:translate-y-2 hover:[box-shadow:0_0px_0_0_var(--color)] hover:border-b-[0px] transition-all duration-150 [box-shadow:0_10px_0_0_var(--color)] rounded-full border-[1px] border-green-400"
              >
                <span
                  class="flex flex-col justify-center items-center h-full text-skin-base font-bold text-lg"
                  ><button onclick="document.location='index.html'">Home</button></span
                >
              </div>
            </li>
            <li>
              <div
                class="button w-40 h-16 bg-skin-fill cursor-pointer select-none hover:translate-y-2 hover:[box-shadow:0_0px_0_0_var(--color)] hover:border-b-[0px] transition-all duration-150 [box-shadow:0_10px_0_0_var(--color)] rounded-full border-[1px] border-green-400"
              >
                <span
                  class="flex flex-col justify-center items-center h-full text-skin-base font-bold text-lg"
                  ><button onclick="document.location='video.html'">Video</button></span
                >
              </div>
            </li>
            <li>
              <div
                class="button w-40 h-16 bg-skin-fill cursor-pointer select-none hover:translate-y-2 hover:[box-shadow:0_0px_0_0_var(--color)] hover:border-b-[0px] transition-all duration-150 [box-shadow:0_10px_0_0_var(--color)] rounded-full border-[1px] border-green-400"
              >
                <span
                  class="flex flex-col justify-center items-center h-full text-skin-base font-bold text-lg"
                  ><button onclick="document.location='game.html'">Game</button></span
                >
              </div>
            </li>
            <li>
              <div
                class="button w-40 h-16 bg-skin-fill cursor-pointer select-none hover:translate-y-2 hover:[box-shadow:0_0px_0_0_var(--color)] hover:border-b-[0px] transition-all duration-150 [box-shadow:0_10px_0_0_var(--color)] rounded-full border-[1px] border-green-400"
              >
                <span
                  class="flex flex-col justify-center items-center h-full text-skin-base font-bold text-lg"
                  ><button onclick="document.location='about.html'">About Us</button></span
                >
              </div>
            </li>
          </ul>
        </div>

        <div class="flex items-end gap-6 md:hidden ml-auto">
          <ion-icon
            onclick="onToggleMenu(this)"
            name="menu"
            class="text-3xl cursor-pointer"
          ></ion-icon>
        </div>
      </nav>
    </header>

    <div class="w-full h-screen relative">
      <div
        class="background bg-[url('/Assets/theme/jungle/bg_image.jpg')] w-full h-full bg-cover bg-right"
      >
        <!-- <img class="w-full h-full object-cover" src="Assets/bg_image.jpg" /> -->
      
        <div
          class="absolute top-0 w-full md:w-96 h-full flex flex-col justify-center md:pl-10 xs:gap-y-1 md:gap-y-1"
        >
          <p
            class="mx-auto md:mx-0 font-bold text-4xl md:text-[100px] text-white"
          >
            WELCOME
          </p>
          <p
            class="mx-auto mx-0 font-bold text-4xl text-[100px] text-white opacity-75 collapse md:visible"
          >
            WELCOME
          </p>
          <p
            class="mx-auto md:mx-0 font-bold text-4xl md:text-[100px] text-white opacity-50 collapse md:visible"
          >
            WELCOME
          </p>
          <p
            class="mx-auto md:mx-0 font-bold text-4xl md:text-[100px] text-white opacity-25 collapse md:visible"
          >
            WELCOME
          </p>
          <div class="center">
          <video width="1080" height="1920" controls
          src="/Assets/Intro.mp4">
          </video>
          </div>
        </div>
      </div>
    </div>

    <form>
      <label for="theme-select">Select a theme:</label>
      <select id="theme-select">
        <option value="theme-jungle">Jungle</option>
        <option value="theme-snow">Snow</option>
        <option value="theme-desert">Desert</option>
      </select>
    </form>

    <script>
      const navLinks = document.querySelector(".nav-links");
      function onToggleMenu(e) {
        e.name = e.name === "menu" ? "close" : "menu";
        navLinks.classList.toggle("top-[9%]");
      }

      var selectElement = document.querySelector("#theme-select");
      var htmlElement = document.querySelector("html");
      var logoElement = document.querySelector(".logo");
      var bgElement = document.querySelector(".background"); // add this line to select the background element

      // Check local storage for saved theme
      var savedTheme = localStorage.getItem("theme");
      if (savedTheme) {
        htmlElement.className = savedTheme;
        if (htmlElement.classList.contains("theme-snow")) {
          logoElement.src = "/Assets/theme/snow/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/snow/bg_image.jpg')";
        } else if (htmlElement.classList.contains("theme-jungle")) {
          logoElement.src = "/Assets/theme/jungle/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/jungle/bg_image.jpg')";
        } else if (htmlElement.classList.contains("theme-desert")) {
          logoElement.src = "/Assets/theme/desert/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/desert/bg_image.jpg')";
        }
        selectElement.value = savedTheme;
      }

      selectElement.addEventListener("change", function () {
        htmlElement.className = selectElement.value;
        if (htmlElement.classList.contains("theme-snow")) {
          logoElement.src = "/Assets/theme/snow/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/snow/bg_image.jpg')";
        } else if (htmlElement.classList.contains("theme-jungle")) {
          logoElement.src = "/Assets/theme/jungle/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/jungle/bg_image.jpg')";
        } else if (htmlElement.classList.contains("theme-desert")) {
          logoElement.src = "/Assets/theme/desert/logo.png";
          bgElement.style.backgroundImage =
            "url('/Assets/theme/desert/bg_image.jpg')";
        }
        localStorage.setItem("theme", selectElement.value);
      });
    </script>
  </body>
</html>
