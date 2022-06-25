<template>
    <div id="demoContain">
        <p class="title">a simple demo, happy 1024 Day!</p>
    </div>
</template>

<script>
import * as THREE from 'three';
import { FontLoader } from 'three/examples/jsm/loaders/FontLoader.js'
// import { TextGeometry } from './jsm/geometries/TextGeometry.js';
// import Stats from 'three/examples/jsm/libs/stats.module.js';

export default {
    data() {
        return {
        }
    },
    methods: {
        // updatePermalink() {
        //     const link = hex + fontMap[ fontName ] + weightMap[ fontWeight ] + boolToNum( bevelEnabled ) + "#" + encodeURI( text );
        //     permalink.href = "#" + link;
        //     window.location.hash = link;
        // },
        // refreshText() {
        //     updatePermalink();
        //     group.remove( textMesh1 );
        //     if ( mirror ) group.remove( textMesh2 );
        //     if ( ! text ) return;
        //     createText();
        // },
        init() {
            const scene = new THREE.Scene();
            scene.background = new THREE.Color( 0x000000 );
            scene.fog = new THREE.Fog( 0x000000, 250, 1400 );
        },
		loadFont() {
            const loader = new FontLoader();
            const font = undefined;
            const fontName = "optimer"; 
			const fontWeight = "bold";
            loader.load( '../assets/' + fontName + '_' + fontWeight + '.typeface.json', function ( response ) {

					font = response;

					// refreshText();

				} );
        }
    },
    mounted() {
        this.init();
        this.loadFont();
    }
}
</script>


<style scoped>
#demoContain {
	margin: 0;
	background-color: #8de3d5;
	color: black;
	font-family: Monospace;
	font-size: 14px;
	overscroll-behavior: none;
    width: 100vw;
    height: 100vh;
    text-align: center;
}
.title {
    width: 50%;
    margin: 0 auto;
}

</style>
