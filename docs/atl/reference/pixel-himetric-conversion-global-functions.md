---
title: Piksel HIMETRIC dönüştürme genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 95b3b9c6ba4e5d25a9f07f72f9479121a223ad00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529109"
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

*lpSizeInHiMetric*<br/>
[in] Nesnenin HIMETRIC birimindeki boyutunu işaretçisi.

*lpSizeInPix*<br/>
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

*lpSizeInPix*<br/>
[in] Nesnesinin piksel boyutunda işaretçisi.

*lpSizeInHiMetric*<br/>
[out] Döndürülecek nesnenin boyutunu HIMETRIC birimleri olduğu için işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)
