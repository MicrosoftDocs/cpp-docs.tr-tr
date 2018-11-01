---
title: SOCKADDR_IN Yapısı
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR_IN
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
ms.openlocfilehash: 22d02b2e3c6fd7151e59cad0f3233539c04a16e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431232"
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN Yapısı

Internet adresi ailesinde `SOCKADDR_IN` yapısı Windows Sockets tarafından bir yuva bağlantı kurmak için bir yerel veya uzak bitiş noktası adresini belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
struct sockaddr_in{
    short sin_family;
    unsigned short sin_port;
struct in_addr sin_addr;
    char sin_zero[8];
};
```

#### <a name="parameters"></a>Parametreler

*sin_family*<br/>
Adres ailesi (af_ınet olmalıdır).

*sin_port*<br/>
IP bağlantı noktası.

*sin_addr*<br/>
IP adresi.

*sin_zero*<br/>
Yapı aynı boyuta getirmek için doldurma `SOCKADDR`.

## <a name="remarks"></a>Açıklamalar

Bu formu şöyledir `SOCKADDR` Internet adresi ailesine özgü yapısı ve atanabilecek `SOCKADDR`.

Bu yapının IP adresi bileşeni türüdür `IN_ADDR`. `IN_ADDR` Yapısı Windows Sockets üstbilgi dosyası WINSOCK tanımlanır. Aşağıdaki gibi H:

```
struct in_addr {
    union {
        struct {
            unsigned char s_b1, s_b2, s_b3, s_b4;
        } S_un_b;
        struct {
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;
};
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** winsock2.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR Yapısı](../../mfc/reference/sockaddr-structure.md)
