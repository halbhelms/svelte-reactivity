<h3>Assignments</h3>
<script>
  // these are simple reactive variables
  let reactiveNumeric = "100"
  let reactiveText = "Earth"
</script>

<!-- this text relies on reactive variables set in <script> -->
<p>Welcome to Sector {reactiveNumeric} of the planet, {reactiveText}</p>

<input type="text" bind:value={reactiveNumeric} on:blur={reactiveNumeric = value}>
<input type="text" bind:value={reactiveText} on:blur={reactiveText = value}>

<p>Accomplished with simple <code>let</code> statement</p>

<code>
&lt;script><br />
&nbsp; &nbsp;// these are simple reactive variables<br />
&nbsp; &nbsp;let <strong>reactiveNumeric</strong> = "100"<br />
&nbsp; &nbsp;let <strong>reactiveText</strong> = "Earth"<br />
&lt;/script><br /><br />
</code>

<code>
&lt;!-- this text relies on reactive variables set in &lt;script> --><br />
&lt;p>Welcome to Sector &#123<strong>reactiveNumeric</strong>} of the planet, &#123<strong>reactiveText</strong>}&lt;/p>
<br /><br />
&lt;!-- this text relies on reactive variables set in &lt;script> --><br />
&lt;input type="text" bind:value=&#123<strong>reactiveNumeric</strong>} on:blur=&#123<strong>reactiveNumeric</strong> = value}><br />
&lt;input type="text" bind:value=&#123<strong>reactiveText</strong>} on:blur=&#123<strong>reactiveText</strong> = value}>
</code>
<br />
<p>Entering values into <code>input</code> text box changes the (reactive) values set in <code>script</code> tag.<p>
  
<p>Since we <code>bind:value</code> the <code>input</code> boxes, when the reactive values change, so does the text that relies on them.</p>

<style>
  code {
    color: blue;
  }

</style>