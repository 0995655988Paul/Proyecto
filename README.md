#include <stdio.h>

float calcularDosisVitaminas(char sexo, float altura, float peso) {
    if ((sexo == 'M' || sexo == 'm') && altura > 1.60 && peso >= 150) {
        return 0.2 * altura + 0.8 * peso;
    } else if ((sexo == 'M' || sexo == 'm') && altura <= 1.60 && peso < 150) {
        return 0.3 * altura + 0.7 * peso;
    } else if ((sexo == 'F' || sexo == 'f') && altura > 1.50 && peso >= 130) {
        return 0.25 * altura + 0.75 * peso;
    } else {
        return 0.35 * altura + 0.65 * peso;
    }
}

int main() {
    char sexo;
    float peso, altura;

    do {
        printf("Ingrese el sexo (M/F): ");
        scanf(" %c", &sexo);

        printf("Ingrese el peso (en lb): ");
        scanf("%f", &peso);

        printf("Ingrese la altura (en m): ");
        scanf("%f", &altura);

        printf("Dosis de vitaminas: %.2f gramos\n", calcularDosisVitaminas(sexo, altura, peso));

        printf("¿Desea ingresar datos para otro estudiante? (S/N): ");
        scanf(" %c", &sexo);

    } while (sexo == 'S' || sexo == 's');

    return 0;
}
