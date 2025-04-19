import discord
import time
intents = discord.Intents.default()

intents.message_content = True

client = discord.Client(intents=intents)
, disminuyendo la contaminación y la liberación de gases de efecto invernadero, y conservando recursos naturales como la madera, el agua y los minerales. 
@client.event
async def on_ready():
    print(f'Hemos iniciado sesión como {client.user}')
    print(f'comandos:$hello, $Reciclar, $medio ambiente')
@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('$hello'):
        await message.channel.send("Hi!")
    elif message.content.startswith('$Reciclar'):
        await message.channel.send("Reciclar es importante porque asi evitamos le cambio climatico, preservamos el medio ambiente y Ahorramos energía\n")
        time.sleep(2)
        await message.channel.send("Puedes reciclar sin afectar a tu vida:\n")
        time.sleep(1)
        await message.channel.send("Usando productos reutilizables como organizadores de escritorio macetas y trapos de limpieza, o\n")
        time.sleep(2)
        await message.channel.send("reducir el uso de plastico y gasto de agua")
        await message.channel.send("Puedes usar tambien: "$medio ambiente"")
    elif message.content.startswith('$medio ambiente'):
        await message.channel.send("El medio ambiente es el entorno natural que rodea a los seres vivos\n")
        time.sleep(2)
        await message.channel.send("El reciclaje ayuda al medio ambiente al reducir la necesidad de extraer nuevas materias primas. \n")
        time.sleep(1)
        await message.channel.send("Esto disminuyendo la contaminación y la liberación de gases de efecto invernadero, y conservando recursos naturales como la madera, el agua y los minerales. ")
    else:
        await message.channel.send(message.content)
    
client.run("Token")
