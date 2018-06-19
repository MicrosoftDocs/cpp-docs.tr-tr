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
ms.openlocfilehash: 591c2dd65fdb9dde00f0ac1373c39affbe82da85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373514"
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

