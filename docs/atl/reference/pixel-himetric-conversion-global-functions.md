---
description: 'Daha fazla bilgi edinin: Pixel/HIMETRIK dönüştürme genel Işlevleri'
title: Pixel-HIMETRIK dönüştürme genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 53753ff92b04466a94b821fdc4b4f221117c6ade
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138989"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Pixel/HIMETRIK dönüştürme genel Işlevleri

Bu işlevler, pixel ve HIMETRIK birimlerine ve bunlara dönüştürme desteği sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIK birimleri (her birim 0,01 Milimeter) piksel olarak dönüştürür.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Pikselleri himetrik birimlere dönüştürür (her birim 0,01 milimetre ölçtürüdür).|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a> AtlHiMetricToPixel

Ekran cihazında, bir nesnenin HIMETRIC birimindeki (her birim 0,01 milimetre) boyutunu piksel cinsinden boyuta dönüştürür.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Parametreler

*Lpsizemetric ölçümü*<br/>
'ndaki HIMETRIK birimlerde nesnenin boyutuna yönelik işaretçi.

*Lpsizeınpix*<br/>
dışı Nesnenin piksel cinsinden boyutunun döndürüleceğini gösteren işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a> AtlPixelToHiMetric

Ekran cihazında, bir nesnenin piksel birimindeki boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) boyuta dönüştürür.

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Parametreler

*Lpsizeınpix*<br/>
'ndaki Nesnenin boyutunun piksel cinsinden işaretçisi.

*Lpsizemetric ölçümü*<br/>
dışı Nesne boyutunun HIMETRIK birimlerde döndürüleceğini gösteren işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
