# Editor_texto
Desarrolladores: Juan Camilo Velasquez Tobo
Juan David Tabares Rodríguez
Institución: Universidad Tecnológica de Pereira 
Programa: Ingeniería de Sistemas y Computación
Facultad: Ingenierías
Materia o Curso: Programación 2
Correo: judatar2@gmail.com

El proyecto elaborado en la herramienta qt, muestra una ventana en la cual, se observan diferentes íconos para efectuar las acciones de cortar, copiar, pegar, 
seleccionar todo, esto último para el contenido del cuadro de texto. Y las acciones de cerrar, guardar, guardar como y abrir, propias del archivo como tal. 
Dentro del repositorio se pueden evidenciar varios archivos, dentro de los cuales están algunos del tipo cpp, los cuales permiten que la aplicación se abra, y al 
mismo tiempo permite ajustar y desarrollar los cambios en términos de codificación, al aspecto de la ventana. Los archivos con extensión .h, 
contienen las acciones que corresponden a cada botón u opción de la ventana y finalmente el archivo .ui el cuál permite desarrollar las modificaciones de manera 
gráfica en la aplicación, abriendo una interfaz de modificaciones, con una vista previa de la ventana.

Explicación de funciones en el mainwindow.cpp:

#include:
Las directivas #include le indican al compilador que incluya los archivos de encabezado para las clases y distintas funciones que se utilizan en el código. En este 
caso, se incluyen los archivos de encabezado para las clases Qt Ui_MainWindow, QMessageBox, QFileDialog, QDebug, QSettings, QMainWindow, QFontComboBox y 
QPlainTextEdit.

*MainWindow::MainWindow(QWidget parent):

Este es el constructor de la clase MainWindow. Toma un QWidget* padre como argumento. El constructor configura la interfaz de usuario llamando al método setupUi() en 
el objeto miembro ui.

MainWindow::~MainWindow():

Este es el destructor de la clase MainWindow. Elimina el objeto miembro ui.

bool MainWindow::on_actionGuardar_Como_triggered()

Esta función se llama cuando se hace clic en el elemento de menú "Guardar como". Abre un cuadro de diálogo de guardado de archivos y guarda el contenido del widget 
plainTextEdit en el archivo seleccionado.

bool MainWindow::savefile():

Esta función guarda el contenido del widget plainTextEdit en el archivo especificado por el objeto miembro curlFile.

bool MainWindow::maybeSave():

Esta función verifica si el contenido del widget plainTextEdit ha sido modificado desde la última vez que se guardó. Si es así, le pregunta al usuario si desea
guardarlos. Si el usuario elige guardar, llama a la función savefile().

bool MainWindow::on_actionGuardar_triggered():

Esta función se llama cuando se hace clic en el elemento de menú "Guardar". Llama a la función maybeSave() y, si devuelve true, guarda el contenido del widget 
plainTextEdit en el archivo especificado por el objeto miembro curlFile.

void MainWindow::on_actionAbrir_Archivo_triggered():

Esta función se llama cuando se hace clic en el elemento de menú "Abrir archivo". Abre un cuadro de diálogo de apertura de archivos y carga el archivo seleccionado 
en el widget plainTextEdit.

void MainWindow::on_actionNuevo_triggered():

Esta función se llama cuando se hace clic en el elemento de menú "Nuevo". Borra el contenido del widget plainTextEdit.

*void MainWindow::closeEvent(QCloseEvent event):

Esta función se llama cuando el usuario intenta cerrar la ventana. Llama a la función maybeSave() y, si devuelve true, acepta el evento de cierre. De lo contrario, 
ignora el evento de cierre.

Explicación detallada de cada bloque de código:

Bloque 1: Constructor de la clase MainWindow:

El constructor de la clase MainWindow llama al método setupUi() en el objeto miembro ui para configurar la interfaz de usuario. La interfaz de usuario consta de un 
widget QPlainTextEdit para editar texto y un menú con los siguientes elementos:

"Guardar como"
"Guardar"
"Abrir archivo"
"Nuevo"

Bloque 2: Destructor de la clase MainWindow:

El destructor de la clase MainWindow elimina el objeto miembro ui.

Bloque 3: Función on_actionGuardar_Como_triggered():

La función on_actionGuardar_Como_triggered() abre un cuadro de diálogo de guardado de archivos y guarda el contenido del widget plainTextEdit en el archivo 
seleccionado.

Bloque 4: Función savefile():

La función savefile() guarda el contenido del widget plainTextEdit en el archivo especificado por el objeto miembro curlFile.

Bloque 5: Función maybeSave():

La función maybeSave() verifica si el contenido del widget plainTextEdit ha sido modificado desde la última vez que se guardó. Si es así, le pregunta al usuario si 
desea guardarlos. Si el usuario elige guardar, llama a la función savefile().

Bloque 6: Función on_actionGuardar_triggered():

La función on_actionGuardar_triggered() llama a la función maybeSave() y, si devuelve true, guarda el contenido del widget plainTextEdit en el archivo especificado 
por el objeto miembro curlFile.

Bloque 7: Función on_actionAbrir_Archivo_triggered():

La función on_actionAbrir_Archivo_triggered() abre un cuadro de diálogo de apertura de archivos y carga el archivo seleccionado en el widget plainTextEdit.

