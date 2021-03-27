<script>
  import { likeCount } from "../store/store";
</script>

<div class="Header">
  <div class="Header-container">
    <div class="Header-content">
      <div class="Header-logo">
        <img
          src="https://www.instagram.com/static/images/web/mobile_nav_type_logo.png/735145cfe0a4.png"
          alt=""
        />
      </div>
      <div class="Header-nav">
        <ul>
          <li>
            <i class="fas fa-heart" />
            {$likeCount}
          </li>
          <li>
            <i class="fas fa-user-alt" />
          </li>
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
  .Header {
    background-color: white;
    position: fixed;
    width: 100%;
  }
  .Header-container {
    grid-template-columns: minmax(auto, 936px);
    display: grid;
    justify-content: center;
    background-color: white;
    border-bottom: 1px solid rgba(38, 38, 38, 0.4);
  }
  .Header-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.5em;
  }
  .Header ul {
    list-style: none;
  }
  .Header li {
    display: inline-block;
    margin: 0 0 0 1em;
  }
  .Header i {
    font-size: 16px;
    color: rgba(38, 38, 38, 0.7);
    cursor: pointer;
  }
</style>
