---
title: OnAnalysisEventFunc typedef
description: C++ Build Insights SDK OnAnalysisEventFunc typedef referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eacd174279caff0db22586d5e40d3a866afc4459
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329122"
---
# <a name="onanalysiseventfunc-typedef"></a>OnAnalysisEventFunc typedef

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`OnAnalysisEventFunc` [Typedef, ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) yapısında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Geçerli olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

*geri aramaBağlam*\
[bu](analysis-descriptor-struct.md) geri arama için ANALYSIS_DESCRIPTOR veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md)olarak ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki adımı kontrol eden [CALLBACK_CODE](callback-code-enum.md) bir değer.

::: moniker-end
