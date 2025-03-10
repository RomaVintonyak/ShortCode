//Пагинация для кастомных типов записей
<?php
$paged = (get_query_var('paged')) ? get_query_var('paged') : 1;
$args = array(
	'posts_per_page' => 6,
	'order' 	 => 'DESC',
	'post_type' 	 => 'MY_POST_TYPE',
	'paged'	         => $paged
);

$MY_QUERY = new WP_Query( $args );

if ( $MY_QUERY->have_posts() ) :
	while ( $MY_QUERY->have_posts() ) : $MY_QUERY->the_post(); ?>
							
	<?php endwhile;
endif; ?>
					
<!-- Pagination -->
<div class="page_nav">
	<?php
	$GLOBALS['wp_query']->max_num_pages = $MY_QUERY->max_num_pages;
	the_posts_pagination(array(
		'type'=>'inline',
		'screen_reader_text' => __( '' ),
		'end_size'     => 1,
		'mid_size'     => 1,
		'prev_next'    => True,
		'prev_text'    => __('<i class="fa fa-angle-left"></i>'),
		'next_text'    => __('<i class="fa fa-angle-right"></i>'),
		'add_args'     => False
	));
	?>
</div>
<?php  wp_reset_postdata(); ?>
<!-- End Pagination -->
