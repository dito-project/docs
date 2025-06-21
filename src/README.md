<style>
#intro-logo { width: 50%; max-width: 300px; }
.star-container { display: flex; justify-content: center; padding: 1rem 0; }
.badges { 
  display: flex; 
  justify-content: center; 
  gap: 0.5rem; 
  padding: 1rem; 
  flex-wrap: wrap;
  margin: 0 1rem;
}
@media (max-width: 768px) {
  .badges {
    gap: 0.3rem;
    padding: 0.5rem;
    margin: 0 0.5rem;
  }
  .badges img {
    max-width: calc(50% - 0.15rem);
    height: auto;
  }
}
</style>

<div class="badges">
  <img src="https://img.shields.io/badge/status-active-green.svg" alt="Status">
  <img src="https://img.shields.io/badge/release-0.7.5-green.svg" alt="Release">
  <img src="https://img.shields.io/badge/license-Apache2-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/language-Go-blue.svg" alt="Language">
</div>

<div class="logo-container" align="center">
  <img id="intro-logo" src="./dito.png" alt="Dito Logo" />
</div>

**Dito** is an advanced, highly extensible **reverse proxy server** written in Go. It features a robust **plugin-based architecture**, **custom certificate handling** for backend connections, **dynamic configuration reloading**, and more. Plugins can manage their own dependencies and provide custom middleware functionality.

The official project repository is available on [GitHub](https://github.com/andrearaponi/dito).