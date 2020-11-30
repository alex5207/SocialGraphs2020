# The Hollywood Project

## Introduction

## Network Evolution

## Actor Community

## Talk of the town

## Wrap-up

### Data
1. Link to notebook
2. Link to Kaggle Data


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

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/alex5207/SocialGraphs2020/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

<div id="text"></div>
 
<script>
document.getElementById("text").innerHTML = "Text added by JavaScript code";
</script>

<script>
     var w = 500;
    var h = 200;

    data1 = [50, 60, 70, 30, 20, 10];
    data2 = [30, 80, 20, 40];
    dataIndex = 1;
    
    var colors = d3.scale.category10();

    //Create SVG element
    var svg = d3.select("#draw_here")
            .append("svg")
            .attr("width", w)
            .attr("height", h);

    svg.selectAll("circle")
            .data(data1)
            .enter()
            .append("circle")
            .attr("cx", function (d, i) {
                return 75 + (i * 80);
            })
            .attr("cy", h / 2)
            .attr("r", function (d, i) {
                return d;
            })
            .attr("fill", function(d, i) {
                return colors(i);
            })
            .attr("opacity", "0.5");

    d3.select("#buttons_here").append("button")
            .text("change data")
            .on("click",function(){
                if (dataIndex==1) {
                    dataIndex=2;  
                } else   {
                    dataIndex=1;
                }
                var circle = svg.selectAll("circle")
                    .data(eval("data"+dataIndex));

                circle.exit().remove();//remove unneeded circles
                    circle.enter().append("circle")
                        .attr("r",0);//create any new circles needed

                circle.transition()
                        .duration(500)
                        .attr("cx", function (d, i) {
                            return 75 + (i * 80);
                        })
                        .attr("cy", h / 2)
                        .attr("r", function (d, i) {
                            return d;
                        })
                        .attr("fill", function(d, i) {
                            return colors(i);
                        });

            });//end click function
</script>

<div class="roulette" style="display:none;"> 
	<img src="http://example.com/star.png"/>
	<img src="http://example.com/flower.png"/>
	<img src="http://example.com/coin.png"/>
	<img src="http://example.com/mshroom.png"/>
	<img src="http://example.com/chomp.png"/>
</div> 
