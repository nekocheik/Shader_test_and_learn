# Shader_test_and_learn

**exemple: 1**

    #ifdef GL_ES
    precision mediump float;
    #endif
    
    uniform float u_time;
    
    void main() {
    	gl_FragColor = vec4(0.229,1.000,0.971,1.000);
				    	#is a color hexa between `0.0` to `1.0`.
    }
### Type of vecteurs
`vec4` `vec3` `vec2` `vec1`

#### gl_FragColor
is the globale varible who do the color of the pixel

#### type `vec4`
vec4 is at four numbers white comma (`float`)
