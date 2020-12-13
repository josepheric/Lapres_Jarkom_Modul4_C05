# Lapres Modul 4

Joseph Eric Amadeo S. / 05111840000077   
Feinard / 05111840000081

## VLSM Pada Cisco Packet Tracer

Gambar Pembagian Subnet  :
**![](https://lh4.googleusercontent.com/acdavSd2G7ZPeRaLu3TTnLu7atRTXcdwMEjvWkQLWKnO51O1ymamACNN34bU8YQWlhe2vrLgGH2aIB-DSbWIMu7dpWJGuLRTWfOW878Bx31riUmbM_VvegfLoU4JKOzP5cEad8OX)**  
Dari pembagian diatas, kami membuat tree berikut:   
**![](https://lh5.googleusercontent.com/tL3XKCdwFWADlFKhXOxPm6pKCAk7cjU0y0Y9Btt8rG6ZjO7dx2E55UzQxMScCfZASIyjMWJ2fKYtymeMrSojsSA1ScxYGukXPZjSKi55UDk05GyFYzeliqnZC6lFub9ZRG6u_msL)**  
 
Kami membagi jaringan menjadi 13 Subnet, berikut rinciannya:   

**![](https://lh6.googleusercontent.com/bbyoc84EmgFeaqVRSGb3o74t1nvXEkpZ9K-S-mbMsxWz_HM5AgPQYpxB5AVwKI0Ukmlv9cq4vnXl7VzsA-yqvDsB_EITZNYwBQ_-lTpYRp-kXn1Has0Iec4MwTZE0ZX_pdp5Jyks)**  

Setelah itu mengatur subnetting pada tiap device pada cisco sesuai pembagian IP. Untuk melihat pengaturan setiap device bisa dilihat di file pkt pada setiap device di bagian config->interfaces. Setelah itu menambahkan routing pada setiap router.  


Berikut file .pkt nya :  
[File .pkt](https://github.com/josepheric/Lapres_Jarkom_Modul4_C05/blob/main/files/Cisco%20VLSM.pkt)





## CIDR Pada UML
Gambar Pembagian Subnet:  
**![](https://lh6.googleusercontent.com/DuX5of8zOjSiKef6gAwUu1EtXjxKSyIo0w4T_IO294SW2BVNHwOSKyby3ywl9XVFVcAOh_nmFu7zCeITemUdAUmNlmGIZonZaGQSEzwsAfwkgdXWYAsmQwgLZVI_hyTdm7Zg3Z7e)**


Dari pembagian diatas, kami membuat tree berikut:   
**![](https://lh5.googleusercontent.com/8Xlrz-12jSMdS1DSt3pVw-q9XQ-ispgMeuXvUQ3h17Ki3o0uOIZPpTHGBBnYqPB9qocvEz-3aKhtCRH1DncQhIpNIpZbqkyp7xzgCiqkbgKXCMfwLNq9HfuWXKc3YhHXBCvKcrVY)**   



Rincian dari pembagian subnet :  

**![](https://lh6.googleusercontent.com/lrqP4l7Y4N7bhCwIvJ4hwEq-eH1phU7tCYQjNT2CCCJaCDLFtJoZtP2grUg0-K8Q1D3KyeU4zMTOMY5fJCSeYnE24b99MrziRPzPtDkwbToo4vw8QZx50t4rPST8IhWqN8iZOfK0)**
Setelah itu, kami membuat UML sesuai dengan rincian dari pembagian subnet yang sudah ada. Berikut **setting UML** nya:  
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
Untuk setiap router perlu mengatur sysctl dengan perintah nano /etc/sysctl.conf kemudian hilangkan tanda pagar (#) pada bagian net.ipv4.ip_forward=1  

Lalu ketikan sysctl -p untuk mengaktifkan perubahan.  

Untuk router surabaya perlu menjalankan iptables untuk bisa akses ke jaringan luar iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16  

**Setting Interface:**   
Router:
**![](https://lh3.googleusercontent.com/IdC2aTibzGrxd7-PwZsfBr3xW0_Uh6wjd1eYTlTXf9Is1UENSd6ptjjQ0njFx4nmq6LXjA5c4AdLbA4W3m2rhL7ONUukBWVrBMkLiid1AcuOfZmHbtPIX-K5Pyt3-Txn4RGK4gOw)**  
**![](https://lh4.googleusercontent.com/3aiAYt8RA_w0Hyw19zqsY-RHTc-tWunaY3d3id1uZarKb9Zq9ScloEirGqIxyh3Xf3YNo5lIpHt-_8t_tPTIwtepwm6V3luFMw8WqfYSzBaYA8GBEW_DhBTWAjeAuwhErXGzaRKs)**    
**![](https://lh4.googleusercontent.com/Hmq6PRzqy4Jh_SUXoOgobDTsyJEoSlQKlCKWOVk-vWhLLOjaYQwtWkz75fcLH47P0KwtJmk1j8tel4de1lye1OGCXRGjgJJ6NtPC7Ot6dlHnQqQggjmS9Buw2s3dBPWD07QC-BeN)**  
 **![](https://lh5.googleusercontent.com/rcfQsi3cDKJa0XkfjbB2w_A22V18PS4nQ-75Lnx8o4IAxxEwySvtVIQhBNp1ZKn0CA9fuqt5mzpDfK8Zi_B3WqvrMRSFhInpM0NrgPV6xWgmZlhvG8R9yAz6_HQUQC_uj7gXMCc6)** 
 Server:  
**![](https://lh6.googleusercontent.com/3kuu0mMM0WsCZeWjCULzc_myrLn_qxZTtCsrJ53AGqzO5-8mMPnStkEBf5U4LuaUoZvd-hKaNBPpT0jVqf9c3_FsCcdv7nuzEI2kHpT7-Elzjfc2Euudu9UzmWSYSFNC3dXNrKAz)**  
Client:  
**![](https://lh3.googleusercontent.com/p2cOEDQCNLp3JpLTe6fp1I5pLoFDS0CWQVGHvpUGFq3b9SgysXCTXYm9J6a4X_jLpPZYe-V5r7Q4Up046Hq-Jg3_PZRgfDfPX2NrEkcvIIChIeD6UGdSQzdb0OwaRKVFimyC2Etm)**  
**![](https://lh5.googleusercontent.com/XlCxCF9sYvVZC5IawN_3XtfWISW22cIcP7Eh6qe92J1EgGpj9L8j2s7Vw_aEGjsi5OQl7iYDOxt3VlkA7UyLvTyPh8FO-MOt5E7QmTJoLTZe0EFcTKOWAlguNYqJUmpb_Aqu0GYG)** 
**Memasang Routing**


Untuk routing dapat digunakan config route.sh untuk setiap router yang bersangkutan:
```
#Surabaya-00
route add -net 192.168.64.0 netmask 255.255.252.0 gw 192.168.64.2
route add -net 192.168.68.0 netmask 255.255.255.252 gw 192.168.68.2
route add -net 192.168.16.0 netmask 255.255.255.252 gw 192.168.68.2
route add -net 192.168.8.0 netmask 255.255.255.128 gw 192.168.68.2
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.68.2
route add -net 192.168.32.0 netmask 255.255.252.0 gw 192.168.68.2
route add -net 192.168.136.0 netmask 255.255.255.252 gw 192.168.136.2
route add -net 192.168.128.0 netmask 255.255.254.0 gw 192.168.136.2
route add -net 192.168.130.0 netmask 255.255.255.240 gw 192.168.136.2
route add -net 192.168.132.0 netmask 255.255.252.0 gw 192.168.136.2
route add -net 192.168.152.0 netmask 255.255.255.252 gw 192.168.136.2
route add -net 192.168.148.0 netmask 255.255.255.0 gw 192.168.136.2
route add -net 192.168.144.0 netmask 255.255.252.0 gw 192.168.136.2
route add -net 10.151.77.48 netmask 255.255.255.252 gw 192.168.136.2
route add -net 10.151.77.52 netmask 255.255.255.252 gw 10.151.77.54

#batu-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.136.1
route add -net 192.168.136.0 netmask 255.255.255.252 gw 192.168.136.1
route add -net 192.168.128.0 netmask 255.255.254.0 gw 192.168.128.2
route add -net 192.168.128.0 netmask 255.255.254.0 gw 192.168.128.3
route add -net 192.168.130.0 netmask 255.255.255.240 gw 192.168.128.2
route add -net 192.168.132.0 netmask 255.255.252.0 gw 192.168.132.2
route add -net 192.168.152.0 netmask 255.255.255.252 gw 192.168.152.2
route add -net 192.168.148.0 netmask 255.255.255.0 gw 192.168.152.2
route add -net 192.168.144.0 netmask 255.255.252.0 gw 192.168.152.2
route add -net 10.151.77.48 netmask 255.255.255.252 gw 192.168.152.2

#Kediri-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.152.1
route add -net 192.168.152.0 netmask 255.255.255.252 gw 192.168.152.1
route add -net 192.168.144.0 netmask 255.255.255.0 gw 192.168.148.2
route add -net 192.168.148.0 netmask 255.255.252.0 gw 192.168.148.2
route add -net 192.168.148.0 netmask 255.255.252.0 gw 192.168.148.3
route add -net 10.151.77.48 netmask 255.255.255.252 gw 10.151.77.50

#Blitar-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.148.1
route add -net 192.168.144.0 netmask 255.255.252.0 gw 192.168.144.2

#Madiun-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.128.1
route add -net 192.168.130.0 netmask 255.255.255.240 gw 192.168.130.2

#Pasuruan-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.68.1
route add -net 192.168.68.0 netmask 255.255.255.252 gw 192.168.68.1
route add -net 192.168.16.0 netmask 255.255.255.252 gw 192.168.16.2
route add -net 192.168.8.0 netmask 255.255.255.128 gw 192.168.16.2
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.16.2
route add -net 192.168.32.0 netmask 255.255.252.0 gw 192.168.32.2

#Probolingo-00
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.168.16.1
route add -net 192.168.8.0 netmask 255.255.255.128 gw 192.168.8.2
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.0.2
```
