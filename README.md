##### AUTHOR: ELIDIAN, MORGANA,  VALDELICE

# DISCIPLINA DE COMPUTAÇÃO GRÁFICA
## TRABALHO DE INTERPOLAÇÃO DE CORES
### RGB E HSL


### function LERP RGB
```
/*
    @param colorRGB = [red, green, blue]
    @param colorRGB = [red, green, blue]
    @param number

    @return colorRGB = [red, green, blue]
*/
```
```
function lerp(color1, color2, factor){
    var r = parseInt(color1[0] + (color2[0]-color1[0])*factor);
    var g = parseInt(color1[1] + (color2[1]-color1[1])*factor);
    var b = parseInt(color1[2] + (color2[2]-color1[2])*factor);
    
    return rgb = [r, g, b];
}
```
### function LERP HSL
/*
    @param colorHSL = [hue, saturation, ligthless]
    @param colorHSL = [hue, saturation, ligthless]
    @param number
    
    @return colorHSL = [hue, saturation, ligthless]
*/
```
function lerp(color1, color2, factor){
    let h = parseInt(color1[0] + (color2[0]-color1[0])*factor);
    let s = parseInt(color1[1] + (color2[1]-color1[1])*factor);
    let l = parseInt(color1[2] + (color2[2]-color1[2])*factor);
    console.log('h: '+h)
    console.log('s: '+s)
    console.log('l: '+l)
    return hsl = [h, s, l];
}
```
### function HSL to RGB
/*
    @param colorHSL = [hue, saturation, ligthless]
    @return colorRGB = [red, green, blue]
*/
```
function hslToRgb(hsl){
    // Must be fractions of 1
    let h = hsl[0];
    let s = hsl[1];
    let l = hsl[2];
    s /= 100;
    l /= 100;

    let c = (1 - Math.abs(2 * l - 1)) * s,
        x = c * (1 - Math.abs((h / 60) % 2 - 1)),
        m = l - c/2,
        r = 0,
        g = 0,
        b = 0;
    
    if (0 <= h && h < 60) {
        r = c; g = x; b = 0;  
    } else if (60 <= h && h < 120) {
        r = x; g = c; b = 0;
    } else if (120 <= h && h < 180) {
        r = 0; g = c; b = x;
    } else if (180 <= h && h < 240) {
        r = 0; g = x; b = c;
    } else if (240 <= h && h < 300) {
        r = x; g = 0; b = c;
    } else if (300 <= h && h < 360) {
        r = c; g = 0; b = x;
    }
    r = Math.round((r + m) * 255);
    g = Math.round((g + m) * 255);
    b = Math.round((b + m) * 255);

    return rgb = [r, g, b];
}
```
### function RGB to HSL
/*
    @param colorRGB = [red, green, blue]
    return stringColorHEX = '#'+hex+hex+hex
*/
```
function rgbToHex (rgb) {   
    var red = intToHex(rgb[0]);
    var green = intToHex(rgb[1]);
    var blue = intToHex(rgb[2]);
    return '#'+red+green+blue;
}
```
### function DEC to HEX
/*
    @param number
    @return numberHEX = hex
*/
```
function intToHex (number) { 
    var hex = Number(number).toString(16);
    if (hex.length < 2) {
        hex = "0" + hex;
    }
    return hex;
}
```

END
