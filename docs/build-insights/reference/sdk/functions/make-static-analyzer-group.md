---
title: MakeStaticAnalyzerGroup
description: C++ Build Insights SDK MakeStaticAnalyzerGroup fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72f7f5d7a408436902394451a52dd66efe1d93f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323937"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MakeStaticAnalyzerGroup` [Çözümle](analyze.md) veya [Yeniden Oturum](relog.md)aç gibi işlevlere geçirilebilen statik bir çözümleyici grubu oluşturmak için kullanılır. Bir çözümleyici grubunun üyeleri, izlemedeki tüm olaylar analiz edilene kadar olayları soldan sağa tektek alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerPtr*\
Bu parametre her zaman çıkarılır.

*Analizörleri*\
Statik çözümleyici grubuna dahil [iAnalyzer](../other-types/ianalyzer-class.md) işaretçilerinden oluşan bir parametre paketi. Bu işaretçiler ham `std::unique_ptr`veya `std::shared_ptr`.

### <a name="return-value"></a>Dönüş Değeri

Statik bir çözümleyici grubu. İade değerini yakalamak için **otomatik** anahtar sözcüğü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik çözümleyici gruplarından farklı olarak, statik çözümleyici grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, statik bir çözümleyici grubu çok biçimli davranış olmayan [IAnalyzer](../other-types/ianalyzer-class.md) işaretçileri içerir. Windows için Olay İzleme (ETW) izlemeyi çözümlemek için statik bir `IAnalyzer` çözümleyici grubu kullanırken, arabirime yapılan çağrılar her zaman çözümleyici grup üyesi tarafından doğrudan işaret edilen nesneye gider. Bu esneklik kaybı, daha hızlı olay işleme süreleri olasılığıyla birlikte gelir. Bir çözümleyici grubunun üyeleri derleme zamanında bilinmiyorsa veya işaretçilerinizde `IAnalyzer` çok biçimli davranış gerektiriyorsanız, dinamik bir çözümleyici grubu kullanmayı düşünün. Dinamik bir çözümleyici grubu kullanmak için [MakeDynamicAnalyzerGroup'u](make-static-analyzer-group.md) arayın.

::: moniker-end
