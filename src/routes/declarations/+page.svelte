<h3>Declarations</h3>
<script>
  // these are simple reactive variables
  let reactiveNumeric = "100"
  let reactiveText = "Earth"
  let double = reactiveNumeric * 2
</script>

<!-- this text relies on reactive variables set in <script> -->
<p>Welcome to Sector {reactiveNumeric} of the planet, {reactiveText}. If you move to the next sector, you will be in Sector {double}</p>

<input type="text" bind:value={reactiveNumeric} on:blur={reactiveNumeric = value}>
<input type="text" bind:value={reactiveText} on:blur={reactiveText = value}><br /><br />

<code>
&lt;script><br />
&nbsp;&nbsp;// these are simple reactive variables<br />
  &nbsp;&nbsp;let reactiveNumeric = "100"<br />
  &nbsp;&nbsp;let reactiveText = "Earth"<br />
  &nbsp;&nbsp;let double = reactiveNumeric * 2<br />
&lt;/script><br />
</code>

<p>Notice that the variable, <code>double</code>, gives us the right value. But when we change the value of the <strong>reactiveNumeric</strong> <code>input</code> box to, say, 300, <code>double</code> is still stuck with the original value.</p>

<p>To make it work the way we want it to (doubling when <strong>reactiveNumeric</strong> is changed), we need to change the <i>assignment</i> of <code><strong>double</strong></code> to a <i>declaration</i>.</p>

<code>
  $: double = reactiveNumeric * 2
</code>

<p>We do that by prefixing the declaration with <code>$:</code>. So a variable that relies on other values (or any declaration) needs the <code>$: </code> prefix.</p>

<style>
  code {
    color: blue;
  }

</style>