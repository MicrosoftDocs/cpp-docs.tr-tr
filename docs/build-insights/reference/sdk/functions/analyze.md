---
title: Çözümleme
description: C++ Build Insights SDK Analiz fonksiyonu başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08b3643270cc785b3fbea36720d192b4a1473104
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324104"
---
# <a name="analyze"></a>Çözümleme

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `Analyze` C++ yapısını izlerken MSVC'den alınan Windows (ETW) için Olay İzleme çözümlemesi için kullanılır. ETW izlemedeki olaylar, arayan tarafından sağlanan bir çözümleyici grubuna sırayla iletilir. Bu işlev, olay akışının çözümleyici grubuna art arda birden çok kez iletilmesine olanak tanıyan çok geçişli analizleri destekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerGroupÜyeleri*\
Bu parametre her zaman çıkarılır.

*inputLogFile*\
Olayları okumak istediğiniz giriş ETW izi.

*numberOfPasses*\
Giriş izleme üzerinde çalıştırmak için çözümleme geçer sayısı. İz, analiz başına bir kez sağlanan analizör grubundan geçirilir.

*analyzerGroup*\
Analiz için kullanılan analizci grubu. Bir çözümleyici grubu oluşturmak için [MakeStaticAnalyzerGroup'u](make-static-analyzer-group.md) arayın. [MakeDynamicAnalyzerGroup'tan](make-dynamic-analyzer-group.md)elde edilen dinamik bir analizör grubunu kullanmak için, önce adresini statik `MakeStaticAnalyzerGroup`bir çözümleyici grubuna ileterek kapsülle.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
