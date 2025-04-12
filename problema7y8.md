<div style="text-align: center;">
  <h1>Veiculos</h1>
</div>

```dart
 mixin Volador {
  void volar() {
    print('Estoy volando');
  }
}

mixin Navegante {
  void navegar() {
    print('Estoy navegando');
  }
}

mixin Acelerable {
  void acelerar() {
    print('Estoy acelerando');
  }
}


class Vehiculo {
  void encender() {
    print('Vehículo encendido');
  }
}


class Avion extends Vehiculo with Volador, Acelerable {
  void tipo(){
    print('Soy un avión');
  }
}

class Bote extends Vehiculo with Navegante, Acelerable {
  void tipo(){
    print('Soy un bote');
  } 
}

class Auto extends Vehiculo with Acelerable {
  void tipo(){
    print('Soy un auto');
  }
}


void main() {
  Avion avion = Avion();
  Bote bote = Bote();
  Auto auto = Auto();

  print('\n (__Avión__) ');
  avion.tipo();
  avion.encender();
  avion.volar();
  avion.acelerar();

  print('\n (__Bote__) ');
  bote.tipo();
  bote.encender();
  bote.navegar();
  bote.acelerar();

  print('\n (__Auto__) ');
  auto.tipo();
  auto.encender();
  auto.acelerar();
}
```
<div style="text-align: center;">
  <h1>Poderes</h1>
</div>

```dart
mixin Hechicero {
  void lanzarHechizo() {
    print('Lanzo hechizos');
  }
}

mixin Guerrero {
  void atacarConArma() {
    print('Se blandir armas');
  }
}

mixin Sanador {
  void curarAliados() {
    print('Curo a mis aliados');
  }
}

class Personaje {
  final String nombre;

  Personaje(this.nombre);

  void presentarse() {
    print('Hola, soy $nombre');
  }
}

class Mago extends Personaje with Hechicero, Sanador {
  Mago(String nombre) : super(nombre);
}

class GuerreroClase extends Personaje with Guerrero {
  GuerreroClase(String nombre) : super(nombre);
}

class Paladin extends Personaje with Guerrero, Sanador {
  Paladin(String nombre) : super(nombre);
}

void main() {
  Mago mago = Mago('Odin');
  GuerreroClase guerrero = GuerreroClase('Conan');
  Paladin paladin = Paladin('Darknes');

  print('\n (__Mago__)');
  mago.presentarse();
  mago.lanzarHechizo();
  mago.curarAliados();

  print('\n (__Guerrero__)');
  guerrero.presentarse();
  guerrero.atacarConArma();

  print('\n (__Paladín__)');
  paladin.presentarse();
  paladin.atacarConArma();
  paladin.curarAliados();
}
```
