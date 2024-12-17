# NiteCtf 2024

## Hardware Challanges(1)

*U ARe T Detective*

	Description:-One of our Detective tapped a channel to intercept this signal but couldn't read it, HELP HIM

	Solution:- The given file was in format of .sr file. So I googled it and found some ways to analyze the file. First I tried to the sigrok command line tool to convert .sr file to .csv file . But i got a 1.8 gb file which had all the bits running through the pins. I also tried to analyze the file using the some python code from chatgpt.But didn't work.Before this i tried to analyze using salae software but it doesn't accept the format. Then I used pulseview which the signals in respective pins. After some googling , Came to know the decoders in that. After adding uart protocol , we used set rx and tx to pind to get the signals and decode. As there are some signals in D1 have set it ha tx and some pin as rx.

	But Here the baudrate doesn't match with the std rate, we have to find the rate using the intervels of one bits (i.e) 1/(bit-width) = baudrate. I used cursor to find the interval and freq.Then applied the rate to UART protocol.Also used a option called binary decoder output view, which showed the binary data transmited through tx (data bit).Then I got a ascii text which is the flag.

	
	**Flag** = nite{n0n_std_b4ud_r4t3s_ftw}

 
