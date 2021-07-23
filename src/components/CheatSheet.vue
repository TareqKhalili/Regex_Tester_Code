<template>
  <button id="viewSheet" @click="sheetHidden = !sheetHidden">
    {{ sheetHidden ? "Show" : "Hidden" }} Cheat Sheet
  </button>
  <div :class="['sheet', sheetHidden && 'hidden']">
    <table>
      <tr>
        <td>/abc/</td>
        <td>A sequence of characters</td>
      </tr>
      <tr>
        <td>/[abc]/</td>
        <td>Any character from a set of characters</td>
      </tr>
      <tr>
        <td>/[^abc]/</td>
        <td>Any character not in a set of characters</td>
      </tr>
      <tr>
        <td>/[0-9]/</td>
        <td>Any character in a range of characters</td>
      </tr>
      <tr>
        <td>/x+/</td>
        <td>One or more occurrences of the pattern x</td>
      </tr>
      <tr>
        <td>/x+?/</td>
        <td>One or more occurrences, nongreedy</td>
      </tr>
      <tr>
        <td>/x*/</td>
        <td>Zero or more occurrences</td>
      </tr>
      <tr>
        <td>/x?/</td>
        <td>Zero or one occurrence</td>
      </tr>
      <tr>
        <td>/x{2,4}/</td>
        <td>Two to four occurrences</td>
      </tr>
    </table>
    <table>
      <tr>
        <td>/(abc)/</td>
        <td>A group</td>
      </tr>
      <tr>
        <td>/a|b|c/</td>
        <td>Any one of several patterns</td>
      </tr>
      <tr>
        <td>/\d/</td>
        <td>Any digit character</td>
      </tr>
      <tr>
        <td>/\w/</td>
        <td>An alphanumeric character (“word character”)</td>
      </tr>
      <tr>
        <td>/\s/</td>
        <td>Any whitespace character</td>
      </tr>
      <tr>
        <td>/./</td>
        <td>Any character except newlines</td>
      </tr>
      <tr>
        <td>/\b/</td>
        <td>A word boundary</td>
      </tr>
      <tr>
        <td>/^/</td>
        <td>Start of input</td>
      </tr>
      <tr>
        <td>/$/</td>
        <td>End of input</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sheetHidden: true,
    }
  },
}
</script>

<style></style>
