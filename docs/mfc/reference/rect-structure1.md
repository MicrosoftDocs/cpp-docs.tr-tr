---
title: RECT Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs: C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f4e56c78e717b24390a82e7cbb55670f36369044
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rect-structure1"></a>RECT Structure1
`RECT` Yapısı dikdörtgenin sol üst ve sağ alt köşe koordinatlarını tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>Üyeler  
 `left`  
 Dikdörtgene sol üst köşesindeki x koordinatını belirtir.  
  
 `top`  
 Dikdörtgene sol üst köşesindeki y koordinatını belirtir.  
  
 `right`  
 Sağ alt köşedeki dikdörtgenin x koordinatını belirtir.  
  
 `bottom`  
 Dikdörtgene sağ alt köşesindeki y koordinatını belirtir.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** windef.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)
