---
title: SOCKADDR Yapısı
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
ms.openlocfilehash: 68d5261c6520b5baee8495b72a0b9d234a35a185
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543851"
---
# <a name="sockaddr-structure"></a>SOCKADDR Yapısı

`SOCKADDR` Yapısı Windows Sockets iletişime katılan bir makine için bir Internet Protokolü (IP) adresi depolamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
struct sockaddr {
    unsigned short sa_family;
    char sa_data[14];
};
```

#### <a name="parameters"></a>Parametreler

*sa_family*<br/>
Yuva Adres ailesi.

*sa_data*<br/>
Tüm farklı yuva adresi yapıları en büyük boyutu.

## <a name="remarks"></a>Açıklamalar

Microsoft TCP/IP yuva Geliştirme Seti, yalnızca Internet adresi etki alanlarını destekler. Aslında bir adresi her bir bölümü için değerleri doldurmak için kullandığınız `SOCKADDR_IN` özellikle bu adresi biçimi için olan veri yapısı. `SOCKADDR` Ve `SOCKADDR_IN` veri yapıları aynı boyutta olan. Yalnızca iki yapı türleri arasında geçiş yapmak için cast.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winsock2.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR_IN Yapısı](../../mfc/reference/sockaddr-in-structure.md)<br/>
[CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)<br/>
[CSocket::Create](../../mfc/reference/csocket-class.md#create)

