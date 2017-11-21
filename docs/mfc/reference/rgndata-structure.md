---
title: "RGNDATA yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RGNDATA
dev_langs: C++
helpviewer_keywords: RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f637dfd76ba293454c7a5c51b12ad60926280a72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rgndata-structure"></a>RGNDATA Yapısı
`RGNDATA` Yapısı üstbilgi ve bir bölge oluşturma dikdörtgenler dizisi içerir. Bu dikdörtgenler soldan sağa sıralanmış yukarıdan çakışmaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *rdh*  
 Belirten bir [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) yapısı. (Bu yapısı hakkında daha fazla bilgi için Windows SDK'sı bakın.) Bu yapı üyeleri (dikdörtgen veya trapezoidal olup), bölge bölgesini, dikdörtgen yapıları içeren arabellek boyutu olun dikdörtgenler sayısı türünü belirtin ve benzeri.  
  
 `Buffer`  
 İçeren boyutu rasgele arabelleği belirtir [RECT](../../mfc/reference/rect-structure1.md) bölgesini olun yapıları.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

