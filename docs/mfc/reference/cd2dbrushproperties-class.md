---
title: "CD2DBrushProperties sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs: C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9aeaa81a6f1192cb2d05ac37c56c95032fa4b398
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties sınıfı
İçin sarmalayıcı `D2D1_BRUSH_PROPERTIES`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Fazla Yüklendi. Oluşturur bir `CD2D_BRUSH_PROPERTIES` yapısı|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrushProperties::CommonInit](#commoninit)|Nesneyi başlatır|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_BRUSH_PROPERTIES`  
  
 `CD2DBrushProperties`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2dbrushproperties"></a>CD2DBrushProperties::CD2DBrushProperties  
 CD2D_BRUSH_PROPERTIES yapısı oluşturur  
  
```  
CD2DBrushProperties();  
CD2DBrushProperties(FLOAT _opacity);

 
CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,  
    FLOAT _opacity = 1.);
```  
  
### <a name="parameters"></a>Parametreler  
 `_opacity`  
 Fırça temel geçirgenliğini. 1.0 varsayılan değerdir.  
  
 `_transform`  
 Dönüştürme için fırça uygulamak için  
  
##  <a name="commoninit"></a>CD2DBrushProperties::CommonInit  
 Nesneyi başlatır  
  
```  
void CommonInit();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
