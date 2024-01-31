# MD_SABBIR_AHMMED
Black_Python_Desktop_CMD





def handle(self,client,user):
    if self.args.execute:
        output=exececute(self.args.exececute)
        self.socket.send(output.encode())

    elif self.args.command:
        cmd_buffer=b''

        while True:
            try:
                client.send(b'BHP : ')
                while '\n' not in cmd_buffer.decode():
                    cmd_buffer+=client.recv(64)

                response=execute(cmd_buffer.decode())
                if response:
                    client.socket.send(response.encode())
                    cmd_buffer=b''
            except Exception as e:
                print(f'server killed {e}')
                self.close()
                sys.exit()

   MD SABBIR             
   Developer policy
   data policy