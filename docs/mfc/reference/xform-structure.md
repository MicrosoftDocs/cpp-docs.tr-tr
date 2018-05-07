---
title: XFORM yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a1c3a8abd39f7f190f36a18e7691475d951cab8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="xform-structure"></a>XFORM Yapısı
`XFORM` Yapısı aşağıdaki biçime sahiptir:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `XFORM` Yapısı sayfa alanı dönüştürme alanına world belirtir. **EDx** ve **eDy** üyeleri yatay ve dikey çeviri bileşenleri sırasıyla belirtin. Aşağıdaki tabloda nasıl diğer üyeler, işlemine bağlı olarak kullanıldığı gösterilmektedir:  
  
|Çalışma|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Döndürme açısının kosinüsünü|Döndürme açısının sinüsünü|Negatif döndürme açısının sinüsünü|Döndürme açısının kosinüsünü|  
|**ölçeklendirme**|Yatay ölçekleme bileşeni|Nothing|Nothing|Dikey ölçekleme bileşeni|  
|**Bükme**|Nothing|Yatay orantı sabiti|Dikey orantı sabiti|Nothing|  
|**Yansıma**|Yatay yansıma bileşeni|Nothing|Nothing|Dikey yansıma bileşeni|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

