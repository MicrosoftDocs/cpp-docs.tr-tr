---
title: "XFORM yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XFORM
dev_langs: C++
helpviewer_keywords: XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3c9e5978d82b1bbaed08eaa05dda53c78160579f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|**Ölçeklendirme**|Yatay ölçekleme bileşeni|Nothing|Nothing|Dikey ölçekleme bileşeni|  
|**Bükme**|Nothing|Yatay orantı sabiti|Dikey orantı sabiti|Nothing|  
|**Yansıma**|Yatay yansıma bileşeni|Nothing|Nothing|Dikey yansıma bileşeni|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

