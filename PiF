import socket
import subprocess
server_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
#UDP 1907 portu dinler
UDP_Port = 1907
server_socket.bind(('', UDP_Port))
#print "UDPServer 1907 dinleniyor"
while True:
        dataFromClient, address = server_socket.recvfrom(256)
        if dataFromClient == "haydut_rpi":
                p = subprocess.Popen(["hostname", "-I"], stdout=subprocess.PIPE)
                message, err = p.communicate()
                #print output
                server_socket.sendto("MyIpAdress: "+message, address)
                server_socket.close()
