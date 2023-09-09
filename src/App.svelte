<script lang="ts">
  import { marked } from "marked";

  const h1Text = "# This is an H1";
  const h2Text = "## This is an H2";
  const linkText = "[A link](https://en.wikipedia.org)";
  const codeText = "```\nThis is some code\nSome code\n ```";
  const inlineCode = "this is some `inline code`";
  const listText = "- a list\n- of \n- items";
  const quoteText = "> a blockquote\n";
  const boldText = "**BOLD TEXT**\n";
  const imageText =
    "![an image](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b6/Image_created_with_a_mobile_phone.png/640px-Image_created_with_a_mobile_phone.png)";

  let value = `${h1Text}\n${h2Text}\n${linkText}\n${codeText}\n${inlineCode}\n${listText}\n${quoteText}\n${boldText}\n${imageText}`;
</script>

<div class="grid">
  input
  <textarea id="editor" bind:value />

  ouput
  <div id="preview">{@html marked(value)}</div>
</div>

<style>
  .grid {
    display: grid;
    grid-template-columns: 5em 1fr;
    grid-template-rows: 1fr 1fr;
    grid-gap: 1em;
    height: 100%;
  }

  textarea {
    flex: 1;
    resize: none;
  }
</style>
