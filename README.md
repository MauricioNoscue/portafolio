interface Bonificable {
    fun calcularBonificacion(): Double
}

open class Empleado(val nombre: String, val salario: Double) {
    fun mostrarInfo() {
        println("$nombre gana $$salario al mes.")
    }
}

class Desarrollador(nombre: String, salario: Double) : Empleado(nombre, salario), Bonificable {
    override fun calcularBonificacion(): Double {
        return salario * 0.10 
    }
}

class Gerente(nombre: String, salario: Double) : Empleado(nombre, salario), Bonificable {
    override fun calcularBonificacion(): Double {
        return salario * 0.20 
    }
}

fun main() {
    val dev = Desarrollador("Ana", 3000.0)
    val gerente = Gerente("Carlos", 5000.0)

    dev.mostrarInfo()
    println("Bonificación para el desarrollador: ${dev.calcularBonificacion()}")

    gerente.mostrarInfo()
    println("Bonificación para el gerente: ${gerente.calcularBonificacion()}")
}
