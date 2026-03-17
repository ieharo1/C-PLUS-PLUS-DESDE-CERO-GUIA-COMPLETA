# ⚙️ C++ DESDE CERO - GUÍA COMPLETA

**C++ desde Cero** es un sitio educativo completo diseñado para enseñar C++ desde los fundamentos hasta conceptos avanzados, con explicaciones claras, ejemplos prácticos y código listo para usar.

> *"C++ is a general-purpose programming language created by Bjarne Stroustrup as an extension of the C programming language."*

---

## 🎯 ¿Qué es este Proyecto?

Este proyecto proporciona un recurso educativo gratuito para aprender C++, incluyendo:

- **Documentación completa** de cada tema
- **Ejemplos de código** listos para ejecutar
- **Ejercicios prácticos** para reforzar el aprendizaje
- **Sitio web educativo** con navegación intuitiva

---

## 📚 Contenido del Curso

### Módulo 1: Fundamentos

1. **Introducción**
   - Historia de C++
   - C++ moderno (C++11/14/17/20)
   - Casos de uso

2. **Instalación**
   - Compiladores (GCC, Clang, MSVC)
   - CMake y gestión de proyectos
   - IDEs recomendados
   - Configuración del entorno

3. **Conceptos básicos**
   - Variables y tipos de datos
   - Punteros y referencias
   - Control de flujo
   - Funciones

### Módulo 2: Intermedio

4. **Ejemplos prácticos**
   - Programación orientada a objetos
   - Templates y genéricos
   - STL (Standard Template Library)
   - Manejo de memoria

5. **Buenas prácticas**
   - Smart pointers
   - Move semantics
   - RAII pattern
   - Modern C++ idioms

### Módulo 3: Avanzado

6. **Casos reales**
   - Multithreading
   - Programación asíncrona
   - Redes y sockets
   - Optimización de rendimiento

7. **Proyecto final**
   - Aplicación completa
   - Build system con CMake
   - Testing con Google Test

---

## 🗂️ Estructura del Proyecto

```
Repositorio-HTML5-CSS-JS-Bootstrap-Linux/
├── index.html          # Página principal
├── css/
│   └── styles.css      # Estilos del sitio
├── js/
│   └── main.js         # JavaScript del sitio
└── README.md
```

---

## 🚀 Cómo Usar este Proyecto

### Opción 1: Navegar el Sitio Web

1. Abre `index.html` en tu navegador
2. Navega por las secciones del curso
3. Haz clic en los temas para ver la documentación detallada

### Opción 2: Ejecutar los Ejemplos

1. Instala compilador C++
2. Compila con `g++ archivo.cpp -o programa`
3. Ejecuta `./programa`

### Requisitos

- Compilador C++17 o superior
- CMake (opcional)
- IDE (VS Code, CLion, Visual Studio)

---

## 📝 Ejemplos Rápidos

### Variables y Tipos

```cpp
#include <iostream>
#include <string>

int main() {
    // Tipos fundamentales
    int edad = 30;
    double altura = 1.75;
    char inicial = 'J';
    bool esEstudiante = true;

    // Auto type deduction
    auto nombre = std::string("Juan");
    auto pi = 3.14159;

    std::cout << "Hola " << nombre << std::endl;
    return 0;
}
```

### Punteros y Referencias

```cpp
#include <iostream>

int main() {
    int valor = 42;

    // Puntero
    int* ptr = &valor;
    std::cout << *ptr << std::endl;

    // Referencia
    int& ref = valor;
    ref = 100;

    // Smart pointers (C++11)
    auto unique = std::make_unique<int>(42);
    auto shared = std::make_shared<int>(42);

    return 0;
}
```

### Clases

```cpp
#include <iostream>
#include <string>

class Persona {
private:
    std::string nombre;
    int edad;

public:
    // Constructor
    Persona(std::string n, int e) : nombre(n), edad(e) {}

    // Métodos
    void saludar() const {
        std::cout << "Hola, soy " << nombre << std::endl;
    }

    // Getters/Setters
    std::string getNombre() const { return nombre; }
    void setEdad(int e) { edad = e; }

    // Destructor
    ~Persona() = default;
};
```

### Templates

