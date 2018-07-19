---
title: CD2DRectF sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f96adf519eb710d412465a9db4cbd7313f91f41
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338278"
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
|[CD2DRectF::CD2DRectF](#cd2drectf)|Fazla Yüklendi. Oluşturur bir `CD2DRectF` nesnesinden `D2D1_RECT_F` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|Döndürür bir **Boole** bir ifade (NULL) geçerli olmayan veri içerip içermediğini gösteren bir değer.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|Dönüştürür `CD2DRectF` için `CRect` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF  
 CRect nesnesinden CD2DRectF bir nesne oluşturur.  
  
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
 *Rect*  
 Kaynak dikdörtgenin  
  
 *fLeft*  
 Kaynak sol koordinatı  
  
 *fTop*  
 Kaynak üst koordinat  
  
 *fRight*  
 Kaynak şu koordinat  
  
 *fBottom*  
 kaynak alt koordinat  
  
##  <a name="isnull"></a>  CD2DRectF::IsNull  
 Bir ifade (Null) geçerli olmayan veri içerip içermediğini gösteren bir Boole değeri döndürür.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgenin üst, sol, alt ve sağ değerlerin tüm 0'a eşit ise TRUE; Aksi durumda FALSE.  
  
##  <a name="operator_crect"></a>  CD2DRectF::operator CRect  
 CD2DRectF CRect nesnesine dönüştürür.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D dikdörtgen geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
