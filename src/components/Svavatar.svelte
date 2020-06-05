<script>
	import Avatars from '@dicebear/avatars';
	import maleSprites from '@dicebear/avatars-male-sprites';
	import femaleSprites from '@dicebear/avatars-female-sprites';
	import botttsSprites from '@dicebear/avatars-bottts-sprites';
	import gridySprites from '@dicebear/avatars-gridy-sprites';
	import humanSprites from '@dicebear/avatars-human-sprites';
	import identiconSprites from '@dicebear/avatars-identicon-sprites';
	import initialsSprites from '@dicebear/avatars-initials-sprites';
	import jdenticonSprites from '@dicebear/avatars-jdenticon-sprites';
	
	//Globals
	export let seed = "svelte-tako-components";
	export let type = "human";
	export let radius = 0;
	export let width = null;
	export let height = null;
	export let margin = 0;
	export let background = null;

	//Human, Female, Male
	export let mood = null;

	//Identicon
	export let colorLevel = 600;

	//Initials
	export let backgroundColors	= [];
	export let backgroundColorLevel = 600;
	export let fontSize = 50;
	export let chars = 2;
	export let bold = false;

	//Bottts
	export let primaryColorLevel = 600;
	export let secondaryColorLevel = 400;
	export let mouthChance = 100;
	export let sidesChance = 100;
    export let textureChance = 50;
    export let topChance = 100;

	//JDenticon
	export let hues = null;
	export let colorLightness = null;
	export let grayscaleLightness = null;
	export let colorSaturation = null;
	export let grayscaleSaturation = null;

	//Gridy
	export let deterministic = false;

	//Identicon, Bottts
	export let colors = null;
	//Bottts, Avataaards
	
	//Botts, Gridy
	export let colorful = false;

	let initialsOptions = {backgroundColors:backgroundColors,backgroundColorLevel:backgroundColorLevel,fontSize:fontSize,chars:chars,bold:bold};
	let botttsOptions = {primaryColorLevel:primaryColorLevel,secondaryColorLevel:secondaryColorLevel,colorful:colorful,mouthChance:mouthChance,sidesChance:sidesChance,textureChance:textureChance,topChance:topChance};
	let jdenticonOptions = {hues:hues,colorLightness:colorLightness,grayscaleLightness:grayscaleLightness,colorSaturation:colorSaturation,grayscaleSaturation:grayscaleSaturation};
	let gridyOptions = {colorful:colorful,deterministic:deterministic};
	function getPackageForSprite(spriteName){
		switch (spriteName) {
			case "male":
				return maleSprites;
			case "female":
				return femaleSprites;
			case "human":
				return humanSprites;
			case "bottts":
				return botttsSprites;
			case "gridy":
				return gridySprites;
			case "identicon":
				return identiconSprites;
			case "initials":
				return initialsSprites;
			case "jdenticon":
				return jdenticonSprites;
			default:
				break;
		}
	}

	let options = {radius:radius,width:width,height:height,margin:margin,background:background};
	((type==="male" || type==="female" || type==="human") && mood!==null) ? options.mood = mood : null;
	((type==="identicon" || type==="bottts") && colors!==null) ? options.colors = colors : null;
	(type==="identicon") ? options.colorLevel = colorLevel : null;
	(type==="initials") ? options = {...options,...initialsOptions} : null;
	(type==="bottts") ? options = {...options,...botttsOptions} : null;
	(type==="jdenticon") ? options={...options,...jdenticonOptions} : null;
	(type==="gridy") ? options = {...options,...gridyOptions} : null;

    console.log(options);

	let avatars = new Avatars(getPackageForSprite(type), options);
	let svg = avatars.create(seed);

</script>

{@html svg}