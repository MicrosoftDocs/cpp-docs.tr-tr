---
title: "ABCFLOAT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABCFLOAT
dev_langs: C++
helpviewer_keywords: ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 983439d773a7ded59e09c1385bce4febc9979ef6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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

