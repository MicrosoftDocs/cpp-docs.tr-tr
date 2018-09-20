---
title: ABCFLOAT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABCFLOAT
dev_langs:
- C++
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9bbece0773c14a4a8b545bc56209bf682e22c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375422"
---
# <a name="abcfloat-structure"></a>ABCFLOAT Yapısı

`ABCFLOAT` Yapı A, B ve C genişlikleri yazı tipi karakterinin içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _ABCFLOAT { /* abcf */
    FLOAT abcfA;
    FLOAT abcfB;
    FLOAT abcfC;
} ABCFLOAT;
```

#### <a name="parameters"></a>Parametreler

*abcfA*<br/>
Karakteri bir boşluğu belirtir. Bir aralık uzaklığı için geçerli konumun karakter simgesi çizmeden önce ekleme ' dir.

*abcfB*<br/>
Karakter B aralığını belirtir. B boşluk karakteri glif çizilen kısmının genişliğidir.

*abcfC*<br/>
C karakter aralığını belirtir. C boşluk, boşluk karakteri glif sağındaki sağlamak için geçerli konumun eklemek için uzaklık olabilir.

## <a name="remarks"></a>Açıklamalar

A, B ve C genişlikleri yazı tipinin taban çizgisinin ölçülür. Bir karakterin karakter artırma (toplam genişlik) A, B ve C alanları toplamıdır. Bir ya da C alanı underhangs veya overhangs göstermek için negatif olabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

