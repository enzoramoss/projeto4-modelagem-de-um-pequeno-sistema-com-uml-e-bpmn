# Projeto 4 – Modelagem de um Pequeno Sistema com UML e BPMN

**Data de Entrega:** 01/ABR  
**Integrantes:**  
- José Enzo Marinho Ramos
- Thiago Botelho Ribeiro Alexandre

---

## Diagrama de Classes (UML)

**Descrição:**  
Este diagrama apresenta uma estrutura simplificada para um sistema de reserva de salas. São utilizadas três classes principais: **Sala**, **Usuário** e **Reserva**. Cada Reserva está associada a uma única Sala e a um único Usuário. Uma Sala e um Usuário podem ter várias Reservas.

+-------------------------+

| Sala |

+-------------------------+

| - idSala: int |

| - nome: String |

| - capacidade: int |

+-------------------------+

| + agendar() |

| + liberar() |

+-------------------------+

| 1

|

| 1..*

|

+-------------------------+

| Reserva |

+-------------------------+

| - idReserva: int |

| - data: Date |

| - horarioInicio: Time |

| - horarioFim: Time |

+-------------------------+

| + confirmar() |

| + cancelar() |

+-------------------------+

^

| 1

|

+-------------------------+

| Usuário |

+-------------------------+

| - idUsuario: int |

| - nome: String |

| - email: String |

+-------------------------+

| + reservarSala() |

+-------------------------+

---

## Diagrama BPMN

**Descrição:**  
Este diagrama mostra o fluxo principal do processo de reserva de uma sala.

[Início]

[Solicitar Reserva] [Verificar Disponibilidade da Sala] {Sala disponível?}

├─ [Sim] ─> [Confirmar Reserva] ─> [Fim]                       └─ [Não] ─> [Informar Usuário] ─> [Fim]
