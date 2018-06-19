---
title: CD2DRectU sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36d960cfc0ce3d9d5632edd3a1b42903f3cdd0f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352024"
---
# <a name="cd2drectu-class"></a>CD2DRectU sınıfı
İçin sarmalayıcı `D2D1_RECT_U`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|Fazla Yüklendi. Oluşturan bir `CD2DRectU` nesnesini `D2D1_RECT_U` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectU::IsNull](#isnull)|Döndürür bir `boolean` bir ifade geçerli bir veri içerip içermediğini gösteren değeri ( `null`).|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|Dönüştürür `CD2DRectU` için `CRect` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2drectu"></a>  CD2DRectU::CD2DRectU  
 CRect nesnesinden CD2DRectU nesnesi oluşturur.  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Kaynak dikdörtgen  
  
 `uLeft`  
 Kaynak sol koordinat  
  
 `uTop`  
 Kaynak üst koordinat  
  
 `uRight`  
 Kaynak sağ koordinat  
  
 `uBottom`  
 kaynak alt koordinat  
  
##  <a name="isnull"></a>  CD2DRectU::IsNull  
 Bir ifade (boş) geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikdörtgenin üst, sol, alt ve sağ değerlerin 0 olarak tüm eşitse TRUE; Aksi takdirde FALSE.  
  
##  <a name="operator_crect"></a>  CD2DRectU::operator CRect  
 CD2DRectU CRect nesnesine dönüştürür.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D dikdörtgen geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