```cpp
#include <iostream>
#include <vector>

// Función template
template<typename T>
T maximo(T a, T b) {
    return (a > b) ? a : b;
}

// Clase template
template<typename T>
class Contenedor {
private:
    T valor;
public:
    Contenedor(T v) : valor(v) {}
    T getValor() const { return valor; }
};

// Uso
int main() {
    std::cout << maximo(5, 10) << std::endl;
    Contenedor<int> cont(42);
    return 0;
}
```

### STL Containers

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <algorithm>

int main() {
    // Vector
    std::vector<int> numeros = {1, 2, 3, 4, 5};
    numeros.push_back(6);

    // Map
    std::map<std::string, int> edades;
    edades["Juan"] = 30;
    edades["Maria"] = 25;

    // Algoritmos
    std::sort(numeros.begin(), numeros.end());
    auto it = std::find(numeros.begin(), numeros.end(), 3);

    // Range-based for
    for (const auto& num : numeros) {
        std::cout << num << " ";
    }

    return 0;
}
```

### Move Semantics

```cpp
#include <iostream>
#include <vector>
#include <utility>

class Recurso {
public:
    Recurso() { std::cout << "Constructor\n"; }
    ~Recurso() { std::cout << "Destructor\n"; }

    // Move constructor
    Recurso(Recurso&& other) noexcept {
        std::cout << "Move constructor\n";
    }

    // Move assignment
    Recurso& operator=(Recurso&& other) noexcept {
        std::cout << "Move assignment\n";
        return *this;
    }
};

int main() {
    std::vector<Recurso> recursos;
    recursos.reserve(10);

    Recurso r;
    recursos.push_back(std::move(r));  // Move en lugar de copy

    return 0;
}
```

---

## 🎓 Metodología de Aprendizaje

### 1. Leer la Teoría
Cada tema comienza con una explicación clara del concepto.

### 2. Ver Ejemplos
Los ejemplos de código muestran la aplicación práctica.

### 3. Practicar
Los ejercicios te permiten aplicar lo aprendido.

### 4. Experimentar
Modifica los ejemplos para entender cómo funcionan.

---

## 🔧 Comandos Esenciales

### Compilación

```bash
# Compilar simple
g++ main.cpp -o programa

# Compilar con C++17
g++ -std=c++17 main.cpp -o programa

# Compilar con warnings
g++ -Wall -Wextra -std=c++17 main.cpp -o programa

# Compilar con debug
g++ -g -std=c++17 main.cpp -o programa

# Múltiples archivos
g++ -std=c++17 main.cpp utils.cpp -o programa

# Usar CMake
mkdir build && cd build
cmake ..
make
```

---

## 📖 Recursos Adicionales

### Documentación Oficial

- [C++ Reference](https://en.cppreference.com/)
- [ISO C++](https://isocpp.org/)
- [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines)

### Herramientas Recomendadas

- **CMake** - Build system
- **CLion** - IDE de JetBrains
- **Visual Studio** - IDE completo
- **Conan** - Package manager

### Comunidades

- [C++ Community](https://isocpp.org/community)
- [Stack Overflow - C++](https://stackoverflow.com/questions/tagged/c%2B%2B)
- [Reddit r/cpp](https://www.reddit.com/r/cpp/)

---

## 💡 Consejos para Principiantes

1. **Empieza con C++ moderno**: Usa C++17 o C++20.
2. **Evita new/delete**: Usa smart pointers.
3. **Aprende STL**: Es fundamental.
4. **Entiende RAII**: Es clave en C++.
5. **Usa const correctness**: Previene errores.

---

## ⚠️ Mejores Prácticas

### Seguridad

- Usa smart pointers en lugar de raw pointers
- Valida siempre los inputs
- Evita buffer overflows

### Rendimiento

- Usa move semantics cuando sea posible
- Reserva memoria con reserve()
- Pasa por referencia const

### Código Limpio

- Sigue las C++ Core Guidelines
- Usa nombres descriptivos
- Mantén funciones pequeñas

---

## 🧪 Ejercicios Prácticos

### Nivel Básico

1. Calculadora de consola
2. Gestor de contactos
3. Juego de adivinar números

### Nivel Intermedio

1. Sistema de archivos
2. Servidor TCP simple
3. Implementación de estructuras de datos

### Nivel Avanzado

1. Motor de juegos simple
2. Sistema multihilo
3. Compilador simple

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
