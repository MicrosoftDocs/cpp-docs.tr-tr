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
ms.openlocfilehash: 61b5f67247b556b37cdf934f94c30947675533e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="abc-structure"></a>ABC Yapısı
**ABC** yapısı Type yazı tipi karakter genişliğini içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *abcA*  
 Karakter A aralığını belirtir. Bir aralık uzaklığı karakter simgesi çizmeden önce geçerli konuma eklemek için ' dir.  
  
 *abcB*  
 Karakter B aralığını belirtir. B boşluk karakteri karakter çizilmiş kısmının genişliğini olabilir.  
  
 *abcC*  
 Karakter C aralığını belirtir. C aralığı uzaklığı boşluk karakteri karakter sağındaki sağlamak için geçerli konumu eklemek için ' dir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir karakterin toplam genişliğini A, B ve C alanları toplamı ' dir. A veya C alanı underhangs veya overhangs göstermek için negatif olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


