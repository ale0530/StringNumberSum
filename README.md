java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class SumaNumeros {

    public static void main(String[] args) {
        String myString = "asfsdalgkjerio435j342234234nh234o32rnowei23io4h324oi32423o4w.,345.,34534534ew342rasfsdalgkjerio435j342234234nh234o32rnowei23io4h324oi32423o4w.,345.,34534534ewf342rasfsdalgkjerio435j342234234nh234o32rnowei23io4h324oi32423o4w.,345., 34534534ewf342rasfsdalgkjerio435j342234234nh234o32rnowei23io4h324oi32423o4w., 345.,34534534ewf342r";
        
        // Llamada al método para obtener la suma
        int suma = sumarNumeros(myString);
        System.out.println("La suma de los números es: " + suma);
    }

    /**
     * Método que toma un String y retorna la suma de todos los números enteros encontrados.
     *
     * @param input El String de entrada que puede contener números.
     * @return La suma de los números enteros encontrados en el String.
     */
    public static int sumarNumeros(String input) {
        // Validación de entrada
        if (input == null || input.isEmpty()) {
            System.out.println("La cadena está vacía o es nula.");
            return 0; // Retorna 0 si la entrada no es válida
        }

        int suma = 0;

        // Usando expresiones regulares para encontrar números
        Pattern pattern = Pattern.compile("\\d+");
        Matcher matcher = pattern.matcher(input);

        // Buscar todos los números en el String
        while (matcher.find()) {
            // Convertir el número encontrado a entero y sumarlo
            suma += Integer.parseInt(matcher.group());
        }

        // Retornar la suma total
        return suma;
    }
}
