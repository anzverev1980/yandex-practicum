<div class="markdown markdown_size_normal markdown_type_theory"><h1>Technological Process</h1><h5>How is gold extracted from ore? Let's look into the process stages.</h5><div class="paragraph">Mined ore undergoes primary processing to get the ore mixture or rougher feed, which is the raw material for flotation (also known as the rougher process). After flotation, the material is sent to two-stage purification.</div><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/viruchka_2_1589899167.jpg">
<div class="paragraph">Let's break down the process:</div><div class="paragraph"><strong>1. Flotation</strong></div><div class="paragraph">Gold ore mixture is fed into the float banks to obtain rougher Au concentrate and rougher tails (product residues with a low concentration of valuable metals).</div><div class="paragraph">The stability of this process is affected by the volatile and non-optimal physicochemical state of the flotation pulp (a mixture of solid particles and liquid).</div><div class="paragraph"><strong>2. Purification</strong></div><div class="paragraph">The rougher concentrate undergoes two stages of purification. After purification, we have the final concentrate and new tails.</div><h2>Data description</h2><div class="paragraph"><strong>Technological process</strong></div><ul><li><em>Rougher feed</em> — raw material</li><li><em>Rougher additions</em> (or <em>reagent additions</em>) — flotation reagents: <em>Xanthate, Sulphate, Depressant</em>
  <ul><li><em>Xanthate</em> — promoter or flotation activator;</li><li><em>Sulphate</em> — sodium sulphide for this particular process;</li><li><em>Depressant</em> — sodium silicate.</li></ul></li><li><em>Rougher process</em>  — flotation</li><li><em>Rougher tails</em> — product residues</li><li><em>Float banks</em> — flotation unit</li><li><em>Cleaner process</em> — purification</li><li><em>Rougher Au</em> — rougher gold concentrate</li><li><em>Final Au</em> — final gold concentrate</li></ul><div class="paragraph"><strong>Parameters of stages</strong></div><ul><li><em>air amount — volume of air</em></li><li><em>fluid levels</em></li><li><em>feed size</em> — feed particle size</li><li><em>feed rate</em></li></ul><h2>Feature naming</h2><div class="paragraph">Here's how you name the features:</div><div class="paragraph"><code class="code-inline code-inline_theme_light">[stage].[parameter_type].[parameter_name]</code></div><div class="paragraph">Example: <code class="code-inline code-inline_theme_light">rougher.input.feed_ag</code></div><div class="paragraph">Possible values for <code class="code-inline code-inline_theme_light">[stage]</code>:</div><ul><li><em>rougher —</em> flotation</li><li><em>primary_cleaner</em> — primary purification</li><li><em>secondary_cleaner</em> — secondary purification</li><li><em>final</em> — final characteristics</li></ul><div class="paragraph">Possible values for <code class="code-inline code-inline_theme_light">[parameter_type]</code>:</div><ul><li><em>input</em> — raw material parameters</li><li><em>output</em> — product parameters</li><li><em>state</em> — parameters characterizing the current state of the stage</li><li><em>calculation —</em> calculation characteristics</li></ul><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/ore_1591699963.jpg">
<h2>Recovery calculation</h2><div class="paragraph">You need to simulate the process of recovering gold from gold ore.</div><div class="paragraph">Use the following formula to simulate the recovery process:</div><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/Recovery_1576238822_1589899219.jpg">
<div class="paragraph">where:</div><ul><li><em>C</em> — share of gold in the concentrate right after flotation (for finding the rougher concentrate recovery)/after purification (for finding the final concentrate recovery)</li><li><em>F</em> — share of gold in the feed before flotation (for finding the rougher concentrate recovery)/in the concentrate right after flotation (for finding the final concentrate recovery)</li><li><em>T</em> — share of gold in the rougher tails right after flotation (for finding the rougher concentrate recovery)/after purification (for finding the final concentrate recovery)</li></ul><div class="paragraph">To predict the coefficient, you need to find the share of gold in the concentrate and the tails. Note that both final and rougher concentrates matter.</div><h2>Evaluation metric</h2><div class="paragraph">To solve the problem, we will need a new metric. It is called <strong>sMAPE,</strong> symmetric Mean Absolute Percentage Error. </div><div class="paragraph">It is similar to MAE, but is expressed in relative values instead of absolute ones. Why is it symmetrical? It equally takes into account the scale of both the target and the prediction.</div><div class="paragraph">Here’s how <em>sMAPE</em> is calculated:</div><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/smape_1576238825_1589899257.jpg">
<div class="paragraph">Denotation:</div><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/y1_1576238832_1589899414.jpg">
<ul><li>Value of target for the observation with the <em>i</em> index in the sample used to measure quality.</li></ul><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/yi_1_1576238835_1589899461.jpg">
<ul><li>Value of prediction for the observation with the <em>i</em> index, for example, in the test sample.</li></ul><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/N_1_1576238819_1589899496.jpg">
<ul><li>Number of observations in the sample.</li></ul><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/I_1576238817_1589899530.jpg">
<ul><li>Summation over all observations of the sample (<em><strong>i</strong></em> takes values from 1 to <em>N</em>).</li></ul><div class="paragraph">We need to predict two values:</div><ol start="1"><li>rougher concentrate recovery <code class="code-inline code-inline_theme_light">rougher.output.recovery</code></li><li>final concentrate recovery <code class="code-inline code-inline_theme_light">final.output.recovery</code></li></ol><div class="paragraph">The final metric includes the two values:</div><img alt="image" class="image image_expandable" src="https://pictures.s3.yandex.net/resources/_smape_1589899561.jpg">
</div>