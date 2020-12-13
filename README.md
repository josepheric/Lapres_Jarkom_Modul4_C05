### Lapres Modul 4
# Lapres Modul 4

Joseph Eric Amadeo S. / 05111840000077   
Feinard / 05111840000081

## VLSM Pada Cisco Packet Tracer

Gambar Pembagian Subnet  :
**![](https://lh4.googleusercontent.com/acdavSd2G7ZPeRaLu3TTnLu7atRTXcdwMEjvWkQLWKnO51O1ymamACNN34bU8YQWlhe2vrLgGH2aIB-DSbWIMu7dpWJGuLRTWfOW878Bx31riUmbM_VvegfLoU4JKOzP5cEad8OX)**  
Dari pembagian diatas, kami membuat tree berikut:   
**![](https://lh5.googleusercontent.com/8Xlrz-12jSMdS1DSt3pVw-q9XQ-ispgMeuXvUQ3h17Ki3o0uOIZPpTHGBBnYqPB9qocvEz-3aKhtCRH1DncQhIpNIpZbqkyp7xzgCiqkbgKXCMfwLNq9HfuWXKc3YhHXBCvKcrVY)**    
Kami membagi jaringan menjadi 13 Subnet, berikut rinciannya:   

**![](https://lh6.googleusercontent.com/bbyoc84EmgFeaqVRSGb3o74t1nvXEkpZ9K-S-mbMsxWz_HM5AgPQYpxB5AVwKI0Ukmlv9cq4vnXl7VzsA-yqvDsB_EITZNYwBQ_-lTpYRp-kXn1Has0Iec4MwTZE0ZX_pdp5Jyks)**  

Lalu kami membuat routing pada Cisco Packet Tracer sesuai dengan rincian dan tree tersebut. Berikut file .pkt nya :

Berikut screenshot dari Cisco Packet Tracer:



## CIDR Pada UML
Gambar Pembagian Subnet:


Dari pembagian diatas, kami membuat tree berikut:   
**![](https://lh4.googleusercontent.com/VmSljbrgNBieoO5y4_skfM-Xx387xqquWAauFP7ZR7afjlVi1JSPxvt6euxILj7OJFZqV0iRjgnnNTQyXBG1BO9Swsnhl5HzK4mc57WNe0As5KHZr4k4NgTTqIfGrRZXfC-bhMr1)**


Rincian dari pembagian subnet :  

**![](https://lh6.googleusercontent.com/lrqP4l7Y4N7bhCwIvJ4hwEq-eH1phU7tCYQjNT2CCCJaCDLFtJoZtP2grUg0-K8Q1D3KyeU4zMTOMY5fJCSeYnE24b99MrziRPzPtDkwbToo4vw8QZx50t4rPST8IhWqN8iZOfK0)**
Setelah itu, kami membuat UML sesuai dengan rincian dari pembagian subnet yang sudah ada. Berikut setting UML nya:  
```
# Switch

uml_switch -unix switch1 > /dev/null < /dev/null & 
uml_switch -unix switch2 > /dev/null < /dev/null & 
uml_switch -unix switch3 > /dev/null < /dev/null & 
uml_switch -unix switch7 > /dev/null < /dev/null & 
uml_switch -unix switch11 > /dev/null < /dev/null & 
uml_switch -unix switch13 > /dev/null < /dev/null & 
uml_switch -unix switch15 > /dev/null < /dev/null & 
uml_switch -unix switch16 > /dev/null < /dev/null & 
uml_switch -unix switch17 > /dev/null < /dev/null & 
uml_switch -unix switch18 > /dev/null < /dev/null & 
uml_switch -unix switch19 > /dev/null < /dev/null & 
uml_switch -unix switch21 > /dev/null < /dev/null & 
uml_switch -unix switch20 > /dev/null < /dev/null & 
uml_switch -unix switch22 > /dev/null < /dev/null & 
uml_switch -unix switch25 > /dev/null < /dev/null & 


# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.76.25 eth1=daemon,,,switch1 eth2=daemon,,,switch2 eth3=daemon,,,switch7 eth4=daemon,,,switch13 mem=64M &
xterm -T PASURUAN -e linux ubd0=PASURUAN,jarkom umid=PASURUAN eth0=daemon,,,switch2 eth1=daemon,,,switch3 eth2=daemon,,,switch19 mem=64M &
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch3 eth2=daemon,,,switch15 eth3=daemon,,,switch16 mem=64M &
xterm -T BATU -e linux ubd0=BATU,jarkom umid=BATU eth0=daemon,,,switch7 eth1=daemon,,,switch11 eth2=daemon,,,switch21 eth3=daemon,,,switch22 mem=64M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch22 eth1=daemon,,,switch25 mem=64M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid=KEDIRI eth0=daemon,,,switch11 eth1=daemon,,,switch17 eth2=daemon,,,switch18 mem=64M &
xterm -T BLITAR -e linux ubd0=BLITAR,jarkom umid=BLITAR eth0=daemon,,,switch17 eth1=daemon,,,switch20 mem=64M &


# Server

xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch18 mem=64M &
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch13 mem=64M &

# Klien 1
xterm -T SAMPANG -e linux ubd0=SAMPANG,jarkom umid=SAMPANG eth0=daemon,,,switch1 mem=64M &
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch19 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch16 mem=64M &
xterm -T JEMBER -e linux ubd0=JEMBER,jarkom umid=JEMBER eth0=daemon,,,switch16 mem=64M &
xterm -T BONDOWOSO -e linux ubd0=BONDOWOSO,jarkom umid=BONDOWOSO eth0=daemon,,,switch15 mem=64M &
xterm -T JOMBANG -e linux ubd0=JOMBANG,jarkom umid=JOMBANG eth0=daemon,,,switch22 mem=64M &
xterm -T BOJONEGORO -e linux ubd0=BOJONEGORO,jarkom umid=BOJONEGORO eth0=daemon,,,switch25 mem=64M &
xterm -T NGANJUK -e linux ubd0=NGANJUK,jarkom umid=NGANJUK eth0=daemon,,,switch21 mem=64M &
xterm -T LUMAJANG -e linux ubd0=LUMAJANG,jarkom umid=LUMAJANG eth0=daemon,,,switch17 mem=64M &
xterm -T TULUNGAGUNG -e linux ubd0=TULUNGAGUNG,jarkom umid=TULUNGAGUNG eth0=daemon,,,switch20 mem=64M &
```

Pembuatan topologi:    


Setting Interface:  
