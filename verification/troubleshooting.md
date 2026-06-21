# Troubleshooting rapido - IKEv2 Policy-Based

1. Si no aparece la SA IKEv2:
   - Verifica que R1 pueda hacer ping a la WAN de R2: 20.25.8.50.
   - Verifica que R2 pueda hacer ping a la WAN de R1: 20.25.8.46.
   - Revisa que la PSK sea igual en ambos routers.
   - Revisa el match identity remote address en el perfil IKEv2.

2. Si IKEv2 aparece READY pero no pasa trafico:
   - Genera trafico desde PC-A hacia PC-B.
   - Revisa show access-lists ACL-IKEV2-POLICY.
   - Revisa que las ACL esten invertidas correctamente en R1 y R2.
   - Revisa show crypto ipsec sa y confirma encaps/decaps.

3. Si los pings fallan al principio:
   - Es normal que el primer ping falle mientras se negocia el tunel.
   - Repite el ping y verifica los contadores IPSec.

4. Si el crypto map no trabaja:
   - Confirma que este aplicado en la interfaz WAN, no en la LAN.
   - En este laboratorio se aplica en GigabitEthernet0/0.
