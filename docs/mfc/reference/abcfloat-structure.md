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
ms.openlocfilehash: 5be39336f3da839dc9b1c7be6a64db54b59f99bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="abcfloat-structure"></a>ABCFLOAT Yapısı
`ABCFLOAT` Yapısı bir yazı tipi karakteri A, B ve C genişliğini içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *abcfA*  
 Karakter A aralığını belirtir. Bir aralık uzaklığı karakter simgesi çizmeden önce geçerli konuma eklemek için ' dir.  
  
 *abcfB*  
 Karakter B aralığını belirtir. B boşluk karakteri karakter çizilmiş kısmının genişliğini olabilir.  
  
 *abcfC*  
 Karakter C aralığını belirtir. C aralığı uzaklığı boşluk karakteri karakter sağındaki sağlamak için geçerli konumu eklemek için ' dir.  
  
## <a name="remarks"></a>Açıklamalar  
 A, B ve C genişlikleri taban çizgisinin yazı tipi ölçülür. Bir karakterin karakter artırma (toplam genişlik) A, B ve C alanları toplamıdır. A veya C alanı underhangs veya overhangs göstermek için negatif olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

