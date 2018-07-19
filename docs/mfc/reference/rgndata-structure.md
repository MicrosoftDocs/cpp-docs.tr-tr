---
title: RGNDATA yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b775b14cb2f6b0f87bca1c81938c1a4c05c1304
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335675"
---
# <a name="rgndata-structure"></a>RGNDATA Yapısı
`RGNDATA` Yapısı üstbilgi ve bölge oluşturma dikdörtgenler dizisi içerir. Bu dikdörtgenler, soldan sağa doğru sıralanmış yukarıdan çakışmaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *rdh*  
 Belirtir bir [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) yapısı. (Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.) Bu yapının üyeleri (dikdörtgen veya trapezoidal olup), bölge dikdörtgen yapıları içeren arabellek boyutu bölgeyi oluşturan dikdörtgenler sayısını türünü belirtin ve benzeri.  
  
 *Arabellek*  
 İçeren bir rastgele boyutlu bir arabellek belirtir [RECT](../../mfc/reference/rect-structure1.md) bölgeyi oluşturan yapılar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

