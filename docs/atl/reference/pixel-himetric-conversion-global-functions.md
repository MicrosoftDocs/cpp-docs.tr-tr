---
title: Piksel-HIMETRIC Dönüşüm Küresel Fonksiyonlar
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 08c72c0d8f3d061950d6945d9fb412c0a16355da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326151"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Piksel/HIMETRIC Dönüşüm Global Fonksiyonlar

Bu işlevler, piksel ve HIMETRIC birimlerine ve bunlara dönüştürme desteği sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC birimlerini (her birim 0,01 milimetredir) piksellere dönüştürür.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Pikselleri HIMETRIC birimlerine dönüştürür (her birim 0,01 milimetredir).|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel

Ekran cihazında, bir nesnenin HIMETRIC birimindeki (her birim 0,01 milimetre) boyutunu piksel cinsinden boyuta dönüştürür.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Parametreler

*lpSizeInHiMetric*<br/>
[içinde] HIMETRIC birimlerinde nesnenin boyutunu işaretçi.

*lpSizeInPix*<br/>
[çıkış] Nesnenin pikselboyutuna döndürülecek yeri işaretle.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric

Ekran cihazında, bir nesnenin piksel birimindeki boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) boyuta dönüştürür.

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Parametreler

*lpSizeInPix*<br/>
[içinde] Piksellerde nesnenin boyutunu işaretle.

*lpSizeInHiMetric*<br/>
[çıkış] HIMETRIC birimlerinde nesnenin boyutunun nereye döndürüleceğini işaretle.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
