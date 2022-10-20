# Custom related posts in individual blog post area

This code displays the Specific blog post ID based Related Post using shortcode in WordPress Post.

You need to edit three files:
1.	function.php
2.  Individual Blog Post 
2.	Style.css

<h3>1. function.php code:</h3>

You need to add the following function code to the function.php file in the directory of your wordpress theme.


```html
add_shortcode('custom_related_post', 'custom_single_post');

function custom_single_post($atts) {
	$a = shortcode_atts(
        array(
            'id' => '',
        ), $atts );
	$out = '';
	$post_id = $a['id'];
	$post = get_post( $post_id );
	add_image_size( 'custom-thumbnail-size', 120, 120, array('center', 'center') );
  if(has_post_thumbnail($post_id)) {
    $out .='
    <a class="custom-thumbnail" title="'.get_the_title($post_id).'" href="'.get_permalink($post_id).'">
    '. get_the_post_thumbnail($post_id, array(120,120)).' 
    <span class="custom-thumbnail-title">'.get_the_title($post_id).'</span>
    </a>';
  }
  else {
    $out .='
    <a class="custom-thumbnail" title="'.get_the_title($post_id).'" href="'.get_permalink($post_id).'">
      <img src="https ://letstalksex.net/wp-content/uploads/2020/11/strawberry-creamy-120x120.jpg" /> /* placeholder image*/
      <span class="custom-thumbnail-title">'.get_the_title($post_id).'</span>
    </a>';
  }
return $out;
}
```

The above function helps to get to the required post's ID and output the post thumbnail, title, pharmalink, 

<h3>2.  individual Blog Post: </h3>

You need to open a blog post and add the code to the very last of the blog post content area.

```html
<div class="custom-related">
  <h3 class="custom-title">You May Also Like</h3>
  <div class="custom-thumbnails-horizontal">
    [custom_related_post id="10"]
    [custom_related_post id="11"]
    [custom_related_post id="12"]
    [custom_related_post id="13"]
   </div>
</div>
```

[You need to open an indivisual blog post in the admin panel dashboard > post area and get the post id from the URL]
[You can display customized related posts in indivisual blog posts]


<h3>3.	Style.css</h3>

If you are having issue with the styling then you can copy & paste the style follwoing codes to style.css or any linked CSS files.

```html
/* Custom realted post shortcode Style */
.custom-related {
    margin: 1em 0;
}
.custom-related a{
    text-decoration: none;
}
.custom-related .custom-thumbnail-title{
    text-align: left;
    font-size: 96%;
    text-decoration: none;
}
.custom-related .custom-title{
    font-weight: bold;
    padding: 0 0 5px 0;
    font-size: 125%;
    text-transform: capitalize;
    margin: 0;
}
.custom-thumbnails-horizontal .custom-thumbnail, .custom-thumbnail-default, .custom-thumbnail-title {
	display: inline-block;
}
.custom-thumbnails-horizontal .custom-thumbnail {
	border: 1px solid #7F7F7F;
	border-color: rgba(127,127,127,0.1);
	width: 130px;
	height: 100%;
	margin: 5px;
	margin-left: 0;
	vertical-align: top;
}
.custom-thumbnail img, .custom-thumbnail-default {
	width: 120px;
	height: 120px;
	margin: 5px;
}
.custom-thumbnails-horizontal .custom-thumbnail img, .custom-thumbnails-horizontal .custom-thumbnail-default {
	display: block;
}
.custom-thumbnails-horizontal .custom-thumbnail-title {
	display: inline-table;
	font-size: 1em;
	max-height: 2.8em;
	line-height: 1.4em;
	margin: 7px;
	margin-top: 0;
	width: 120px;
	text-decoration: inherit;
	overflow: hidden;
}
.custom-thumbnail-default {
	overflow: hidden;
}
.custom-thumbnail-default img {
	min-height: 120px;
	min-width: 120px;
}
```

The Final Output:


If you still face any issues to use the codes, feel free to contact me at: me.sifat@live.com Or, Directly hire me at: Upwork / Fiverr

Happy Coding!
