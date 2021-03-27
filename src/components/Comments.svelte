<script>
  export let comments = [];

  const addComment = (e) => {
    const mensaje = e.target.text.value;

    if (mensaje.length > 6) {
      const message = {
        id: Date.now(),
        text: mensaje,
        username: "HzCode",
      };

      comments = [...comments, message];
      e.target.text.value = "";
    }
  };
</script>

<div class="Comments">
  <div class="Comments-container">
    <div class="Comments-users">
      <div class="Comments-content">
        {#each comments as comment (comment.id)}
          <h3>{comment.username}</h3>
          <span>{comment.text}</span>
        {/each}
      </div>
    </div>
    <div class="Comments-add">
      <form on:submit|preventDefault={(e) => addComment(e)}>
        <input
          autocomplete="off"
          type="text"
          class="Comments-input"
          placeholder="Agregar Comentario..."
          id="text"
        />
        <button type="submit"> Post </button>
      </form>
    </div>
  </div>
</div>

<style>
  .Comments h3 {
    font-size: 14px;
    color: black;
    font-weight: bold;
    margin: 0;
    padding: 0;
  }
  .Comments span {
    font-size: 14px;
    margin: 0 0 0 0.5em;
    font-weight: normal;
    color: rgba(black, 0.9);
  }
  .Comments-add {
    padding: 1em 1em 1em 1em;
    border-top: 1px solid rgba(219, 219, 219, 0.8);
  }
  .Comments-add form {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Comments-content {
    padding: 0 1em 0.5em 1em;
  }
  .Comments-users {
    margin: 0 0 0.5em 0;
    display: flex;
  }

  input {
    border: solid 1px #e9e9e9;
    border-radius: 5px;
    color: #696969;
    border: 1px solid transparent;
    font-size: 12px;
    outline: none;
    width: 100%;
    display: flex;
  }
  button {
    border: none;
    color: #3897f0;
    font-size: 12px;
    outline: none;
    cursor: pointer;
  }
  /* label {
    display: none;
  } */
</style>
