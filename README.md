## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/azinneera/build-dashboard.github.io/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/azinneera/build-dashboard.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

# Load the library
require 'google-image-charts.rb'

# Populate the chart details
chartDetails = {
	:title 	=> "Test chart",
	:height => 250,
	:width 	=> 400,
	:data	=> [[4,5,10,6,2,9], [2,2,12,9,11,1]], # Array of data arrays (one for each line)
	:labels	=> ["Series 1", "Series 2"]
}

# Create the chart
lineGraph = GoogleImageCharts::LineGraph.new(chartDetails)

# Use it!
chartUrl = lineGraph.chart_url
# => "http://chart.apis.google.com/chart?cht=lc&chs=400x250&chd=t:4,5,10,6,2,9%7C2,2,12,9,11,1&chdl=Series%201%7CSeries%202&chdlp=b&chtt=Test%20chart&chco=a&chds=a&chxt=x,y"

imageTag = lineGraph.html_img_tag
# => "<img src='http://chart.apis.google.com/chart?cht=lc&chs=400x250&chd=t:4,5,10,6,2,9%7C2,2,12,9,11,1&chdl=Series%201%7CSeries%202&chdlp=b&chtt=Test%20chart&chco=a&chds=a&chxt=x,ycht=lc&chs=400x250&chd=t:4,5,10,6,2,9%7C2,2,12,9,11,1&chdl=Series%201%7CSeries%202&chdlp=b&chtt=Test%20chart&chco=a&chds=a&chxt=x,y' alt='Test chart' height='250' width='400' />"

# Make it prettier
lineGraph.chartColors = ["5CB8E6","E68A00"]
	
