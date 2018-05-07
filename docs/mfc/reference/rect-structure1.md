---
title: RECT Structure1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61c794b8fa383eeea62459a5a83948ef2efe10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
