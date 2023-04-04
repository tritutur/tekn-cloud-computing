#### MININET
###### Interact with Hosts and Switches
Start a minimal topology and enter the CLI:</br>
<blockquote>$ sudo mn</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-1.PNG"/></br>

Display nodes:</br>
<blockquote>mininet> nodes</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-2.PNG"/></br>

Display links:</br>
<blockquote>mininet> net</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-3.PNG"/></br>

Dump information about all nodes:</br>
<blockquote>mininet> dump</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-4.PNG"/></br>

Check config on h1 :</br>
<blockquote>h1 ifconfig -a</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-5.PNG"/></br>

**Test Connectivity beetween hots**</br>
<blockquote>h1 ping -c 1 h2</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-6.PNG"/></br>

**Run a simple web server and client**</br>
<blockquote>mininet> h1 python -m http.server 80 &</br>
mininet> h2 wget -O - h1</br>
mininet> h1 kill %python</br>
mininet> py sys.version</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/mininet-7.PNG"/></br>


