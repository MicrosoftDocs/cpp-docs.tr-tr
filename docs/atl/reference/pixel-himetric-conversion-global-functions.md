---
title: Piksel HIMETRIC dönüştürme genel işlevleri | Microsoft Docs
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
ms.openlocfilehash: 14b28ec031cf4570ec98e9ab2cebfa3954a88754
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881168"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Piksel/HIMETRIC dönüştürme genel işlevleri
Bu işlevler, gelen ve piksel hımetrıc dönüştürme için destek sağlar.  
  
> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Piksel HIMETRIC birimleri (her birim 0,01 milimetre'dir) dönüştürür.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Piksel HIMETRIC birimleri dönüştürür (her birim 0,01 milimetre'dir).|  
  
##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel  
 Ekran cihazında, bir nesnenin HIMETRIC birimindeki (her birim 0,01 milimetre) boyutunu piksel cinsinden boyuta dönüştürür.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpSizeInHiMetric*  
 [in] Nesnenin HIMETRIC birimindeki boyutunu işaretçisi.  
  
 *lpSizeInPix*  
 [out] Döndürülecek nesnenin boyutunu piksel cinsinden olduğu için işaretçi.  
  
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
 *lpSizeInPix*  
 [in] Nesnesinin piksel boyutunda işaretçisi.  
  
 *lpSizeInHiMetric*  
 [out] Döndürülecek nesnenin boyutunu HIMETRIC birimleri olduğu için işaretçi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
