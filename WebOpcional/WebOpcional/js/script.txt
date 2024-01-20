document.addEventListener("DOMContentLoaded", function () {
    //PASAR CURSOR Enlaces
    const url = document.querySelectorAll(".url");
    url.forEach(x => x.addEventListener("mouseover", function () {
        this.style.color = "#e8786e";
    }));
    url.forEach(x => x.addEventListener("mouseleave", function () {
        this.style.color = "";
    }));

    //ZOOM IMAGENES
    const clientsimg = document.querySelectorAll(".clientsimg");
    clientsimg.forEach(x => x.addEventListener("mouseover", function () {
        this.style.transform = "scale(1.1)";
    }));
    clientsimg.forEach(x => x.addEventListener("mouseleave", function () {
        this.style.transform = "scale(1)";
    }));
    //PASAR CURSOR BOTONES
    const boton = document.querySelectorAll(".inputs");
    boton.forEach(x => x.addEventListener("mouseover", function () {
        this.style.backgroundColor = "#555";
        this.style.border = "none";
    }));
    boton.forEach(x => x.addEventListener("mouseleave", function () {
        this.style.backgroundColor = "";
        this.style.border = "";

    }));

    //click en circulos
    const circle = document.querySelectorAll(".image-circle");
    circle.forEach(x => x.addEventListener("click", function () {
        this.style.backgroundColor = '#' + Math.floor(Math.random() * 16777215).toString(16);
    }));

    // Seleccionamos todos los inputs con la clase ".box"
    const box = document.querySelectorAll(".box");

    // Para cada uno de esos inputs, agregamos dos eventos
    box.forEach(input => {

        // Este evento se dispara cuando el input recibe el foco, es decir, cuando el usuario hace clic en él
        input.addEventListener("focus", function () {
            // Cuando se hace clic en el input, independientemente de si tiene texto o no, establecemos el borde en rojo
            this.style.border = "2px solid red";
        });
        // Este evento se dispara cuando el usuario comienza a escribir en el input
        input.addEventListener("keydown", function () {
            // Cuando el usuario comienza a escribir, eliminamos el borde
            this.style.border = "";
        });

        // Este evento se dispara cuando el input pierde el foco, es decir, cuando el usuario hace clic fuera del input
        input.addEventListener("blur", function () {
            // Cuando el usuario hace clic fuera, verificamos si hay texto en el input
            if (this.value.trim() === "") {
                // Si el input está vacío, establecemos el borde en rojo
                this.style.border = "2px solid red";
            } else {
                // Si el input tiene texto, establecemos el borde en verde
                this.style.border = "2px solid green";
            }
        });
    });
    // ⦁	Si hacemos doble clic en el botón del formulario, nos aparecerá un alert con el mensaje: “formulario enviado”
    // seleccionamos el formulario
    const form = document.querySelector(".formbox form");

    form.addEventListener('submit', function (event) {
        event.preventDefault(); // previene la acción por defecto (enviar el formulario)
        alert('El formulario ha sido enviado');

    });

    // ⦁	Cuando el usuario copia algún texto de la sección “about us”, se escribe en el console.log el texto copiado.
    const aboutUs = document.querySelector(".container3");

    // Agrega un detector de eventos para el evento "copy"
    aboutUs.addEventListener("copy", function (event) {
        // Obtiene el texto seleccionado
        let selectedText = window.getSelection().toString();

        // Muestra el texto seleccionado en la consola
        console.log(`Se ha copiado lo siguiente: ${selectedText}`);
    });
    // ⦁	Cuando hagas un clic en la web con el botón derecho en cualquier parte del footer, se mostrará un alert con el mensaje “Has hecho clic con el botón derecho dentro del footer”

    // Seleccionamos el elemento footer en la página
    const footer = document.querySelector("footer");

    // Añadimos un detector de eventos para el evento 'contextmenu'
    footer.addEventListener('contextmenu', function (e) {
        // Mostramos un mensaje de alerta
        alert('Has hecho clic con el botón derecho dentro del footer');
    });

});