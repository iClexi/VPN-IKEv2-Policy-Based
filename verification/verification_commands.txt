# Comandos de verificacion - VPN IPSec IKEv2 Policy-Based

# 1. Generar trafico interesante desde PC-A
ping 192.168.84.10

# 2. Verificar en R1
show crypto ikev2 sa
show crypto ipsec sa
show crypto session
show access-lists ACL-IKEV2-POLICY
show crypto map

# 3. Verificar en R2
show crypto ikev2 sa
show crypto ipsec sa
show crypto session
show access-lists ACL-IKEV2-POLICY
show crypto map

# Indicadores esperados:
# - show crypto ikev2 sa: estado READY.
# - show crypto ipsec sa: contadores encaps/encrypt/decaps/decrypt aumentando.
# - show crypto session: Session status UP-ACTIVE.
# - show access-lists: matches aumentando en la ACL de trafico interesante.
# - show crypto map: peer, transform-set, perfil IKEv2 e interfaz WAN correctos.