El código primero llama a la función maybeSave() para verificar si el contenido del widget plainTextEdit ha sido modificado desde la última vez que se guardó. Si es 
así, le pregunta al usuario si desea guardarlos. Si el usuario elige guardar, llama a la función savefile().

Si el contenido del widget plainTextEdit no ha sido modificado, la función abre un cuadro de diálogo de apertura de archivos. El cuadro de diálogo muestra una lista 
de archivos en el directorio especificado por la variable /home/juanc/Documents. El usuario puede seleccionar un archivo para abrir.

Si el usuario selecciona un archivo, la función abre el archivo y carga su contenido en el widget plainTextEdit. También establece la variable curlFile en el nombre 
del archivo abierto.

Bloque 8: Función on_actionNuevo_triggered():

La función on_actionNuevo_triggered() borra el contenido del widget plainTextEdit.
El código primero llama a la función maybeSave() para verificar si el contenido del widget plainTextEdit ha sido modificado desde la última vez que se guardó. Si es 
así, le pregunta al usuario si desea guardarlos. Si el usuario elige guardar, llama a la función savefile().

Si el contenido del widget plainTextEdit no ha sido modificado, la función borra el contenido del widget.

Bloque 9: Función closeEvent()

La función closeEvent() se llama cuando el usuario intenta cerrar la ventana. La función llama a la función maybeSave() para verificar si el contenido del widget
plainTextEdit ha sido modificado desde la última vez que se guardó. Si es así, le pregunta al usuario si desea guardarlos. Si el usuario elige guardar, llama a la 
función savefile().

Si el contenido del widget plainTextEdit no ha sido modificado, la función acepta el evento de cierre. De lo contrario, ignora el evento de cierre.



Manual técnico:

Objetivo:

El objetivo de este manual es proporcionar instrucciones paso a paso para utilizar el código. El código consta de una aplicación de editor de texto simple que 
permite al usuario crear, abrir, guardar y cerrar archivos de texto.

Requisitos:

Para utilizar el código Qt, se necesita lo siguiente:

1) Una computadora con el sistema operativo Linux, macOS o Windows.
2) El compilador Qt.

Instalación:

Para instalar el código Qt, siga estos pasos:

1) Descargue el compilador Qt de la página web de Qt.
2) Instale el compilador Qt siguiendo las instrucciones de instalación.

Compilación:

Para compilar el código Qt, siga estos pasos:

1) Cree una carpeta para el código.
2) Copie el código Qt en la carpeta que creó.
3) Abra una terminal en la carpeta que contiene el código Qt.
4) Ejecute el siguiente comando para compilar el código: qmake -o Makefile editor.pro make
Esto creará un archivo ejecutable llamado editor.

Uso:

Para utilizar el editor de texto, siga estos pasos:

1) Ejecute el archivo ejecutable editor.
2) Utilice el widget QPlainTextEdit para escribir o editar texto.
3) Para guardar el archivo, haga clic en el elemento de menú "Guardar" o presione Ctrl + S.
4) Para abrir un archivo, haga clic en el elemento de menú "Abrir" o presione Ctrl + O.
5) Para crear un nuevo archivo, haga clic en el elemento de menú "Nuevo" o presione Ctrl + N.
6) Para cerrar el editor, haga clic en el botón "X" en la esquina superior derecha de la ventana.

Paso a paso:

Crear un nuevo archivo:

1) Ejecute el archivo ejecutable editor.
2) Haga clic en el elemento de menú "Nuevo" o presione Ctrl + N.
3) El widget QPlainTextEdit se limpiará.
4) Puede comenzar a escribir o editar texto.

Guardar un archivo:

1) Escriba o edite el texto que desea guardar.
2) Haga clic en el elemento de menú "Guardar" o presione Ctrl + S.
3) Se abrirá un cuadro de diálogo de guardado de archivos.
4) Seleccione la ubicación donde desea guardar el archivo.
5) Escriba el nombre del archivo.
6) Haga clic en el botón "Guardar".

Abrir un archivo:

1) Haga clic en el elemento de menú "Abrir" o presione Ctrl + O.
2) Se abrirá un cuadro de diálogo de apertura de archivos.
3) Seleccione el archivo que desea abrir.
4) Haga clic en el botón "Abrir".
5) El contenido del archivo se cargará en el widget QPlainTextEdit.

Cerrar el editor:

1) Haga clic en el botón "X" en la esquina superior derecha de la ventana.
2) Se le pedirá que guarde el archivo si el contenido del widget QPlainTextEdit ha sido modificado.
3) Si desea guardar el archivo, haga clic en el botón "Sí".
4) Si no desea guardar el archivo, haga clic en el botón "No".

Errores comunes:

- Si el compilador Qt no se puede encontrar, asegúrese de haber instalado el compilador Qt correctamente.
- Si el código no se compila, asegúrese de que el archivo editor.pro esté configurado correctamente.
- Si el editor de texto no se abre, asegúrese de haber ejecutado el archivo ejecutable editor correctamente.

Conclusión:

Este manual proporciona instrucciones paso a paso para utilizar el código Qt proporcionado. El código consta de una aplicación de editor de texto simple que permite
al usuario crear, abrir, guardar y cerrar archivos de texto.


Datos de Contacto: 
Juan David Tabares Rodríguez
Cel:+573166170699
Correo:judatar2@gmail.com
Juan Camilo Velásquez Tobo
Cel:+573136992715
Correo: