---
title: "CD2DEllipse sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs: C++
helpviewer_keywords: CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 396d462b76b1aaa2fac5d0fdf2d0b89e581085e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dellipse-class"></a>CD2DEllipse sınıfı
İçin sarmalayıcı `D2D1_ELLIPSE`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Fazla Yüklendi. Oluşturan bir `CD2DEllipse` nesnesini `D2D1_ELLIPSE` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse  
 CD2DRectF nesnesinden CD2DEllipse nesnesi oluşturur.  
  
```  
CD2DEllipse(const CD2DRectF& rect);  
CD2DEllipse(const D2D1_ELLIPSE& ellipse);  
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

 
CD2DEllipse(
    const CD2DPointF& ptCenter,  
    const CD2DSizeF& sizeRadius);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Kaynak dikdörtgen  
  
 `ellipse`  
 Kaynak elips  
  
 `ptCenter`  
 Elips orta noktası.  
  
 `sizeRadius`  
 RADIUS X ve Y-radius elipsin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
