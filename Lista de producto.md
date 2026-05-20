# Índice de Productos

| #   | Producto                                                                               | Descripción                                    |
| --- | -------------------------------------------------------------------------------------- | ---------------------------------------------- |
| 1   | [Producto 021](#producto-021--indicador-de-capacidad-de-la-terminal)                   | Indicador de Capacidad de la Terminal          |
| 2   | [Producto 028 (1 dígito)](#producto-028--indicador-de-encripción-3desdukpt-1-dígito)   | Indicador de Encripción 3DES/DUKPT (1 dígito)  |
| 3   | [Producto 028 (2 dígitos)](#producto-028--indicador-de-encripción-3desdukpt-2-dígitos) | Indicador de Encripción 3DES/DUKPT (2 dígitos) |
| 4   | [Producto 084](#producto-084--ksn-dukpt)                                               | KSN DUKPT                                      |
| 5   | [Producto 078](#producto-078--indicador-de-mpos)                                       | Indicador de mPOS                              |
| 6   | [Producto 022](#producto-022--indicador-de-fallback)                                   | Indicador de Fallback                          |
| 7   | [Producto 101](#producto-101--indicador-de-requerimiento-de-tid)                       | Indicador de requerimiento de TID              |
| 8   | [Producto 043](#producto-043--tid-terminal-identification)                             | TID (Terminal Identification)                  |
| 9   | [Producto 103](#producto-103--identificador-del-submerchant-id)                        | Identificador del Submerchant ID               |
| 10  | [Producto 062](#producto-062--nombre-o-datos-del-submerchant)                          | Nombre o Datos del Submerchant                 |
| 11  | [Producto 033](#producto-033--datos-del-submerchant-payfac)                            | Datos del Submerchant (PayFac)                 |
| 12  | [Producto 102](#producto-102--identificador-del-gateway)                               | Identificador del Gateway                      |
| 13  | [Producto 094](#producto-094--indicador-de-autorización-parcial)                       | Indicador de Autorización Parcial              |
| 14  | [Producto 044](#producto-044--importe-original-solicitado)                             | Importe Original Solicitado                    |
| 15  | [Producto 061](#especificaciones-de-producto-061-campo-iso-59)                         | Envío de Código de Seguridad                   |
| 16  | [Producto 083](#especificaciones-de-producto-083-operatoria-qr)                        | Operatoria QR                                  |
| 17  | [Producto 085](#producto-085--id-de-billetera)                                         | Id Billetera                                   |
| 18  | [Producto 106](#producto-106--debt-repayment)                                          | Debt Repayment                                 |

---

# Producto 021 – Indicador de Capacidad de la Terminal

Con el propósito de informarle al Host cuál es la capacidad máxima de ingreso que acepta la terminal, se enviará este producto.

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**                           |
| -------------------------- | ------------ | --------- | ----------- | ----------------------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                                         |
| **Tipo de Producto**       | An3          | 3         | ASCII       | Identifica el Tipo de Producto: **"021"** |
| **Cantidad de Subcampos**  | N4           | 4         | ASCII       | Cantidad utilizada: **"0001"**            |
| **Longitud Sub-Campo**     | N3 / An3     | 3         | ASCII       | Longitud del Subcampo: **"004"**          |
| **Identificador Subcampo** | An4          | 1         | ASCII       | Subcampo **"070"**                        |
| **Dato del Subcampo**      | An4          | 1         | ASCII       | Indicador de capacidad de captura         |

## Valores posibles del Subcampo 070

| **Valor** | **Significado**     |
| --------- | ------------------- |
| 1         | Manual / E-commerce |
| 2         | Lectura de banda    |
| 5         | Lectura de chip     |
| 7         | Lectura Contactless |

## Ejemplo ASCII

02100010040701

## Observaciones

- Este producto es **mandatorio** para operaciones de **mundo presente y ecommerce**.

## ✔️ Caso 1 — Capacidad de encripción de **1 dígito** (0..9)

# Producto 028 – Indicador de Encripción 3DES/DUKPT (1 dígito)

## Tabla Técnica

| **Dato**                  | **Atributo** | **Bytes** | **Formato** | **Comentarios**                                                            |
| ------------------------- | ------------ | --------- | ----------- | -------------------------------------------------------------------------- |
| **Longitud Total**        | N2           | 2         | BCD         | —                                                                          |
| **Tipo de Producto**      | An3          | 3         | ASCII       | “028”                                                                      |
| **Cantidad de Subcampos** | N4           | 4         | ASCII       | “0001”                                                                     |
| **Longitud Sub-Campo**    | N3           | 3         | ASCII       | “004”                                                                      |
| **ID Sub-Campo**          | An3          | 3         | ASCII       | “078”                                                                      |
| **Dato Sub-Campo**        | N1           | 1         | ASCII       | Capacidad de encripción 3DES asignada por PRISMA MP (0–9) Ref tabla indice |

## Ejemplo ASCII

```
0280001004078X

    (X = valor de 0 a 9)
```

## ✔️ Caso 2 — Capacidad de encripción de **2 dígitos** (10..99)

# Producto 028 – Indicador de Encripción 3DES/DUKPT (2 dígitos)

## Tabla Técnica

| **Dato**                  | **Atributo** | **Bytes** | **Formato** | **Comentarios**                                                               |
| ------------------------- | ------------ | --------- | ----------- | ----------------------------------------------------------------------------- |
| **Longitud Total**        | N2           | 2         | BCD         | —                                                                             |
| **Tipo de Producto**      | An3          | 3         | ASCII       | “028”                                                                         |
| **Cantidad de Subcampos** | N4           | 4         | ASCII       | “0001”                                                                        |
| **Longitud Sub-Campo**    | N3           | 3         | ASCII       | “005”                                                                         |
| **ID Sub-Campo**          | An3          | 3         | ASCII       | “078”                                                                         |
| **Dato Sub-Campo**        | N2           | 2         | ASCII       | Capacidad de encripción 3DES asignada por PRISMA MP (10..99) Ref tabla indice |

## Ejemplo ASCII

```
0280001005078XX

    (XX = valor entre 10 y 99)
```

### Índices de Dispositivos Payway Productivos

| Índice | Dispositivo        |
| ------:| ------------------ |
| 4      | Newland N910+      |
| 6      | Ingenico Lane 3000 |
| 11     | Nexgo N6           |

# Producto 084 – KSN DUKPT

## Tabla Técnica

| **Dato**                  | **Atributo** | **Bytes** | **Formato** | **Comentarios**                  |
| ------------------------- | ------------ | --------- | ----------- | -------------------------------- |
| **Longitud Total**        | N2           | 2         | BCD         | —                                |
| **Tipo de Producto**      | An3          | 3         | ASCII       | “084”                            |
| **Cantidad de Subcampos** | N4           | 4         | ASCII       | “0001”                           |
| **Longitud Sub-Campo**    | N3           | 3         | ASCII       | “023”                            |
| **ID Sub-Campo**          | An3          | 3         | ASCII       | “209”                            |
| **Dato Sub-Campo**        | An20         | 20        | ASCII       | Valor KSN en hexadecimal (DUKPT) |

## Ejemplo ASCII

0840001003209XXXXXXXXXXXXXXXXXXXX

    (20 caracteres hexadecimales)

# Producto 078 – Indicador de mPOS

Se incorpora a la mensajería actual el producto 078 del Campo ISO 59.

## Tabla Técnica – Caso General (VISA y otras marcas)

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**    |
| -------------------------- | ------------ | --------- | ----------- | ------------------ |
| **Longitud Total**         | N3           | 2         | BCD         | —                  |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “078”              |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”             |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “005”              |
| **ID Sub-Campo**           | An3          | 3         | ASCII       | “200”              |
| **Dato Sub-Campo**         | An2          | 2         | ASCII       | Enviar “MP” (mPOS) |

## Ejemplo ASCII (VISA)

```
0780001005200MP
```

# Extensión para MasterCard / Maestro

Para transacciones MasterCard/Maestro, se debe **agregar un segundo subcampo** adicional “211”.

## Tabla Técnica – Subcampo adicional para MC/Maestro

| **Dato**               | **Atributo** | **Bytes** | **Formato** | **Comentarios**     |
| ---------------------- | ------------ | --------- | ----------- | ------------------- |
| **Longitud Sub-Campo** | N3           | 3         | ASCII       | “004”               |
| **ID Sub-Campo**       | An3          | 3         | ASCII       | “211”               |
| **Dato Sub-Campo**     | An1          | 1         | ASCII       | Tipo de dispositivo |

## Valores posibles – Subcampo 211 (MasterCard/Maestro)

| **Valor** | **Significado**                   |
| --------- | --------------------------------- |
| 0         | Dispositivo que cumple PCI        |
| 1         | Dispositivo móvil listo para usar |
| 2–9       | Reservado                         |

## Ejemplo ASCII completo (MasterCard)

```
0780002005200MP0042110
```

# Producto 022 – Indicador de Fallback

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**           |
| -------------------------- | ------------ | --------- | ----------- | ------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                         |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “022”                     |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                    |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “004”                     |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “071”                     |
| **Dato Sub-Campo**         | An4          | 1         | ASCII       | Identificador de fallback |

## Valores posibles del Subcampo 071

| **Valor** | **Significado** |
| --------- | --------------- |
| F         | Fallback        |

## Ejemplo ASCII

```
0220001004071F
```

## Observaciones

- Este producto indica que la terminal ha realizado **fallback** (por ejemplo, chip fallido → lectura de banda).

# Producto 101 – Indicador de requerimiento de TID

Este producto informa que el comercio está preparado para recibir el TID provisto por la marca dentro del Campo ISO 60.

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**                   |
| -------------------------- | ------------ | --------- | ----------- | --------------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                                 |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “101”                             |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                            |
| **Longitud Sub-Campo**     | N3 / An3     | 3         | ASCII       | “004”                             |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “241”                             |
| **Dato Sub-Campo**         | An1          | 1         | ASCII       | Indicador de requerimiento de TID |

## Valores posibles del Subcampo 241

| **Valor** | **Significado**                                 |
| --------- | ----------------------------------------------- |
| 1         | Comercio requiere recibir un TID desde la marca |

## Ejemplo ASCII

```
10100010042411
```

## Observaciones

- Este producto se envía desde la **terminal** o **sistema propio del comercio**.
- Permite que la marca devuelva un **TID dinámico** en el ISO 60 de las transacciones 0110/0210.

# Producto 043 – TID (Terminal Identification)

Este producto contiene el **TID asignado por la marca**, enviado por la red en el Campo ISO 60 de los mensajes de respuesta 0110 / 0210.

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**           |
| -------------------------- | ------------ | --------- | ----------- | ------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                         |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “043”                     |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                    |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “018”                     |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “113”                     |
| **Dato Sub-Campo**         | Ans15        | 15        | ASCII       | TID provisto por la marca |

## Ejemplo ASCII

```
0430001003113XXXXXXXXXXXXXXX
```

(“XXXXXXXXXXXXXXX” = TID de 15 caracteres alfanuméricos)

## Observaciones

- El TID enviado aquí **no lo define el comercio**, lo **asigna la marca**.
- El TID puede variar según reglas de cada marca y modalidad.
- Este producto se devuelve **solo si el comercio envía antes el Producto 101** solicitando el TID.

# Producto 103 – Identificador del Submerchant ID

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**               |
| -------------------------- | ------------ | --------- | ----------- | ----------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                             |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “103”                         |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                        |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “018”                         |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “243”                         |
| **Dato Sub-Campo**         | AN15         | 15        | ASCII       | Identificador del Submerchant |

## Descripción del Dato del Subcampo (243)

- Identificador único del **Submerchant**, asignado por el **PayFac**.  
- Alineado a la izquierda, rellenado con espacios a la derecha.  
- Similar al formato del Nro de establecimiento del campo 42.

## Observaciones

- El Submerchant ID debe ser **único por subcomercio** en las bases del PayFac.

# Producto 062 – Nombre o Datos del Submerchant

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**          |
| -------------------------- | ------------ | --------- | ----------- | ------------------------ |
| **Longitud Total**         | N3           | 2         | BCD         | —                        |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “062”                    |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                   |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “028”                    |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “157”                    |
| **Dato Sub-Campo**         | ANS25        | 25        | ASCII       | Nombre/Datos Submerchant |

## Reglas del contenido del Subcampo 157

Debe formarse así:

1. **Nombre abreviado del PayFac** (3, 7 o 12 caracteres)  
2. Un **asterisco “*”** en la posición siguiente  
3. **Nombre del submerchant** desde la posición 5, 9 o 14, según el caso  

### Ejemplo de estructura:

```
PFAC*SUBMERCHANT
PAYFACABR*TIENDA
```

## Observaciones

- La longitud total del valor no puede superar **25 caracteres**.

# Producto 033 – Datos del Submerchant (PayFac)

## Tabla Técnica General

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**         |
| -------------------------- | ------------ | --------- | ----------- | ----------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                       |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “033”                   |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0018”                  |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | Variable según subcampo |

# Subcampos (0018 en total)

## Subcampo 089

| **Dato** | **Long** | **Tipo** | **Descripción**                                    |
| -------- | -------- | -------- | -------------------------------------------------- |
| 089      | 1        | N1       | Tipo de documento<br>0 = CUIT / 1 = CUIL / 2 = DNI |

## Subcampo 090

| **Dato** | **Long** | **Tipo** | **Descripción**                                              |
| -------- | -------- | -------- | ------------------------------------------------------------ |
| 090      | 11       | N11      | Número de CUIT/CUIL/DNI. Completar con ceros a la izquierda. |

## Subcampo 068

| **Dato** | **Long** | **Tipo** | **Descripción**                                             |
| -------- | -------- | -------- | ----------------------------------------------------------- |
| 068      | 12       | AN12     | Nro. de factura a pagar. Izquierda texto, derecha espacios. |

## Subcampo 069

| **Dato** | **Long** | **Tipo** | **Descripción**                    |
| -------- | -------- | -------- | ---------------------------------- |
| 069      | 12       | ANS12    | Nro. factura anulación/devolución. |

## Subcampo 094

| **Dato** | **Long** | **Tipo** | **Descripción**                             |
| -------- | -------- | -------- | ------------------------------------------- |
| 094      | 20       | ANS20    | Nombre del submerchant o “Nombre/Apellido”. |

## Subcampo 095

| **Dato** | **Long** | **Tipo** | **Descripción**                                          |
| -------- | -------- | -------- | -------------------------------------------------------- |
| 095      | 30       | ANS30    | Dirección (calle, altura, piso, localidad). Obligatorio. |

## Subcampo 003

| **Dato** | **Long** | **Tipo** | **Descripción**                                         |
| -------- | -------- | -------- | ------------------------------------------------------- |
| 003      | 6        | ANS6     | Número de puerta. Completar con blancos a la izquierda. |

## Subcampo 097

| **Dato** | **Long** | **Tipo** | **Descripción**             |
| -------- | -------- | -------- | --------------------------- |
| 097      | 8        | AN8      | Código Postal. Obligatorio. |

## Subcampo 096

| **Dato** | **Long** | **Tipo** | **Descripción**          |
| -------- | -------- | -------- | ------------------------ |
| 096      | 5        | AN5      | Código MCC. Obligatorio. |

## Subcampo 098

| **Dato** | **Long** | **Tipo** | **Descripción**  |
| -------- | -------- | -------- | ---------------- |
| 098      | 3        | AN3      | Código de Canal. |

## Subcampo 112

| **Dato** | **Long** | **Tipo** | **Descripción**    |
| -------- | -------- | -------- | ------------------ |
| 112      | 5        | AN5      | Código Geográfico. |

## Subcampo 154

| **Dato** | **Long** | **Tipo** | **Descripción**     |
| -------- | -------- | -------- | ------------------- |
| 154      | 20       | ANS20    | Producto que vende. |

## Subcampo 244

| **Dato** | **Long** | **Tipo** | **Descripción**                      |
| -------- | -------- | -------- | ------------------------------------ |
| 244      | 16       | AN13     | Ciudad del submerchant. Obligatorio. |

## Subcampo 245

| **Dato** | **Long** | **Tipo** | **Descripción**                     |
| -------- | -------- | -------- | ----------------------------------- |
| 245      | 6        | A3       | Código país (Alpha‑3). Obligatorio. |

## Subcampo 246

| **Dato** | **Long** | **Tipo** | **Descripción**                                             |
| -------- | -------- | -------- | ----------------------------------------------------------- |
| 246      | 6        | AN3      | Subdivisión del país (provincia/departamento). Obligatorio. |

## Subcampo 247

| **Dato** | **Long** | **Tipo** | **Descripción**      |
| -------- | -------- | -------- | -------------------- |
| 247      | 53       | AN50     | URL del submerchant. |

## Subcampo 248

| **Dato** | **Long** | **Tipo** | **Descripción**               |
| -------- | -------- | -------- | ----------------------------- |
| 248      | 19       | AN16     | Teléfono servicio al cliente. |

## Subcampo 249

| **Dato** | **Long** | **Tipo** | **Descripción**                                                   |
| -------- | -------- | -------- | ----------------------------------------------------------------- |
| 249      | 6        | N3       | Código país del gobierno que controla al submerchant (si aplica). |

# Producto 102 – Identificador del Gateway

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**                       |
| -------------------------- | ------------ | --------- | ----------- | ------------------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                                     |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “102”                                 |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                                |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “014”                                 |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “242”                                 |
| **Dato Sub-Campo**         | AN11         | 11        | ASCII       | Identificador de Gateway (Gateway ID) |

## Descripción del Subcampo 242

- Identificador asignado por el integrador/gateway.  
- Debe ser único para cada plataforma de pago.  
- Longitud fija: **11 caracteres** (alfanumérico, ASCII).

## Ejemplo ASCII

1020001004242XXXXXXXXXXX

    Donde `XXXXXXXXXXX` = Gateway ID (11 caracteres).
    
    ## Observaciones
    - Este producto permite que la marca identifique qué **gateway** intervino en la transacción.  
    - Se envía típicamente en operaciones **eCommerce** y flujos con **procesadores externos**.

# Producto 094 – Indicador de Autorización Parcial

Este producto informa si la terminal está habilitada para procesar **autorizaciones parciales**.  
Es mandatorio para todo dispositivo que soporte esta operativa.  
Aplica únicamente para transacciones de **compra**, processing code “00”, MTI **0200**.

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**                   |
| -------------------------- | ------------ | --------- | ----------- | --------------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                                 |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “094”                             |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                            |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “004”                             |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “230”                             |
| **Dato Sub-Campo**         | Ans1         | 1         | ASCII       | Indicador de autorización parcial |

## Valores permitidos en Subcampo 230

| **Valor** | **Descripción**                 |
| --------- | ------------------------------- |
| 1         | Autorización parcial habilitada |

## Ejemplo ASCII

09400010042301

```
## Observaciones
- Debe enviarse **siempre** que el dispositivo soporte autorizaciones parciales.
- Afecta únicamente mensajes ISO **0200** (request de compra).
```

# Producto 044 – Importe Original Solicitado

Este producto se envía en el **ISO 60 de la respuesta 0210**, únicamente cuando la marca responde:  
**Response Code = “10”** (transacción aprobada parcialmente).

Indica el importe original enviado por el comercio en el ISO 0200.

## Tabla Técnica

| **Dato**                   | **Atributo** | **Bytes** | **Formato** | **Comentarios**           |
| -------------------------- | ------------ | --------- | ----------- | ------------------------- |
| **Longitud Total**         | N3           | 2         | BCD         | —                         |
| **Tipo de Producto**       | An3          | 3         | ASCII       | “044”                     |
| **Cantidad de Sub-Campos** | N4           | 4         | ASCII       | “0001”                    |
| **Longitud Sub-Campo**     | N3           | 3         | ASCII       | “015”                     |
| **Identificador Subcampo** | An3          | 3         | ASCII       | “114”                     |
| **Dato Sub-Campo**         | Ans12        | 12        | ASCII       | Importe original en pesos |

## Formato del Importe (Subcampo 114)

- 10 enteros  
- 2 decimales  
- Sin separadores ni signos  
- Relleno a izquierda con ceros si corresponde  

### Ejemplo

Monto original: **1.234,50** → “000000123450”

## Ejemplo ASCII

```
0440001005114000000123450
```

## Observaciones

- Se usa **solo** cuando la red determina que la transacción debe aprobarse por un monto menor al solicitado.
- El campo 4 en 0210 mostrará el monto autorizado; este producto muestra el monto original.

# Especificaciones de Producto 061 (Campo ISO 59)

## 1. PRODUCTO 061 – ENVÍO DE CÓDIGO DE SEGURIDAD

El producto **061** tiene como propósito trasladar los datos del identificador **"Con Control"** y la **dirección IP de origen**, bajo el siguiente formato:

| **Dato**               | **Atributo** | **Bytes** | **Formato** | **Comentarios**                                                |
| ---------------------- | ------------ | --------- | ----------- | -------------------------------------------------------------- |
| Tipos de Producto      | An3          | 3         | ASCII       | "061"                                                          |
| Cantidad de Sub-Campos | N4           | 4         | ASCII       | "0002"                                                         |
| Longitud Sub-Campo     | N3           | 3         | ASCII       | "006"                                                          |
| ID Sub-Campo           | An3          | 3         | ASCII       | "155"                                                          |
| Dato Sub-Campo         | AnS..20      | ..20      | ASCII       | "CCT"                                                          |
| Longitud Sub-Campo     | N3           | 3         | ASCII       | "015"                                                          |
| ID Sub-Campo           | An3          | 3         | ASCII       | "156"                                                          |
| Dato Sub-Campo         | An..12       | ..12      | ASCII       | IP de origen (completo, sin puntos y con blancos a la derecha) |

## 2. MENSAJERÍA VISA PARA NO ENVIAR CÓDIGO DE SEGURIDAD

### Contexto: Pago Recurrente

Se utiliza el producto **061** del Campo ISO 59 para trasladar los datos del identificador **"Sin control"** y la **dirección IP de origen**.

> **Nota importante:** > * La dirección IP de origen es deseable pero no mandatoria. En caso de no obtenerla del Comercio, enviar la del Gateway de pago.
> 
> - En este caso **no se enviará el campo ISO 55** que contiene el CVV2.

### Estructura de Datos

| **Dato**                    | **Atributo** | **Bytes** | **Formato** | **Comentarios**                                              |
| --------------------------- | ------------ | --------- | ----------- | ------------------------------------------------------------ |
| Longitud Total              | N3           | 2         | BCD         |                                                              |
| Tipo de Producto            | An3          | 3         | ASCII       | "061"                                                        |
| Cantidad de Sub-Campos      | N4           | 4         | ASCII       | "0002"                                                       |
| Longitud Sub-Campo          | N3           | 3         | ASCII       | "006"                                                        |
| Identificador del Sub-Campo | An3          | 3         | ASCII       | "155"                                                        |
| Dato del Sub-Campo          | An3          | 3         | ASCII       | Identificador "Sin control". Valor a informar: **"SCT"**     |
| Longitud Sub-Campo          | N3           | 3         | ASCII       | "015"                                                        |
| Identificador del Sub-Campo | An3          | 3         | ASCII       | "156"                                                        |
| Dato del Sub-Campo          | An12         | 12        | ASCII       | IP de origen (sin puntos, completo con blancos a la derecha) |

# Especificaciones de Producto 083 (Operatoria QR)

En caso de que el Sistema Propio incorpore la operatoria de pago con lectura de **QR**, se deben tener en cuenta las siguientes consideraciones técnicas para el cierre de lote.

## 1. Cierre de Lote

Se debe incorporar el **campo ISO 59** con el producto **“083”**, independientemente de si se han realizado transacciones con esta modalidad durante el período del lote.

### Formato del campo ISO 59 (Envío)

| **Dato**               | **Atributo** | **Bytes** | **Formato** | **Comentarios**                      |
| ---------------------- | ------------ | --------- | ----------- | ------------------------------------ |
| Longitud Total         | N2           | 2         | BCD         |                                      |
| Tipos de Producto      | An3          | 3         | ASCII       | “083”                                |
| Cantidad de Sub-Campos | N4           | 4         | ASCII       | “0001”                               |
| Longitud Sub-Campo     | N3           | 3         | ASCII       | “004”                                |
| ID Sub-Campo           | An3          | 3         | ASCII       | “208”                                |
| Dato Sub-Campo         | An1          | 1         | ASCII       | Indicador de operatoria QR = **“Q”** |

---

## 2. Consideraciones de Consolidación

> **Importante:** Dado que comparten la misma terminal, las transacciones realizadas con QR **deben sumarse** en los consolidados (compras, anulaciones, devoluciones) junto al resto de las operaciones del mismo lote.

**Producto 083 – Marca QR**

## Descripción

### Sub-Campo 208

**Campo requerido para transacciones Visa y Mastercard**

Identifica la operatoria QR en la transacción y el indicador de transacciones QR en cierre de lotes.

***

### Sub-Campo 255

**Campo de uso exclusivo y requerido para transacciones Mastercard**

Para transacciones con tarjetas Mastercard, se adiciona este subproducto en el cual, en caso de conocerlo, los Comercios deberán enviar el subtipo de QR que está operando.

En caso de no conocer el subtipo de QR, el Comercio deberá informar el valor **`61`** (no enviar espacios).

> **Nota:**  
> Si la tarjeta/PAN que se cursa **no es de bandera Mastercard**, se deberá informar solamente el **producto 083** con el **sub-campo 208**.

***

## Estructura del Producto 083

| Dato                        | Atributo | Bytes | Formato | Comentarios                                                                  |
| --------------------------- | -------- | ----- | ------- | ---------------------------------------------------------------------------- |
| Longitud Total              | N3       | 2     | BCD     |                                                                              |
| Tipo de Producto            | An3      | 3     | ASCII   | Identifica el Tipo de Producto. En este caso es **“083”**                    |
| Cantidad de Sub-Campos      | N4       | 4     | ASCII   | Informa la cantidad de Sub-Campos que utiliza el Tipo de Producto (**0002**) |
| Longitud Sub-Campo          | N3       | 3     | ASCII   | Longitud del Sub-Campo (valor a informar **004**)                            |
| Identificador del Sub-Campo | An3      | 3     | ASCII   | Sub-Campo **“208”**                                                          |
| Dato del Sub-Campo          | An1      | 1     | ASCII   | Indicador operatoria QR = **‘Q’**                                            |
| Longitud Sub-Campo          | N3       | 3     | ASCII   | Longitud del Sub-Campo (valor a informar **005**)                            |
| Identificador del Sub-Campo | An3      | 3     | ASCII   | Sub-Campo **“255”**                                                          |
| Dato del Sub-Campo          | An1      | 1     | ASCII   | **XQR Subtype**<br>61 – QR Merchant presented<br>62 – QR Consumer presented  |

***

## Valores del Sub-Campo 255 (XQR Subtype)

* **61** – QR Merchant presented
* **62** – QR Consumer presented

> **Nota:**  
> En caso de no contar con la información del sub-campo **255**, se deberá informar el valor **61**.

***

## Ejemplos

### Visa

```text
0830001004208Q
```

### Mastercard

```text
0830002004208Q00525560
```

# Producto 085 – ID de Billetera

## Descripción

Permite identificar la **billetera digital** que está operando en la transacción.

El **sub-campo 210** es **obligatorio** y debe ser informado por el Comercio.

***

## Estructura del Producto 085

| Dato                        | Atributo | Bytes | Formato | Comentarios                                                                  |
| --------------------------- | -------- | ----- | ------- | ---------------------------------------------------------------------------- |
| Longitud Total              | N3       | 2     | BCD     |                                                                              |
| Tipo de Producto            | An3      | 3     | ASCII   | Identifica el Tipo de Producto. En este caso es **“085”**                    |
| Cantidad de Sub-Campos      | N4       | 4     | ASCII   | Informa la cantidad de Sub-Campos que utiliza el Tipo de Producto (**0001**) |
| Longitud Sub-Campo          | N3       | 3     | ASCII   | Longitud del Sub-Campo (valor a informar **004**)                            |
| Identificador del Sub-Campo | An3      | 3     | ASCII   | Sub-Campo **“210”**                                                          |
| Dato del Sub-Campo          | Ans1     | 1     | ASCII   | Identificador de Billetera                                                   |

***

## Sub-Campo Obligatorio

* **Campo:** P59.085.210
* **Nombre:** Wallet Identifier
* **Descripción:** Identificador de la billetera que interviene en la operación.
* **Responsable:** Debe ser informado por el **Comercio**.

> **Nota:**  
> La billetera es asignada por el equipo de **Online Payment**.

***

## Ejemplo

```
08500010042103
```

# Producto 106 – Debt Repayment

En este campo se deberá informar el indicador especial correspondiente a la operatoria **Debt repayment: `'9'`**

### Estructura

| Dato                   | Atributo | Bytes | Formato | Comentarios          |
| ---------------------- | -------- | ----- | ------- | -------------------- |
| Longitud total         | N3       | 2     | BCD     |                      |
| Tipo de producto       | An3      | 3     | ASCII   | Valor: `106`         |
| Cantidad de subcampos  | N4       | 4     | ASCII   | Valor: `0001`        |
| Longitud subcampo      | N3       | 3     | ASCII   | Valor: `004`         |
| Identificador subcampo | An3      | 3     | ASCII   | Valor: `253`         |
| Dato del subcampo      | An1      | 1     | ASCII   | `9 = Debt repayment` |

## 4. Configuración y Diferenciación de Respuestas en ISO 8583

Para diferenciar los distintos rechazos que pueden ocurrir en esta operatoria, se definió un nuevo código de respuesta asociado a una leyenda. Esto permite obtener más detalle sobre el motivo del rechazo en los mensajes **MTI 0210**.

## Campo ISO 39 - Código de respuesta

### Descripción

El **campo 39 del estándar ISO 8583** es un campo en formato ASCII que tiene la unción principal de proporcionar al comercio una respuesta relacionada con el resultado de una transacción. Su propósito es informar si la operación fue exitosa o, en caso contrario, detallar el motivo del rechazo o error.

### Atributos

- Largo fijo  
- Tipo: ASCII  
- Longitud: 2 posiciones  

### Valor

| Cod Rta | Descripción                     | Referencia                                    |
| ------- | ------------------------------- | --------------------------------------------- |
| H1      | Error Mensajería Debt repayment | Datos de la mensajería incompletos o erróneos |

## Campo ISO 63 – Leyenda asociada

### Descripción

El campo 63 en ISO 8583:

- Se transmite en **ASCII**  
- Su longitud se expresa en **BCD (Binary Coded Decimal)**  

### Atributos

- Longitud variable  
- Permite enviar información adicional o personalizada  
- La longitud real se define en el prefijo BCD  

### Reglas de visualización e impresión si está informado en el BitMap

#### 1. Si el primer carácter es `.`

- Mostrar en display  
- Imprimir en ticket  
- Máximo: 40 caracteres  

#### 2. Si el primer carácter es `,`

- No mostrar en display  
- Imprimir en ticket  
- Máximo: 200 caracteres  
- Reservar 5 líneas (32 columnas)

### Formato especial de impresión

- Usar el carácter especial | (ALT + 124) para indicar el fin de línea, continuando en el próximo renglón. No se debe dejar un espacio luego del carácter especial | (ALT + 124)  
- Usar el carácter especial ^ (ALT + 94) para indicar el fin del mensaje.  
- Las líneas impresas deben estar centradas. 
  Estos formatos de mensaje pueden enviarse en cualquier tipo de transacción  

Los mensajes de detalle se especifican en la sección de rechazos.

## 5. Rechazos

A continuación se detallan los controles aplicables a la operatoria:

| #   | Control                           | Campo 39 | Campo 63 – Leyenda                       |
| --- | --------------------------------- | -------- | ---------------------------------------- |
| 1   | MCC no elegible (≠ 6012/6051)     | H1       | `.Debt repayment solo rubros 6012 6051^` |
| 2   | No permite cashback               | H1       | `.Pago de deuda no admite cashback^`     |
| 3   | No admite preautorización         | H1       | `.Error mensajeria Debt repayment^`      |
| 4   | Producto crédito no permitido     | H1       | `.Debt repayment no admite credito^`     |
| 5   | 3 rechazos misma tarjeta/comercio | 57       | `.No reintentar por 14 días^`            |
| 6   | Rechazo Categoría 1               | 57       | `.No reintentar, use otra tarjeta^`      |

