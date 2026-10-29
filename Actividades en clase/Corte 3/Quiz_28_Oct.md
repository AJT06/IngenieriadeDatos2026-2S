show dbs

admin    40.00 KiB

config  108.00 KiB

local   104.00 KiB

use saborya

switched to db saborya

db

saborya

db.getName

\[Function: getName] {

&#x20; serverVersions: \[ '0.0.0', '999.999.999' ],

&#x20; apiVersions: \[ 0, Infinity ],

&#x20; topologies: \[ 'ReplSet', 'Standalone', 'Sharded', 'LoadBalanced' ],

&#x20; returnType: { type: 'unknown', attributes: {} },

&#x20; returnsPromise: false,

&#x20; deprecated: false,

&#x20; platforms: \[ 'Compass', 'Browser', 'CLI' ],

&#x20; isDirectShellCommand: false,

&#x20; acceptsRawInput: false,

&#x20; shellCommandCompleter: undefined,

&#x20; newShellCommandCompleter: undefined,

&#x20; help: \[Function (anonymous)] Help

}

show collections

db.getCollectionNames ()

\[]

db.createCollection ("Producto")

{ ok: 1 }

show collections

Producto

db.createCollection ("Clientes")

{ ok: 1 }

db.createCollection ("Restaurante")

{ ok: 1 }

show collections

Clientes

Producto

Restaurante

db.stats

\[Function: stats] AsyncFunction {

&#x20; apiVersions: \[ 0, 0 ],

&#x20; returnsPromise: true,

&#x20; serverVersions: \[ '0.0.0', '999.999.999' ],

&#x20; topologies: \[ 'ReplSet', 'Standalone', 'Sharded', 'LoadBalanced' ],

&#x20; returnType: { type: 'unknown', attributes: {} },

&#x20; deprecated: false,

&#x20; platforms: \[ 'Compass', 'Browser', 'CLI' ],

&#x20; isDirectShellCommand: false,

&#x20; acceptsRawInput: false,

&#x20; shellCommandCompleter: undefined,

&#x20; newShellCommandCompleter: undefined,

&#x20; help: \[Function (anonymous)] Help

}

db.stats ()

{

&#x20; db: 'saborya',

&#x20; collections: Long('3'),

&#x20; views: Long('0'),

&#x20; objects: Long('0'),

&#x20; avgObjSize: 0,

&#x20; dataSize: 0,

&#x20; storageSize: 12288,

&#x20; indexes: Long('3'),

&#x20; indexSize: 12288,

&#x20; totalSize: 24576,

&#x20; scaleFactor: Long('1'),

&#x20; fsUsedSize: 228215160832,

&#x20; fsTotalSize: 238675816448,

&#x20; ok: 1

}

db.c.countDocuments()

0

