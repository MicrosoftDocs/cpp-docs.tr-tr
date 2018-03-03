---
title: "Piksel HIMETRIC dönüştürme genel işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d670d667345c233fc499cda42194dfafa185dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pixelhimetric-conversion-global-functions"></a>Piksel/HIMETRIC dönüştürme genel işlevler
Bu işlevler piksel gelen ve HIMETRIC birimleri dönüştürmek için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|(Her 0,01 milimetre birimdir) HIMETRIC birimleri piksel olarak dönüştürür.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Piksel HIMETRIC birimlerine dönüştürür (her 0,01 milimetre birimdir).|  
  
##  <a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
 Ekran cihazında, bir nesnenin HIMETRIC birimindeki (her birim 0,01 milimetre) boyutunu piksel cinsinden boyuta dönüştürür.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpSizeInHiMetric`  
 [in] İşaretçi HIMETRIC birimleri nesnenin boyutu.  
  
 `lpSizeInPix`  
 [out] Nesnenin boyutu piksel cinsinden döndürülecek olduğu için işaretçi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
 Ekran cihazında, bir nesnenin piksel birimindeki boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) boyuta dönüştürür.  
  
```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpSizeInPix`  
 [in] İşaretçi piksel cinsinden nesnenin boyutu.  
  
 `lpSizeInHiMetric`  
 [out] Nesnenin boyutu HIMETRIC birimlerindeki döndürülecek olduğu için işaretçi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
