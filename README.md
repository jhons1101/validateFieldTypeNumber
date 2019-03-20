# validateLengthFieldTypeNumber
Validación de longitud de un campo tipo Number en JavaScript

A continuación, dos maneras de validar la longitud de un campo de tipo 'number', debido a que según la W3C definió que los campos tipo 'numbers' se validara su longitud como un rango de numeros y no cómo la longitud de una cadena (al no ser una cadena de texto)... Salió la necesidad de validar por JavaScript la cadena de una campo tipo 'number' ya que si los valores permitidos en un campo de texto, llegan a ser impredecibles o llegan a ser muy grandes, pues definir el rango de valores va a ser poco efectivo.

# Opción 1

&#60;input type="number" maxlength="4" name="year" class="form-control" onkeydown="if(this.value.length == 4) return false;"&#62;


# Opción 2 # recomendada

&#60;input type="number" maxlength="4" name="year" class="form-control" oninput="maxlengthNumber(this);"&#62;

&#60;script&#62;
    function maxlengthNumber (obj) {
    
        console.log(obj.value);
        
        if (obj.value.length > obj.maxLength) {
        
            obj.value = obj.value.slice(0, obj.maxLength);
            
        }
        
    }
    
&#60;/script&#62;
