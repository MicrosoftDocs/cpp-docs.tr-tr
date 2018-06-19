---
title: CD2DPointF sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a6439a25072975d28b98e4c6d88c3a1de8703d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348712"
---
# <a name="cd2dpointf-class"></a>CD2DPointF sınıfı
İçin sarmalayıcı `D2D1_POINT_2F`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Fazla Yüklendi. Oluşturan bir `CD2DPointF` nesnesini `D2D1_POINT_2F` nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|Dönüştürür `CD2DPointF` için `CPoint` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>  CD2DPointF::CD2DPointF  
 CPoint nesnesinden CD2DPointF nesnesi oluşturur.  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 Kaynak noktası  
  
 `fX`  
 Kaynak X  
  
 `fY`  
 Kaynak Y  
  
##  <a name="operator_cpoint"></a>  CD2DPointF::operator CPoint  
 CD2DPointF CPoint nesnesine dönüştürür.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D noktanın geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
