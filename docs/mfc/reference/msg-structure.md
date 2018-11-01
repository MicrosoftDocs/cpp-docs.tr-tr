---
title: MSG Yapısı
ms.date: 11/04/2016
f1_keywords:
- MSG
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
ms.openlocfilehash: 1a953f8d0d685e25beedd2d401e227c934414208
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499821"
---
# <a name="msg-structure"></a>MSG Yapısı

`MSG` Yapısı, bir iş parçacığının ileti kuyruğundan ileti bilgileri içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagMSG {     // msg
    HWND hwnd;
    UINT message;
    WPARAM wParam;
    LPARAM lParam;
    DWORD time;
    POINT pt;
} MSG;
```

#### <a name="parameters"></a>Parametreler

*HWND*<br/>
Pencere yordamı olan iletiyi alır penceresi tanımlar.

*message*<br/>
İleti sayısını belirtir.

*wParam*<br/>
İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.

*lParam*<br/>
İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.

*saat*<br/>
Başlangıçtan iletinin gönderildiği saati belirtir.

*PT*<br/>
İletinin gönderildiği sırada ekran koordinatlarında imleç konumu belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

