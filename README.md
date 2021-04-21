##### AUTHOR: ELIDIAN, MORGANA,  VALDELICE

# DISCIPLINA DE COMPUTAÇÃO GRÁFICA
### TRABALHO DE INTERPOLAÇÃO DE CORES
##### KEYWORDS: INTERPOLAÇÃO, LERP, RGB, HSL, HTML, JAVASCRIPT, CSS


### function LERP RGB
```
/**
*   Interpolation two RGB color
*   @param {Array} colorRGB - array of color RGB[red, green, blue]
*   @param {Array} colorRGB - array of color RGB[red, green, blue]
*   @param {number} factor - factor of interpalation
*   @return {Array} colorRGB - array of color RGB[red, green, blue]
*/
function lerp(color1, color2, factor){
    let r = parseInt(color1[0] + (color2[0]-color1[0])*factor);
    let g = parseInt(color1[1] + (color2[1]-color1[1])*factor);
    let b = parseInt(color1[2] + (color2[2]-color1[2])*factor);
    
    return rgb = [r, g, b];
}
```
### function LERP HSL
```
/**
*   Interpolation two HSL color
*   @param {Array} colorHSL - array of color HSL[hue, saturation, ligthless]
*   @param {Array} colorHSL - array of color HSL[hue, saturation, ligthless]
*   @param {number} factor - factor of interpalation
*   @return {Array} colorHSL - array of color HSL[hue, saturation, ligthless]
*/
function lerp(color1, color2, factor){
    let h = parseInt(color1[0] + (color2[0]-color1[0])*factor);
    let s = parseInt(color1[1] + (color2[1]-color1[1])*factor);
    let l = parseInt(color1[2] + (color2[2]-color1[2])*factor);
    
    return hsl = [h, s, l];
}
```
### function HSL to RGB
```
/**
*   Convert HSL color to RGB color
*   @param {Array} colorHSL - array of color HSL[hue, saturation, ligthless]
*   @return {Array} colorRGB - array of color RGB[red, green, blue]
*/
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
### function RGB to #HEX
```
/**
*   Convert RGB color to HEXADECIMAL color in string formact
*   @param {Array} colorRGB - array of color RGB[red, green, blue]
*   @return {string} colorHEX - return color hexadecimal '#'+hex+hex+hex
*/
function rgbToHex (rgb) {   
    let red = intToHex(rgb[0]);
    let green = intToHex(rgb[1]);
    let blue = intToHex(rgb[2]);
    
    return '#'+red+green+blue;
}
```
### function DEC to HEX
```
/**
*   Convert decimal number to hexadecimal number
*   @param {number} number
*   @return {hexadecimal} hex
*/
function intToHex (number) { 
    let hex = Number(number).toString(16);
    if (hex.length < 2) {
        hex = "0" + hex;
    }
    return hex;
}
```

END
