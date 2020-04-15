---
title: AnalyzeA
description: C++ Build Insights SDK AnalyzeA fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7c7602c49ab5f3ce67693424019e253727563293
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324135"
---
# <a name="analyzea"></a>AnalyzeA

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `AnalyzeA` Windows için Olay İzleme (ETW) izinden gelen bir girişten okunan MSVC olaylarını çözümlemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE AnalyzeA(
    const char*                inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Parametreler

*inputLogFile*\
Olayları okumak istediğiniz giriş ETW izi.

*analizAçıklayıcı*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) bir nesneye işaretçi. Çözümlemesi yapılandırmak için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
