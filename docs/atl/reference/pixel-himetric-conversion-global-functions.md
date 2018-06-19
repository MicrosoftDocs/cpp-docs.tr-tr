---
title: Piksel HIMETRIC dönüştürme genel işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92d84204bdf02e75f1baf64bd52d96eab0b3d271
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359432"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Piksel/HIMETRIC dönüştürme genel işlevler
Bu işlevler piksel gelen ve HIMETRIC birimleri dönüştürmek için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|(Her 0,01 milimetre birimdir) HIMETRIC birimleri piksel olarak dönüştürür.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Piksel HIMETRIC birimlerine dönüştürür (her 0,01 milimetre birimdir).|  
  
##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel  
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
  
##  <a name="atlpixeltohimetric"></a>  AtlPixelToHiMetric  
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
