<h1> Why I Fixed My HTML: Lessons from a Personal Portfolio Accessibility Audit</h1>
We have all built web layouts that look visually spectacular on a modern desktop browser. But have you ever stopped to wonder how your website "sounds" to someone using an audio screen reader, or how it operates for someone navigating entirely via a keyboard?

As part of my frontend engineering milestones this week, I ran a comprehensive accessibility audit on my personal portfolio using Chrome Lighthouse and the WAVE Web Accessibility Tool. The raw results were an eye-opener, pushing me to re-evaluate how I write markup—shifting away from purely visual layout tricks to prioritizing semantic code structures.

Understanding Semantic HTML
Semantic HTML means using structural tags that inherently describe their meaning to both the browser, assistive technologies, and fellow developers. A generic <div> wrapper tells us absolutely nothing about its context. Conversely, tags like <main>, <nav>, <article>, and <fieldset> instantly flag exactly what role their inner elements play.

Writing clean, semantic components creates a rock-solid foundation for digital inclusion, cleaner search engine optimization (SEO), and painless long-term code maintenance.

Before and After: The Contact Form Layout
During my initial audit, my form elements were scattered inside generic structural containers without logical boundaries, and input elements lacked accessible connections to their descriptive text labels.

The Non-Semantic Way (Before)
HTML
<div class="form-group">
  <span class="label-text">Email Address</span>
  <input type="text" name="email" placeholder="Enter email">
</div>
The Semantic and Accessible Way (After)
HTML
<fieldset>
  <legend>Contact Information</legend>
  <p>
    <label for="email">Email Address *</label>
    <input type="email" id="email" name="email" placeholder="alex.dev@example.com" required>
  </p>
</fieldset>
<h1>Key Accessibility Fixes Applied</h1>
 - Explicit Input Labels: I linked every <label> with its companion input using matching for and id tag properties so screen readers announce the label text when       the field receives focus.

 - Context-Rich Hyperlinks: I removed ambiguous, detached link strings like "click here" and replaced them with descriptive indicators like "Explore my web             applications on the Projects Showcase page."

- Rigid Heading Hierarchies: I repaired broken layout loops (such as jumping directly from an <h1> title down to an <h4> sub-heading for visual sizing scale),         ensuring that structural screen reader outlines read sequentially (<h1> → <h2>).


<h1> Project Links</h1>
  - Live Repository: <a href="iyf-s11-week-01-nahashonmutahi95 "</a>

  - GitHub Profile: @nahashonmutahi95
