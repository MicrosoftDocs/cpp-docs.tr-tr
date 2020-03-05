---
title: Makestaticanaliz Zergroup
description: C++ Build Insights SDK 'Sı Makestaticanalgrubu işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5eabb0fcbb0a0bb0eea0f4e6bbf27b8e4c53c3ab
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332819"
---
# <a name="makestaticanalyzergroup"></a>Makestaticanaliz Zergroup

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeStaticAnalyzerGroup` işlevi, [Çözümle](analyze.md) veya [relog](relog.md)gibi işlevlere geçirilebilecek bir statik çözümleyici grubu oluşturmak için kullanılır. Bir çözümleyici grubunun üyeleri, bir izleme içindeki tüm olaylar çözümlenene kadar olayları bir veya soldan sağa doğru bir şekilde alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerPtrs*\
Bu parametre her zaman çıkarılır.

*çözümleyiciler*\
Statik çözümleyici grubuna dahil edilen [ıanalyzer](../other-types/ianalyzer-class.md) işaretçilerinin parametre paketi. Bu işaretçiler ham, `std::unique_ptr`veya `std::shared_ptr`olabilir.

### <a name="return-value"></a>Dönüş Değeri

Statik çözümleyici grubu. Dönüş değerini yakalamak için **Auto** anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik çözümleyici gruplarından farklı olarak, statik çözümleyici grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, statik bir çözümleyici grubu, çok biçimli davranışa sahip olmayan [ıanalyzer](../other-types/ianalyzer-class.md) işaretçilerini içerir. Bir Windows için olay Izleme (ETW) izlemek için bir statik çözümleyici grubu kullanırken, `IAnalyzer` arabirimine yapılan çağrılar her zaman doğrudan çözümleyici grup üyesi tarafından işaret edilen nesneye çözümlenir. Bu esneklik kaybı, daha hızlı olay işleme süreleriyle birlikte gelir. Bir çözümleyici grubunun üyeleri derleme zamanında tanınamaz veya `IAnalyzer` işaretçilerde polimorfik davranışa ihtiyaç duyuyorsanız, dinamik çözümleyici grubunu kullanmayı düşünün. Dinamik çözümleyici grubunu kullanmak için, bunun yerine [Makedynamicanaliz zergroup](make-static-analyzer-group.md) çağırın.

::: moniker-end