db.Restaurante.insert(\[\_id:"R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: {type: "Point", coordinates: \[-74.0636, 4.6486]}, etiquetas: \["arepas","desayunos", "económico"]])

SyntaxError: Unexpected token, expected "," (1:26)



> 1 | db.Restaurante.insert(\[\_id:"R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: {type: "Point", coordinates: \[-74.0636, 4.6486]}, etiquetas: \["arepas","desayunos", "económico"]])

&#x20;   |                           ^

db.Restaurante.insert(\_id:"R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: {type: "Point", coordinates: \[-74.0636, 4.6486]}, etiquetas: \["arepas","desayunos", "económico"])

SyntaxError: Unexpected token, expected "," (1:25)



> 1 | db.Restaurante.insert(\_id:"R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: {type: "Point", coordinates: \[-74.0636, 4.6486]}, etiquetas: \["arepas","desayunos", "económico"])

&#x20;   |                          ^

db.Restaurante.insert({ \_id: "R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.0636, 4.6486] }, etiquetas: \["arepas", "desayunos", "económico"] })

DeprecationWarning: Collection.insert() is deprecated. Use insertOne, insertMany, or bulkWrite.

{

&#x20; acknowledged: true,

&#x20; insertedIds: {

&#x20;   '0': 'R01'

&#x20; }

}

"Restaurantes: " + db.restaurantes.countDocuments()

Restaurantes: 0

db.restaurantes.insertMany(\[

&#x20; { \_id: "R01", nombre: "Arepas La 19", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "Chapinero", calificacion: 4.6, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.0636, 4.6486] }, etiquetas: \["arepas", "desayunos", "económico"] },

&#x20; { \_id: "R02", nombre: "Sushi Nikko", categoria: "Japonesa", ciudad: "Bogotá", barrio: "Usaquén", calificacion: 4.8, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.0305, 4.695] }, etiquetas: \["sushi", "ramen"], horario: { apertura: "12:00", cierre: "22:00" } },

&#x20; { \_id: "R03", nombre: "Pizzería Napoli", categoria: "Italiana", ciudad: "Bogotá", barrio: "Chicó", calificacion: 4.3, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.048, 4.676] }, etiquetas: \["pizza", "pasta"] },

&#x20; { \_id: "R04", nombre: "Burger Norte", categoria: "Hamburguesas", ciudad: "Bogotá", barrio: "Cedritos", calificacion: 3.9, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.04, 4.724] }, etiquetas: \["hamburguesas", "económico"] },

&#x20; { \_id: "R05", nombre: "Ajiaco \& Co", categoria: "Comida colombiana", ciudad: "Bogotá", barrio: "La Candelaria", calificacion: 4.5, domicilio: false, ubicacion: { type: "Point", coordinates: \[-74.0726, 4.5964] }, etiquetas: \["ajiaco", "almuerzos"] },

&#x20; { \_id: "R06", nombre: "Verde Vivo", categoria: "Vegetariana", ciudad: "Medellín", barrio: "El Poblado", calificacion: 4.4, domicilio: false, ubicacion: { type: "Point", coordinates: \[-75.5664, 6.2088] }, etiquetas: \["vegano", "saludable"], menu\_vegano: true },

&#x20; { \_id: "R07", nombre: "Bandeja Paisa Doña Rosa", categoria: "Comida colombiana", ciudad: "Medellín", barrio: "Laureles", calificacion: 4.7, domicilio: true, ubicacion: { type: "Point", coordinates: \[-75.59, 6.245] }, etiquetas: \["bandeja paisa", "almuerzos"] },

&#x20; { \_id: "R08", nombre: "Taco Loco", categoria: "Mexicana", ciudad: "Medellín", barrio: "Envigado", calificacion: 4.1, domicilio: true, ubicacion: { type: "Point", coordinates: \[-75.588, 6.171] }, etiquetas: \["tacos", "picante"] },

&#x20; { \_id: "R09", nombre: "Brasa Caribe", categoria: "Asados", ciudad: "Barranquilla", barrio: "El Prado", calificacion: 4.2, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.7964, 10.9878] }, etiquetas: \["asados", "parrilla"] },

&#x20; { \_id: "R10", nombre: "Mar y Coco", categoria: "Mariscos", ciudad: "Barranquilla", barrio: "Riomar", calificacion: 4.6, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.812, 11.015] }, etiquetas: \["mariscos", "pescado"] }

])



db.clientes.insertMany(\[

&#x20; { \_id: "C01", nombre: "Laura Gómez", email: "laura.gomez@example.com", ciudad: "Bogotá", fecha\_registro: new Date("2026-08-14"), puntos: 120, direcciones: \[{ alias: "Casa", direccion: "Calle 72 # 10-34", barrio: "Chapinero" }], preferencias: \["japonesa", "colombiana"] },

&#x20; { \_id: "C02", nombre: "Andrés Rojas", email: "andres.rojas@example.com", ciudad: "Bogotá", fecha\_registro: new Date("2025-11-02"), puntos: 340, direcciones: \[{ alias: "Casa", direccion: "Carrera 15 # 93-20", barrio: "Chicó" }, { alias: "Oficina", direccion: "Calle 26 # 69-76", barrio: "Salitre" }], preferencias: \["colombiana", "italiana"] },

&#x20; { \_id: "C03", nombre: "Valentina Ríos", email: "valentina.rios@example.com", ciudad: "Bogotá", fecha\_registro: new Date("2026-03-21"), puntos: 50, direcciones: \[{ alias: "Apartamento", direccion: "Calle 140 # 11-45", barrio: "Cedritos" }], preferencias: \["hamburguesas"] },

&#x20; { \_id: "C04", nombre: "Camilo Torres", email: "camilo.torres@example.com", ciudad: "Medellín", fecha\_registro: new Date("2025-06-10"), puntos: 410, direcciones: \[{ alias: "Casa", direccion: "Carrera 70 # 44-12", barrio: "Laureles" }], preferencias: \["colombiana", "mexicana"] },

&#x20; { \_id: "C05", nombre: "Mariana López", email: "mariana.lopez@example.com", ciudad: "Medellín", fecha\_registro: new Date("2026-09-30"), puntos: 0, direcciones: \[{ alias: "Casa", direccion: "Calle 10 # 43-15", barrio: "El Poblado" }], preferencias: \["vegetariana"] },

&#x20; { \_id: "C06", nombre: "Santiago Pérez", email: "santiago.perez@example.com", ciudad: "Barranquilla", fecha\_registro: new Date("2026-01-15"), puntos: 200, direcciones: \[{ alias: "Casa", direccion: "Carrera 54 # 72-80", barrio: "El Prado" }], preferencias: \["asados", "mariscos"] },

&#x20; { \_id: "C07", nombre: "Daniela Martínez", email: "daniela.martinez@example.com", ciudad: "Barranquilla", fecha\_registro: new Date("2026-07-07"), puntos: 80, direcciones: \[{ alias: "Apartamento", direccion: "Calle 98 # 52-115", barrio: "Riomar" }], preferencias: \["mariscos"] },

&#x20; { \_id: "C08", nombre: "Julián Castro", email: "julian.castro@example.com", ciudad: "Bogotá", fecha\_registro: new Date("2024-12-01"), puntos: 600, direcciones: \[{ alias: "Casa", direccion: "Calle 85 # 12-30", barrio: "Chicó" }], preferencias: \["japonesa", "italiana", "hamburguesas"] }

])



db.productos.insertMany(\[

&#x20; { \_id: "P01", restaurante\_id: "R01", nombre: "Arepa de choclo con queso", tipo: "plato", precio: 9500, stock: 40, disponible: true, descripcion: "Arepa dulce de maíz tierno con queso campesino derretido" },

&#x20; { \_id: "P02", restaurante\_id: "R01", nombre: "Arepa rellena de carne", tipo: "plato", precio: 14000, stock: 25, disponible: true, descripcion: "Arepa asada rellena de carne desmechada y hogao" },

&#x20; { \_id: "P03", restaurante\_id: "R01", nombre: "Jugo de lulo", tipo: "bebida", precio: 6000, stock: 60, disponible: true, descripcion: "Jugo natural de lulo en agua", volumen\_ml: 400 },

&#x20; { \_id: "P04", restaurante\_id: "R02", nombre: "Combo Sake", tipo: "plato", precio: 41000, stock: 15, disponible: true, descripcion: "Selección de rollos de salmón con salsa de la casa", piezas: 18 },

&#x20; { \_id: "P05", restaurante\_id: "R02", nombre: "Ramen tonkotsu", tipo: "plato", precio: 36000, stock: 20, disponible: true, descripcion: "Caldo de cerdo, fideos, huevo marinado y cebollín" },

&#x20; { \_id: "P06", restaurante\_id: "R02", nombre: "Té verde", tipo: "bebida", precio: 7000, stock: 50, disponible: true, descripcion: "Té verde japonés caliente", volumen\_ml: 300 },

&#x20; { \_id: "P07", restaurante\_id: "R03", nombre: "Pizza hawaiana mediana", tipo: "plato", precio: 32000, stock: 30, disponible: true, descripcion: "Pizza de jamón, piña y queso mozzarella", tamano: "mediana", masa: "delgada" },

&#x20; { \_id: "P08", restaurante\_id: "R03", nombre: "Pizza margarita grande", tipo: "plato", precio: 38000, stock: 25, disponible: true, descripcion: "Pizza de tomate, albahaca y queso mozzarella", tamano: "grande", masa: "tradicional" },

&#x20; { \_id: "P09", restaurante\_id: "R03", nombre: "Lasaña boloñesa", tipo: "plato", precio: 29000, stock: 0, disponible: false, descripcion: "Lasaña de carne gratinada con queso" },

&#x20; { \_id: "P10", restaurante\_id: "R04", nombre: "Hamburguesa clásica", tipo: "plato", precio: 22000, stock: 45, disponible: true, descripcion: "Carne de res, queso cheddar, lechuga y tomate" },

&#x20; { \_id: "P11", restaurante\_id: "R04", nombre: "Papas a la francesa", tipo: "acompañamiento", precio: 8000, stock: 80, disponible: true, descripcion: "Papas fritas crocantes con sal marina" },

&#x20; { \_id: "P12", restaurante\_id: "R05", nombre: "Ajiaco santafereño", tipo: "plato", precio: 28000, stock: 35, disponible: true, descripcion: "Sopa de tres papas con pollo, guascas, crema y alcaparras" },

&#x20; { \_id: "P13", restaurante\_id: "R05", nombre: "Chocolate con queso", tipo: "bebida", precio: 9000, stock: 40, disponible: true, descripcion: "Chocolate caliente con queso y almojábana", volumen\_ml: 350 },

&#x20; { \_id: "P14", restaurante\_id: "R06", nombre: "Bowl de quinua", tipo: "plato", precio: 26000, stock: 20, disponible: true, descripcion: "Quinua, aguacate, garbanzos y vegetales asados" },

&#x20; { \_id: "P15", restaurante\_id: "R06", nombre: "Hamburguesa de lentejas", tipo: "plato", precio: 24000, stock: 18, disponible: true, descripcion: "Hamburguesa vegana de lentejas con pan integral" },

&#x20; { \_id: "P16", restaurante\_id: "R07", nombre: "Bandeja paisa", tipo: "plato", precio: 34000, stock: 30, disponible: true, descripcion: "Fríjoles, arroz, chicharrón, huevo, carne molida, maduro y arepa" },

&#x20; { \_id: "P17", restaurante\_id: "R07", nombre: "Arepa con hogao", tipo: "acompañamiento", precio: 8000, stock: 50, disponible: true, descripcion: "Arepa paisa con hogao casero" },

&#x20; { \_id: "P18", restaurante\_id: "R08", nombre: "Tacos al pastor x3", tipo: "plato", precio: 21000, stock: 40, disponible: true, descripcion: "Tres tacos de cerdo al pastor con piña y salsa picante" },

&#x20; { \_id: "P19", restaurante\_id: "R08", nombre: "Burrito de pollo", tipo: "plato", precio: 25000, stock: 22, disponible: true, descripcion: "Burrito de pollo con fríjoles, queso y guacamole" },

&#x20; { \_id: "P20", restaurante\_id: "R09", nombre: "Picada para dos", tipo: "plato", precio: 58000, stock: 12, disponible: true, descripcion: "Carne, chorizo, butifarra, yuca y bollo" },

&#x20; { \_id: "P21", restaurante\_id: "R09", nombre: "Costillas BBQ", tipo: "plato", precio: 45000, stock: 15, disponible: true, descripcion: "Costillas de cerdo a la parrilla con salsa BBQ" },

&#x20; { \_id: "P22", restaurante\_id: "R10", nombre: "Cazuela de mariscos", tipo: "plato", precio: 52000, stock: 10, disponible: true, descripcion: "Mariscos en salsa de coco con arroz blanco" },

&#x20; { \_id: "P23", restaurante\_id: "R10", nombre: "Arroz con coco y pescado", tipo: "plato", precio: 39000, stock: 14, disponible: true, descripcion: "Pescado frito con arroz con coco y patacón" },

&#x20; { \_id: "P24", restaurante\_id: "R10", nombre: "Limonada de coco", tipo: "bebida", precio: 9000, stock: 30, disponible: true, descripcion: "Limonada cremosa de coco", volumen\_ml: 400 }

])



db.pedidos.insertMany(\[

&#x20; { \_id: "PD001", cliente: { id: "C01", nombre: "Laura Gómez" }, restaurante: { id: "R02", nombre: "Sushi Nikko", ciudad: "Bogotá" }, fecha: new Date("2026-10-01T19:30:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P04", nombre: "Combo Sake", precio: 41000, cantidad: 1 }, { producto\_id: "P06", nombre: "Té verde", precio: 7000, cantidad: 2 }], total: 55000 },

&#x20; { \_id: "PD002", cliente: { id: "C02", nombre: "Andrés Rojas" }, restaurante: { id: "R01", nombre: "Arepas La 19", ciudad: "Bogotá" }, fecha: new Date("2026-10-01T08:15:00-05:00"), estado: "entregado", metodo\_pago: "efectivo", items: \[{ producto\_id: "P01", nombre: "Arepa de choclo con queso", precio: 9500, cantidad: 2 }, { producto\_id: "P03", nombre: "Jugo de lulo", precio: 6000, cantidad: 1 }], total: 25000 },

&#x20; { \_id: "PD003", cliente: { id: "C08", nombre: "Julián Castro" }, restaurante: { id: "R03", nombre: "Pizzería Napoli", ciudad: "Bogotá" }, fecha: new Date("2026-10-02T20:10:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P07", nombre: "Pizza hawaiana mediana", precio: 32000, cantidad: 1 }, { producto\_id: "P08", nombre: "Pizza margarita grande", precio: 38000, cantidad: 1 }], total: 70000 },

&#x20; { \_id: "PD004", cliente: { id: "C03", nombre: "Valentina Ríos" }, restaurante: { id: "R04", nombre: "Burger Norte", ciudad: "Bogotá" }, fecha: new Date("2026-10-03T13:05:00-05:00"), estado: "cancelado", metodo\_pago: "nequi", items: \[{ producto\_id: "P10", nombre: "Hamburguesa clásica", precio: 22000, cantidad: 2 }, { producto\_id: "P11", nombre: "Papas a la francesa", precio: 8000, cantidad: 2 }], total: 60000 },

&#x20; { \_id: "PD005", cliente: { id: "C04", nombre: "Camilo Torres" }, restaurante: { id: "R07", nombre: "Bandeja Paisa Doña Rosa", ciudad: "Medellín" }, fecha: new Date("2026-10-03T12:40:00-05:00"), estado: "entregado", metodo\_pago: "efectivo", items: \[{ producto\_id: "P16", nombre: "Bandeja paisa", precio: 34000, cantidad: 2 }, { producto\_id: "P17", nombre: "Arepa con hogao", precio: 8000, cantidad: 1 }], total: 76000 },

&#x20; { \_id: "PD006", cliente: { id: "C05", nombre: "Mariana López" }, restaurante: { id: "R06", nombre: "Verde Vivo", ciudad: "Medellín" }, fecha: new Date("2026-10-04T19:00:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P14", nombre: "Bowl de quinua", precio: 26000, cantidad: 1 }, { producto\_id: "P15", nombre: "Hamburguesa de lentejas", precio: 24000, cantidad: 1 }], total: 50000 },

&#x20; { \_id: "PD007", cliente: { id: "C06", nombre: "Santiago Pérez" }, restaurante: { id: "R09", nombre: "Brasa Caribe", ciudad: "Barranquilla" }, fecha: new Date("2026-10-05T21:15:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P20", nombre: "Picada para dos", precio: 58000, cantidad: 1 }], total: 58000 },

&#x20; { \_id: "PD008", cliente: { id: "C07", nombre: "Daniela Martínez" }, restaurante: { id: "R10", nombre: "Mar y Coco", ciudad: "Barranquilla" }, fecha: new Date("2026-10-05T13:30:00-05:00"), estado: "entregado", metodo\_pago: "nequi", items: \[{ producto\_id: "P22", nombre: "Cazuela de mariscos", precio: 52000, cantidad: 1 }, { producto\_id: "P24", nombre: "Limonada de coco", precio: 9000, cantidad: 2 }], total: 70000 },

&#x20; { \_id: "PD009", cliente: { id: "C01", nombre: "Laura Gómez" }, restaurante: { id: "R05", nombre: "Ajiaco \& Co", ciudad: "Bogotá" }, fecha: new Date("2026-10-06T12:20:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P12", nombre: "Ajiaco santafereño", precio: 28000, cantidad: 1 }, { producto\_id: "P13", nombre: "Chocolate con queso", precio: 9000, cantidad: 1 }], total: 37000 },

&#x20; { \_id: "PD010", cliente: { id: "C08", nombre: "Julián Castro" }, restaurante: { id: "R02", nombre: "Sushi Nikko", ciudad: "Bogotá" }, fecha: new Date("2026-10-07T20:45:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P05", nombre: "Ramen tonkotsu", precio: 36000, cantidad: 2 }], total: 72000 },

&#x20; { \_id: "PD011", cliente: { id: "C02", nombre: "Andrés Rojas" }, restaurante: { id: "R03", nombre: "Pizzería Napoli", ciudad: "Bogotá" }, fecha: new Date("2026-10-08T19:50:00-05:00"), estado: "cancelado", metodo\_pago: "efectivo", items: \[{ producto\_id: "P07", nombre: "Pizza hawaiana mediana", precio: 32000, cantidad: 2 }], total: 64000 },

&#x20; { \_id: "PD012", cliente: { id: "C04", nombre: "Camilo Torres" }, restaurante: { id: "R08", nombre: "Taco Loco", ciudad: "Medellín" }, fecha: new Date("2026-10-09T20:00:00-05:00"), estado: "entregado", metodo\_pago: "nequi", items: \[{ producto\_id: "P18", nombre: "Tacos al pastor x3", precio: 21000, cantidad: 2 }, { producto\_id: "P19", nombre: "Burrito de pollo", precio: 25000, cantidad: 1 }], total: 67000 },

&#x20; { \_id: "PD013", cliente: { id: "C06", nombre: "Santiago Pérez" }, restaurante: { id: "R10", nombre: "Mar y Coco", ciudad: "Barranquilla" }, fecha: new Date("2026-10-10T13:10:00-05:00"), estado: "entregado", metodo\_pago: "efectivo", items: \[{ producto\_id: "P23", nombre: "Arroz con coco y pescado", precio: 39000, cantidad: 2 }], total: 78000 },

&#x20; { \_id: "PD014", cliente: { id: "C03", nombre: "Valentina Ríos" }, restaurante: { id: "R01", nombre: "Arepas La 19", ciudad: "Bogotá" }, fecha: new Date("2026-10-11T09:00:00-05:00"), estado: "entregado", metodo\_pago: "nequi", items: \[{ producto\_id: "P02", nombre: "Arepa rellena de carne", precio: 14000, cantidad: 1 }, { producto\_id: "P03", nombre: "Jugo de lulo", precio: 6000, cantidad: 2 }], total: 26000 },

&#x20; { \_id: "PD015", cliente: { id: "C08", nombre: "Julián Castro" }, restaurante: { id: "R04", nombre: "Burger Norte", ciudad: "Bogotá" }, fecha: new Date("2026-10-12T18:30:00-05:00"), estado: "en\_camino", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P10", nombre: "Hamburguesa clásica", precio: 22000, cantidad: 1 }, { producto\_id: "P11", nombre: "Papas a la francesa", precio: 8000, cantidad: 1 }], total: 30000 },

&#x20; { \_id: "PD016", cliente: { id: "C05", nombre: "Mariana López" }, restaurante: { id: "R07", nombre: "Bandeja Paisa Doña Rosa", ciudad: "Medellín" }, fecha: new Date("2026-10-12T13:00:00-05:00"), estado: "pendiente", metodo\_pago: "efectivo", items: \[{ producto\_id: "P16", nombre: "Bandeja paisa", precio: 34000, cantidad: 1 }], total: 34000 },

&#x20; { \_id: "PD017", cliente: { id: "C01", nombre: "Laura Gómez" }, restaurante: { id: "R02", nombre: "Sushi Nikko", ciudad: "Bogotá" }, fecha: new Date("2026-10-13T20:20:00-05:00"), estado: "en\_camino", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P04", nombre: "Combo Sake", precio: 41000, cantidad: 2 }], total: 82000 },

&#x20; { \_id: "PD018", cliente: { id: "C07", nombre: "Daniela Martínez" }, restaurante: { id: "R09", nombre: "Brasa Caribe", ciudad: "Barranquilla" }, fecha: new Date("2026-10-13T21:00:00-05:00"), estado: "pendiente", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P21", nombre: "Costillas BBQ", precio: 45000, cantidad: 1 }, { producto\_id: "P20", nombre: "Picada para dos", precio: 58000, cantidad: 1 }], total: 103000 },

&#x20; { \_id: "PD019", cliente: { id: "C02", nombre: "Andrés Rojas" }, restaurante: { id: "R05", nombre: "Ajiaco \& Co", ciudad: "Bogotá" }, fecha: new Date("2026-10-14T12:45:00-05:00"), estado: "entregado", metodo\_pago: "tarjeta", items: \[{ producto\_id: "P12", nombre: "Ajiaco santafereño", precio: 28000, cantidad: 2 }], total: 56000 },

&#x20; { \_id: "PD020", cliente: { id: "C04", nombre: "Camilo Torres" }, restaurante: { id: "R06", nombre: "Verde Vivo", ciudad: "Medellín" }, fecha: new Date("2026-10-14T19:10:00-05:00"), estado: "cancelado", metodo\_pago: "nequi", items: \[{ producto\_id: "P15", nombre: "Hamburguesa de lentejas", precio: 24000, cantidad: 2 }], total: 48000 }

])

{

&#x20; acknowledged: true,

&#x20; insertedIds: {

&#x20;   '0': 'PD001',

&#x20;   '1': 'PD002',

&#x20;   '2': 'PD003',

&#x20;   '3': 'PD004',

&#x20;   '4': 'PD005',

&#x20;   '5': 'PD006',

&#x20;   '6': 'PD007',

&#x20;   '7': 'PD008',

&#x20;   '8': 'PD009',

&#x20;   '9': 'PD010',

&#x20;   '10': 'PD011',

&#x20;   '11': 'PD012',

&#x20;   '12': 'PD013',

&#x20;   '13': 'PD014',

&#x20;   '14': 'PD015',

&#x20;   '15': 'PD016',

&#x20;   '16': 'PD017',

&#x20;   '17': 'PD018',

&#x20;   '18': 'PD019',

&#x20;   '19': 'PD020'

&#x20; }

}

print("Restaurantes: " + db.restaurantes.countDocuments())

Restaurantes: 10

db.Restaurante.insertone({ \_id: "R011", nombre: "Dulce Tentación", categoria: "Postres", ciudad: "Bogotá", barrio: "Teusaquillo", calificacion: 4.8, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.0386, 4.6556] }, etiquetas: \["Pasteles", "Postres"] })

TypeError: db.Restaurante.insertone is not a function

db.restaurantes.insertOne({ \_id: "R011", nombre: "Dulce Tentación", categoria: "Postres", ciudad: "Bogotá", barrio: "Teusaquillo", calificacion: 4.8, domicilio: true, ubicacion: { type: "Point", coordinates: \[-74.0386, 4.6556] }, etiquetas: \["Pasteles", "Postres"] })



