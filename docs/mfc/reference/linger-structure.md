---
title: LINGER Yapısı
ms.date: 11/04/2016
f1_keywords:
- LINGER
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
ms.openlocfilehash: 78f1a5ce993373ea9e477262f0779515c52dbd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495324"
---
# <a name="linger-structure"></a>LINGER Yapısı

`LINGER` Yapısı SO_LINGER ve SO_DONTLINGER seçenekleri işlemek için kullanılan `CAsyncSocket::GetSockOpt`.

## <a name="syntax"></a>Sözdizimi

```
struct linger {
    u_short l_onoff;            // option on/off
    u_short l_linger;           // linger time
};
```

## <a name="remarks"></a>Açıklamalar

SO_DONTLINGER seçeneği ayarlama engeller üye işlevini engelleme `Close` gönderilecek gönderilmemiş verileri beklenirken. Bu ayar ile SO_LINGER ayarını eşdeğer `l_onoff` 0 olarak ayarlayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winsock2.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)<br/>
[CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

