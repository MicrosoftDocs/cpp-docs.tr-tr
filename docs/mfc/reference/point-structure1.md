---
title: NOKTASI Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POINT
- LPPOINT
dev_langs: C++
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 708282417ae5d2a17b07bd5b7672ec3c00fe9f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="point-structure1"></a>NOKTASI Structure1
**Noktası** yapısını tanımlar x *-*  noktasının y koordinatları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagPOINT {  
    LONG x;  
    LONG y;  
} POINT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 Bir noktasının x koordinatını belirtir.  
  
 *y*  
 Bir noktasının y koordinatını belirtir.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** windef.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)
