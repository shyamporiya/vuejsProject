<template>
  <div>
    <nav class="navbar navbar-expand-lg unique_clr">
      <div class="container-fluid nav_font">
        <a class="navbar-brand nav_font_add" href="#">Vuejs</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNavDropdown"
          aria-controls="navbarNavDropdown"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a
                class="nav-link active nav_font_add"
                aria-current="page"
                href="#"
                >Home</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link nav_font_add" href="#">Features</a>
            </li>
            <li class="nav-item">
              <a class="nav-link nav_font_add" href="#">Pricing</a>
            </li>
            <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle nav_font_add"
                href="#"
                id="navbarDropdownMenuLink"
                role="button"
                data-bs-toggle="dropdown"
                aria-expanded="false"
              >
                Dropdown link
              </a>
              <ul
                class="dropdown-menu"
                aria-labelledby="navbarDropdownMenuLink"
              >
                <li>
                  <a class="dropdown-item nav_font_add" href="#">Action</a>
                </li>
                <li>
                  <a class="dropdown-item nav_font_add" href="#"
                    >Another action</a
                  >
                </li>
                <li>
                  <a class="dropdown-item nav_font_add" href="#"
                    >Something else here</a
                  >
                </li>
              </ul>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script></script>
<style scoped>
.unique_clr {
  background: linear-gradient(45deg, #5f2626, transparent);
}
.nav_font_add {
  color: antiquewhite !important;
  /* text-decoration: underline; */
  font-weight: 400;
  font-family: fangsong;
}
</style>
