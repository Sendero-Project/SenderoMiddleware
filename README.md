![Sendero](https://lh3.googleusercontent.com/1usi6Uqss_u8rz98wNi9nxY6eC0swEH_oGddW7ATQFhSnXgHneaS1YbZTeRaY-po0Emz-KzGBHk2n_sO6ebHwABeFKhafD9KGDRDy00f7dbxIKW90tbKyMBgluXa6ylG3HaW-BJGfcjv5HZdj7k6zIQ03_exI4GoJWq1dZysytKN7YMFb5lybqkN3Ghqsax8GRJV8xrZmwHFNt0KqsA8qeAkYTwGBtQnEN4RiDY7pXC6P8kW1xedU3LgcOU7Kw0zsTNKSVTdrZXg4HXzvZXcr1dF90ILqmBxTcakss8PT348oSHhKduW_2z7X0EAddVgpcgafcGURs795l5VR8rgf-0J7oiieVygI204_P1GBXX5avvmUfCi9_qb-0LnCw7U5J5DLP0sqmEavt8af5bId6OMeFaWWnnCuF7iUHnRmErj3mPjIhI3myo5W3uS_b290mrQj2Etr5_T41Vi3702lpOGbRb2Dg3PQPKd6N15So31PX44fwVu8iC1BYZlO4XhRfG845b7MupXQfoWiWeQN0seUeN8hchcGUjcSgA16KfAwdKcrMHD60G_LFK4EqhbV5a2dNEQ8hOOSWOJvuV_4m_fqshAePs=w330-h233-no)

Sendero Middleware
==================

This component (fully developed in Python3) is the man in the middle between [Sendero Server](https://github.com/Sendero-Project/SenderoServer) and Sendero Wireless controllers. It is responsible for the management of the wireless devices and the delivery of Sendero frame data to the them. It is also capable of generating its own color content.

To use Sendero Middleware with Sendero Server, it must be configured as a `Device` in Sendero Server's configuration file. 

It offers the following **execution modes**:

- `devserver`:    Starts a straming session with device management.
                  Allows an extra parameter to send a simulated streaming among `sin` | `flash` | `artnet`.


- `prodserver`:   Starts a streaming session with device management, control and keep-alive servers.
                  Allows an extra parameter to send a simulated streaming.

Stream modes (**extra params**):

- `sin`:          Streams a sin-controlled lighting pattern.

- `flash`:        Streams a flash pattern in broadcast mode.

- `artnet`:       Receives, adapts and redirects ArtNet packets.


                
Modules
-------

- `config`: Stores all the configurable settings.

- `streaming`: Module responsible of the translation and redirection of Art-Net packets.

- `utils`: A set of utilitary methods for the whole app.

- `devices`: Device manager, is responsible for all the actions related to a wireless device. 
(Registering, Controlling, etc...)

- `networking`: Used to manage multicast networking.
              For artworks containing a lot of pixels, the size of the packet can be divided using mutliple multicast groups. 

Settings
--------

All configurations are commented in the `config.py` module. 


Invocation
---------- 
```
python3 middleware.py < execution mode > [extra params]
```

-------------

For more information about Sendero Project go to the [base repository](https://github.com/Sendero-Project/Sendero).

