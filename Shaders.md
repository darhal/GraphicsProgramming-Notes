# Shaders
Shaders are small programs that run in a parallel fashion on the GPU. 
There are multiple shading languages the most famous among them are GLSL (primiarly used with OpenGL and Vulkan) and HLSL (Used with DirectX but can aslo be used with Vulkan).

## GLSL Concepts
GLSL syntax resembles a lot that of the C language. GLSL shaders always begin with version declaration followed by list of input and output variables. 
Like C the entry point is the main function where we process the inputs and assign the outputs to the output variables.

### Types : 
GLSL has the most of the default basic scalar types like :  `int`, `float`, `double`, `uint` and `bool`.  
It also has two container types that will be used a lot namely vectors and matricies. 
These types are limited to up to 4 components per dimension (2, 3 or 4).

#### Vectors
Components of vector can be accessed via their `.x`, `.y`, `.z` and `.w` components to access their 1st, 2nd, 3rd and fourth components respectively.  
GLSL also allow the use of `rgba` and `stpq` for color and texture coordinates respectively allowing access to the same components.  
The vector also allow for flexible component selection called *swizzling* which allow the use of syntax like this : 
```glsl
vec2 someVec;
vec4 differentVec = someVec.xyxx;
vec3 anotherVec = differentVec.zyw;
vec4 otherVec = someVec.xxxx + anotherVec.yxzy;
```
Similiarly we can construct other vectors based on this syntax : 
```
vec2 vect = vec2(0.5, 0.7);
vec4 result = vec4(vect, 0.0, 0.0);
vec4 otherResult = vec4(result.xyz, 1.0);
```

|Type|Fundamental Type|Dimension|
|----|----------------|---------|
|vecN|N float         |N       |
|dvecN|N double       |N       |
|ivecN|N integer      |N       |
|uvecN|N unsigned int |N       |
|bvecN|N bool         |N       |

Compon
### Vertex Shader : 
In the vertex shader, each input variable is also known as a vertex attribute. There is a maximum number of vertex attributes we are allowed to declare that is limited by the hardware. 
OGl guarantees at minimum 16 4-component vertex attributes. Some hardware may have more but the user have to query for this.

## HLSL Concepts
