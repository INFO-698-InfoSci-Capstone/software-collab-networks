# Weekly/Bi-Weekly Log

## Prompts
Following the [Rose/Bud/Thorn](https://www.panoramaed.com/blog/rose-bud-thorn-activity-and-worksheet#:~:text=%22Rose%2C%20Bud%2C%20Thorn%22%20is%20a%20mindful%20design%2D,day%2C%20week%2C%20or%20month.) model:

### Date:
Week April 14th -19th

log date 04/18/2025


### Number of hours:


- 3 h – Revisit the context file to extract all author–software pairs, making sure each DOI’s full set of software mentions is captured uniquely.
- 2 h – Clean and deduplicate the raw edgelist, verifying that multi‐software papers generate distinct edges for each tool.
- 4 h – Adapt the PLAY‐Network R script to tag each edge with its software property and generate a colored network visualizatio.
- 1 h – Run preliminary network‐science analyses—calculate degree and betweenness centralities, assess community structure, and check for assortativity by software label.
- 1 h – Document the entire workflow and code changes, and commit the cleaned edgelist and visualization scripts to our /code and /data folders on Box.



### Rose:
I’ve outlined a robust pipeline to pull every unique software mention into our author–paper edgelist—so papers that reference both TNT and MEGA (like DOI 12910) will now correctly spawn two separate software ties.

### Bud:
I’m looking forward to mapping this enriched network—coloring each collaboration tie by its software label will not only highlight tool‐specific communities but also reveal authors who bridge across multiple software ecosystems, giving us insight into interdisciplinarity and knowledge flow.

### Thorn:
Ensuring that my script handles papers with multiple software mentions without dropping or duplicating edges—and seamlessly integrating the edge‐property coloring from the PLAY visualizations code—could get tricky, so I’ll need to validate every step and debug carefully.

## Additional thought

---

