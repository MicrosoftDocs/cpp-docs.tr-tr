---
title: "CD2DRectF sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs: C++
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b0919780e4fcad86772892bb0b300a735df81e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2drectf-class"></a>CD2DRectF sınıfı
İçin sarmalayıcı `D2D1_RECT_F`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|Fazla Yüklendi. Oluşturan bir `CD2DRectF` nesnesini `D2D1_RECT_F` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|Döndürür bir `boolean` bir ifade geçerli bir veri içerip içermediğini gösteren değeri ( `null`).|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|Dönüştürür `CD2DRectF` için `CRect` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
 CRect nesnesinden CD2DRectF nesnesi oluşturur.  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Kaynak dikdörtgen  
  
 `fLeft`  
 Kaynak sol koordinat  
  
 `fTop`  
 Kaynak üst koordinat  
  
 `fRight`  
 Kaynak sağ koordinat  
  
 `fBottom`  
 kaynak alt koordinat  
  
##  <a name="isnull"></a>CD2DRectF::IsNull  
 Bir ifade (boş) geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgenin üst, sol, alt ve sağ değerlerin 0 olarak tüm eşitse TRUE; Aksi takdirde FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectF::operator CRect  
 CD2DRectF CRect nesnesine dönüştürür.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D dikdörtgen geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
