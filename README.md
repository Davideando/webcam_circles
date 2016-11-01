# webcam_circleis
Circle detection from online webcam images

Fuentes de transformada Hough

Wikipedia

https://en.wikipedia.org/wiki/Hough_transform

Tutorial de Hough Circles

http://docs.opencv.org/2.4/doc/tutorials/imgproc/imgtrans/hough_circle/hough_circle.html

Definición en OpenCV
http://docs.opencv.org/2.4/modules/imgproc/doc/feature_detection.html?highlight=houghcircles#houghcircles

Si se coge la función de detección de circulos de hough:

void HoughCircles(InputArray image, OutputArray circles, int method, double dp, double minDist, double param1=100, double param2=100, int minRadius=0, int maxRadius=0 )

Los parametros se pueden definir como:

· image: Es la imagen donde se buscarán los circulos, y debe ser en blanco y negro. Normalmente esta imagen además esta filtrada, como en este ejemplo que se filtra utilizando un filtro Gausiano.

· circles: Es una array, en este caso de tres valores (posición en x, posición en y, radio), que devuelve la posición de todos los circulos que ha detectado en la imagen

· method: Es el metodo, por ahora solo funciona el paramegro CV_HOUGH_GRADIENT.

· dp: Es la inversa del ratio de la resolución del acumulador, es decir, proporciona la resolución que tendrá la salida. Si es 1, la salida tiene la misma resolución que la imagen, si es 2 tiene la mitad.

· minDist: Define la distancia mínima entre dos circulos detectados a la vez, Es decir, si el numero que hay es muy pequeño se pueden detectar circulos muy cercanos, y de esa manera, que haya falsas detecciones. Si es muy grande se pueden perder circulos intermedios.

· Param1: El el valor del umbral superior del detector canny integrado dentro de la función de hough. Este tipo de detector lo que hace es filtrar las imagenes que no están dentro del margen deseado. 

· Param2: Es el segundo parametro. En este caso es el umbral para la detección de los circulos, es decir, contra más pequeño sea, mas falsas detecciones habrán, contra más alto, menos. Hay que buscar un valor medio.

· minRadius: Aqui se establece cual ha de ser el radio mínimo del circulo detectado. De esta manera se pueden filtrar los circulos mas pequeños de un cierto número

· maxRadius: Es el contrarío, es decir, se determina cual será el máximo radio detectado. De esta manera se podrá acotar el tamaño máximo del circulo a detectar.


