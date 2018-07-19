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
ms.openlocfilehash: 2c9aac181edb12df8904a2bc6d891d59c0067ecc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339325"
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
 *abcA*  
 Karakteri bir boşluğu belirtir. Bir aralık uzaklığı için geçerli konumun karakter simgesi çizmeden önce ekleme ' dir.  
  
 *abcB*  
 Karakter B aralığını belirtir. B boşluk karakteri glif çizilen kısmının genişliğidir.  
  
 *abcC*  
 C karakter aralığını belirtir. C boşluk, boşluk karakteri glif sağındaki sağlamak için geçerli konumun eklemek için uzaklık olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir karakterin toplam genişlik A, B ve C alanları toplamı ' dir. Bir ya da C alanı underhangs veya overhangs göstermek için negatif olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


