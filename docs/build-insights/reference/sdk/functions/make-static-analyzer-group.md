---
title: MakeStaticAnalyzerGroup
description: C++ derleme öngörüleri SDK 'Sı Makestaticanalgrubu işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d7ddb8652400438c38882b1d27e635e8f1e8db51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920248"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`MakeStaticAnalyzerGroup`İşlevi, veya gibi işlevlere geçirilebilecek bir statik çözümleyici grubu oluşturmak için kullanılır [`Analyze`](analyze.md) [`Relog`](relog.md) . Bir çözümleyici grubunun üyeleri, bir izleme içindeki tüm olaylar çözümlenene kadar olayları bir veya soldan sağa doğru bir şekilde alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerPtrs*\
Bu parametre her zaman çıkarılır.

*Çözümleyicileri*\
[`IAnalyzer`](../other-types/ianalyzer-class.md)Statik çözümleyici grubuna dahil edilen işaretçilerin parametre paketi. Bu işaretçiler ham, veya olabilir `std::unique_ptr` `std::shared_ptr` .

### <a name="return-value"></a>Dönüş Değeri

Statik çözümleyici grubu. **`auto`** Dönüş değerini yakalamak için anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik çözümleyici gruplarından farklı olarak, statik çözümleyici grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, bir statik çözümleyici grubu, [`IAnalyzer`](../other-types/ianalyzer-class.md) çok biçimli davranışa sahip olmayan işaretçiler içerir. Bir Windows için olay Izleme (ETW) izlemeyi çözümlemek için bir statik çözümleyici grubu kullanırken, arabirime yapılan çağrılar `IAnalyzer` her zaman doğrudan çözümleyici grup üyesi tarafından işaret edilen nesneye çözümlenir. Bu esneklik kaybı, daha hızlı olay işleme süreleriyle birlikte gelir. Bir çözümleyici grubunun üyeleri derleme zamanında tanınamaz veya işaretçilerde polimorfik davranışa ihtiyacınız varsa `IAnalyzer` , bir dinamik çözümleyici grubu kullanmayı düşünün. Dinamik çözümleyici grubunu kullanmak için [`MakeDynamicAnalyzerGroup`](make-static-analyzer-group.md) bunun yerine çağırın.

::: moniker-end
