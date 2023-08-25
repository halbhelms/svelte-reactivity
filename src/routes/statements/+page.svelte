<h3>Statements</h3>
<script>
  // these are simple reactive variables
  let reactiveNumeric = "100"
  let reactiveText = "Earth"
  $: double = reactiveNumeric * 2
  $: console.log(double)
</script>

<!-- this text relies on reactive variables set in <script> -->
<p>Welcome to Sector {reactiveNumeric} of the planet, {reactiveText}. If you move to the next sector, you will be in Sector {double}</p>

<input type="text" bind:value={reactiveNumeric} on:blur={reactiveNumeric = value}>
<input type="text" bind:value={reactiveText} on:blur={reactiveText = value}>

<p>Look at the code in our script tag for this example:</p>

<code>
&lt;script><br />
  &nbsp; &nbsp;// these are simple reactive variables<br />
  &nbsp; &nbsp;let reactiveNumeric = "100"<br />
  &nbsp; &nbsp;let reactiveText = "Earth"<br />
  &nbsp; &nbsp;$: double = reactiveNumeric * 2<br />
  &nbsp; &nbsp;console.log(double)<br />
&lt;/script>
</code>

<p>If you run this code, <code>double</code> has a value of <code>undefined</code>.</p>

<p>In the context of dereferencing <code>double</code> in the HTML (within curly braces), <code>double</code> is understood, but when we write a <i>statement</i> (such as <code>console.log(double)</code>), it is <i>not</i> understood.</p>

<p>Luckily, we can <i>declare</i> a statement:</p>
<code>$: console.log(double)</code>
<p>and the code now works fine.</p>
<p></p>
<p>You can even put the <code>$:</code> in front of things like if blocks:</p>
<code>
  $: if (reactiveNumber > 1000) &#123<br />
	&nbsp; &nbsp;alert('The largest sector is 1000')<br />
	&nbsp; &nbsp;reactiveNumber = 100<br />
}
</code>

<style>
  code {
    color: blue;
  }
</style>