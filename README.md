<?php

/*
Plugin Name: HTML5 jQuery Audio Player
Plugin URI: http://wordpress.org/extend/plugins/html5-jquery-audio-player/
Description: The trendiest audio player plugin for WordPress. Works on iPhone/iPad and other mobile devices. Insert with shortcode [hmp_player]
Author: EnigmaWeb
Version: 2.6.2
Author URI: https://profiles.wordpress.org/enigmaweb/
Text Domain: html5-jquery-audio-player
Domain Path: /languages
*/

error_reporting(0);
ini_set('display_errors', 0);

require 'includes/db-settings.php';
register_activation_hook( __FILE__, 'hmp_db_create' );

add_action( 'admin_menu', 'my_plugin_menu' );
function my_plugin_menu() {
    add_menu_page( 'HTML5 MP3 Player', 'HTML5 Player', 'manage_options', 'hmp-options', 'wp_hmp_options',plugin_dir_url( __FILE__ )."/music-beam.png" );
    add_submenu_page('hmp-options','','','manage_options','hmp-options','wp_hmp_options');
    add_submenu_page('hmp-options','Display Settings','Display Settings','manage_options','display_settings','wp_hmp_options');
    add_submenu_page( 'hmp-options', 'Manage Songs', 'Manage Songs', 'manage_options', 'hmp_palylist', 'wp_hmp_playlist' );	
}

function hmp_scripts_method() {
    $query = $_SERVER['PHP_SELF'];
    wp_enqueue_script('jquery');
    
    wp_deregister_script( 'hmp-custom-js' );
    wp_register_script( 'hmp-custom-js', plugin_dir_url( __FILE__ )."player/js/hmp-custom.js");
    wp_enqueue_script('media-upload');
    wp_enqueue_script('thickbox');
    
    if(strpos($query,'admin.php')!==false){
	wp_enqueue_script( 'hmp-custom-js' );
    }
    wp_enqueue_style('thickbox');
}
add_action('admin_enqueue_scripts', 'hmp_scripts_method');

add_action( 'admin_init', 'register_mysettings' );
function register_mysettings() {
    register_setting( 'baw-settings-group', 'buy_text' );
    register_setting( 'baw-settings-group', 'color' );
    register_setting( 'baw-settings-group', 'showlist' );
    register_setting( 'baw-settings-group', 'showbuy' );
    register_setting( 'baw-settings-group', 'hmp_description' );
    register_setting( 'baw-settings-group', 'currency' );
    register_setting( 'baw-settings-group', 'tracks' );
    register_setting( 'baw-settings-group', 'tcolor' );
    register_setting( 'baw-settings-group', 'autoplay' );	
}

function wp_hmp_options() {
    include 'player/settings.php';
}
