---
title: ABC yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a977e3f0efd763ee416348f11e3c6b016c0d42e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373718"
---
# <a name="abc-structure"></a>ABC Yapısı

`ABC` Yapı içeren bir karakter TrueType yazı tipi genişliği.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _ABC { /* abc */
    int abcA;
    UINT abcB;
    int abcC;
} ABC;
```

#### <a name="parameters"></a>Parametreler

*abcA*<br/>
Karakteri bir boşluğu belirtir. Bir aralık uzaklığı için geçerli konumun karakter simgesi çizmeden önce ekleme ' dir.

*abcB*<br/>
Karakter B aralığını belirtir. B boşluk karakteri glif çizilen kısmının genişliğidir.

*abcC*<br/>
C karakter aralığını belirtir. C boşluk, boşluk karakteri glif sağındaki sağlamak için geçerli konumun eklemek için uzaklık olabilir.

## <a name="remarks"></a>Açıklamalar

Bir karakterin toplam genişlik A, B ve C alanları toplamı ' dir. Bir ya da C alanı underhangs veya overhangs göstermek için negatif olabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


