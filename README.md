# SwipeRefreshLayoutOverlay

![alt text](http://cl.ly/image/1h0U252w0S1Q/swiperefresh.png "SwipeRefreshLayoutOverlay")

## Warning! ¡Atención!

This library is now discontinued and you should only use it if you want to use the <21 support library in your application. In other case, the new support library SwipeRefreshLayout contains a new method, setProgressViewOffset, to set the view offset.

Esta biblioteca ha sido descontinuada y sólo deberías usarla si quieres utilizar la versión previa a la API 21 de la biblioteca de soporte. Para cualquier otro caso el SwipeRefreshLayout de la nueva biblioteca de soporte contiene el método setProgressViewOffset con el cual podrás ajustar el margen de la vista.

## English

### What is this?

SwipeRefreshLayoutOverlay is modification of Android's SwipeRefreshLayout to use this pattern when you're overlaying the ActionBar (or the Status Bar in >= KitKat).
If you use the original view in the support library you'll find out that the progress bar falls behind the ActionBar, making the refresh progress almost impossible to notice. Use this custom view instead of the original one to avoid the problem.
 
### Usage

It works just like the original SwipeRefreshLayout. You just have to call to the `setTopMargin` method with the desired margin (which should be the same as the ActionBar height, or the Status Bar + ActionBar heights if you're targeting KitKat or newer and the status bar is also translucent)

### Example

```java
public class Whatever extends Activity {
private SwipeRefreshLayoutOverlay swipeToRefresh;

...

@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);

swipeToRefresh = (SwipeRefreshLayoutOverlay) findViewById(R.id.refresher);
swipeToRefresh.setOnRefreshListener(this);
swipeToRefresh.setColorSchemeResources(android.R.color.holo_blue_bright, android.R.color.holo_green_light, android.R.color.holo_orange_light, android.R.color.holo_red_light);
swipeToRefresh.setTopMargin(getActionBar().getHeight());
}

...

}
```


## Español

### ¿Qué es esto?

SwipeRefreshLayoutOverlay es una modificación del SwipeRefreshLayout de Android para usar este patrón de diseño cuando utilizas una ActionBar translúcida (o una Status Bar translúcida si estás utilizando KitKat o superior). 
Si utilizas la view original de la librería de soporte verás que la barra de progreso queda detrás de la ActionBar, de forma que es muy difícil verla. Utiliza esta custom view en lugar de la original para solucionar el problema.
 
###Uso

Funciona igual que la SwipeRefreshLayout original. Simplemente tienes que llamar al método `setTopMargin` pasándole el margen deseado (que deberá ser igual que la altura de la ActionBar o de la Status Bar + la ActionBar si estás utilizando una Status Bar translúcida)

###Ejemplo

```java
public class Whatever extends Activity {
private SwipeRefreshLayoutOverlay swipeToRefresh;

...

@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);

swipeToRefresh = (SwipeRefreshLayoutOverlay) findViewById(R.id.refresher);
swipeToRefresh.setOnRefreshListener(this);
swipeToRefresh.setColorSchemeResources(android.R.color.holo_blue_bright, android.R.color.holo_green_light, android.R.color.holo_orange_light, android.R.color.holo_red_light);
swipeToRefresh.setTopMargin(getActionBar().getHeight());
}

...

}
```
