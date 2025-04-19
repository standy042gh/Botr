import discord
intents = discord.Intents.default()

intents.message_content = True

client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print(f'Hemos iniciado sesión como {client.user}')

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
    else:
        await message.channel.send(message.content)
    
client.run("El token")
