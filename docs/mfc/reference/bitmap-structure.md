---
title: BITMAP Yapısı
ms.date: 11/04/2016
f1_keywords:
- BITMAP
helpviewer_keywords:
- BITMAP structure [MFC]
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
ms.openlocfilehash: a9ffa7191b5f0e815db9c7e8b8a26b0b6b200f2d
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330248"
---
# <a name="bitmap-structure"></a>BITMAP Yapısı

**Bit eşlem** yapısı, yükseklik, genişlik, renk biçimi ve mantıksal bir bit eşlem bit değerleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagBITMAP {  /* bm */
    int bmType;
    int bmWidth;
    int bmHeight;
    int bmWidthBytes;
    BYTE bmPlanes;
    BYTE bmBitsPixel;
    LPVOID bmBits;
} BITMAP;
```

#### <a name="parameters"></a>Parametreler

*bmType*<br/>
Bit eşlem türünü belirtir. Bu üye, mantıksal bit eşlemler için 0 olmalıdır.

*bmWidth*<br/>
Bit eşlem genişliğini piksel cinsinden belirtir. Genişliği 0'dan büyük olmalıdır.

*bmHeight*<br/>
Izgara satır bit eşlem yüksekliğini belirtir. Yüksekliği 0'dan büyük olmalıdır.

*bmWidthBytes*<br/>
Her bir ızgara satırda bulunan bayt sayısını belirtir. Bu değer, grafik cihaz arabirimi (GDI) bit eşlem bit değerleri tamsayı (2 baytlık) değerler dizisi form varsaydığından bir çift sayı olmalıdır. Diğer bir deyişle, *bmWidthBytes* \* 8, 16 ne zaman elde değerine eşit veya değerinden sonraki katları olmalıdır *bmWidth* üye çarpılarak *bmBitsPixel*  üyesi.

*bmPlanes*<br/>
Renk düzlemi sayısı bit eşleminde belirtir.

*bmBitsPixel*<br/>
Bir pikselin tanımlamak için gerekli her gezmeyi bitişik renk bit sayısını belirtir.

*bmBits*<br/>
Bit eşlem bit değerleri konumunu işaret eder. *BmBits* üye 1-bayt değerleri dizisi uzun bir işaretçi olması gerekir.

## <a name="remarks"></a>Açıklamalar

Şu anda kullanılan bit eşlem biçimler şunlardır: tek renkli ve rengi. Bit eşlemi renkliye dönüştürmesi gerekirse bir 1 bit, 1-düzlemi biçimini kullanır. Her tarama 16 bit sayısının katı değil.

Taramaları gibi bir tek renkli yükseklik bit eşlem için düzenlenmiş *n*:

```
Scan 0
Scan 1
.
.
.
Scan n-2
Scan n-1
```

Her iki siyah pikseldir tek renkli bir cihazda veya beyaz. Karşılık gelen bit eşlemde 1 ise, piksel (beyaz) üzerinde etkinleştirilir. Karşılık gelen bit eşlemde 0 ise, piksel (siyah) devre dışı etkinleştirilir.

İçinde RASTERCAPS dizinini bit RC_BITBLT kümeniz bit eşlemler tüm cihazları destekleyin [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) üye işlevi.

Her bir cihaz kendi benzersiz renk biçimi vardır. Bir CİHAZDAN bir bit eşlem aktarmak için kullanılması [GetDIBits](/windows/desktop/api/wingdi/nf-wingdi-getdibits) ve [SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits) Windows işlevleri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
