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
### Type
`float`, `int` & `bool`

### Type of presition
precision lowp float;


### Type of vecteurs
`vec4` `vec3` `vec2` `vec1`

#### gl_FragColor
is the globale varible who do the color of the pixel

#### type `vec4`
vec4 is at four numbers white comma (`float`)


Text complementary


#### ifndef
Une autre caractéristique du C importante que nous pouvons voir dans cet exemple est la présence de macros de préprocesseur. Les macros font partie de l'étape de pré-compilation, elles permettent de définir (`#define`) des variables globales et de faire des opérations conditionnelles de base (avec  `#ifdef`  &  `#endif`). Toutes les macros commencent par un hashtag (`#`). La pré-compilation se produit - comme son nom l'indique - avant la compilation du shader, elle copie et renseigne tous les  `#define`  et vérifie les inclusions conditionnelles  `#ifdef`  (si défini) et  `#ifndef`  (si non défini). Dans l'exemple ci-dessus, nous n'insérons la ligne 2 que si  `GL_ES`  est défini, ce qui se produit principalement lorsque le code est compilé sur mobile ou dans un navigateur. 
#### float
Le type `float` est vital dans les shaders, donc le niveau de _précision_ des nombres flottants est crucial. Une précision basse permet un rendu plus rapide mais une qualité moindre et inversement, une précision élevée permet un meilleur rendu au prix de performances réduites. On peut spécifier la précision de chaque variable se servant de, ligne 2, `precision mediump float;`, nous assignons la précision _medium_ à tous les flottants de l'application. Nous pourrions leur donner une valeur basse (`precision lowp float;`) ou haute (`precision highp float;`).

###  Syntaxe avec les points 
La dernière remarque, probablement la plus importante, est que les spécifications GLSL ne garantissent pas que les variables seront _castées_ automatiquement. Qu'est-ce que cela veut dire ? Les fabricants ont des approches différentes pour accélérer leurs cartes graphiques mais ils doivent toutefois se conformer au minimum à un ensemble de spécifications communes. Le casting automatique des variables ne fait pas partie des spécifications. Dans notre exemple, `vec4` attend des `floats` et rien d'autre. Si vous voulez obtenir un code homogène et éviter de passer des heures à débugger un écran blanc, prenez l'habitude de mettre des points (`.`) dans vos floats. Ce genre de code ne marchera pas toujours :




# Errors

    void main() { gl_FragColor = vec4(1,0,0,1); // ERROR }

    void main() { gl_FragColor = vec4(1., .0, 0., 1.); // BETTER }

