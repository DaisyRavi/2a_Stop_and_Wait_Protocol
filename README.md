# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

```
import time

def send_frame(frame):
    print(f"Sending frame: {frame}")
    time.sleep(1)  # Simulating transmission time
    return True

def receive_ack():
    time.sleep(1)  # Simulating transmission time
    return True

def stop_and_wait_protocol(frame_size):
    for frame_number in range(frame_size):
        frame = f"Frame {frame_number}"
        while not send_frame(frame):
            print("Timeout occurred. Resending frame.")
        print(f"Frame {frame_number} sent successfully.")

        ack_received = receive_ack()
        while not ack_received:
            print("Timeout occurred. Resending frame.")
            ack_received = receive_ack()

        print(f"Acknowledgment received for Frame {frame_number}.\n")

    print("Data transmission completed.")

if _name_ == "_main_":
    frame_size = int(input("Enter the frame size: "))
    stop_and_wait_protocol(frame_size)
```
## OUTPUT


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
