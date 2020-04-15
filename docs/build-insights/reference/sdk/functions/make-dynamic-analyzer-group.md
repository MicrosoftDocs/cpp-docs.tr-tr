---
title: MakeDynamicAnalyzerGroup
description: C++ Build Insights SDK MakeDynamicAnalyzerGroup fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 148eeea41f29ac6dd75653feed7f3f3f8c301911
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323969"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `MakeDynamicAnalyzerGroup` dinamik bir çözümleyici grubu oluşturmak için kullanılır. Bir çözümleyici grubunun üyeleri, izlemedeki tüm olaylar analiz edilene kadar olayları soldan sağa tektek alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>Parametreler

*Analizörleri*\
Dinamik çözümleyici grubuna dahil edilen [IAnalyzer](../other-types/ianalyzer-class.md) işaretçilerinden oluşan bir vektör. Bu işaretçiler ham `std::unique_ptr`veya `std::shared_ptr`.

### <a name="return-value"></a>Dönüş Değeri

Dinamik bir analizci grubu. İade değerini yakalamak için **otomatik** anahtar sözcüğü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik çözümleyici gruplarının aksine, dinamik çözümleyici grubunun üyelerinin derleme zamanında bilinmesi gerekmez. Program girişine göre çalışma zamanında çözümleyici grup üyelerini seçebilir veya derleme zamanında bilinmeyen diğer değerleri temel alabilirsiniz. Statik çözümleyici gruplarının aksine, dinamik çözümleyici grubundaki [IAnalyzer](../other-types/ianalyzer-class.md) işaretçileri çok biçimli davranışa sahiptir ve sanal işlev çağrıları doğru bir şekilde gönderilir. Bu esneklik, muhtemelen daha yavaş bir olay işleme süresi pahasına gelir. Tüm çözümleyici grup üyeleri derleme zamanında biliniyorsa ve çok biçimli davranışa ihtiyacınız yoksa statik çözümleyici grubu kullanmayı düşünün. Statik çözümleyici grubu kullanmak için Bunun yerine [MakeStaticAnalyzerGroup'u](make-static-analyzer-group.md) arayın.

Dinamik bir çözümleyici grubu statik bir çözümleyici grubu içinde kapsüllenebilir. Adresini [MakeStaticAnalyzerGroup'a](make-static-analyzer-group.md)vererek yapılır. Dinamik çözümleyici gruplarını yalnızca statik çözümleyici gruplarını kabul eden [Analyze](analyze.md)gibi işlevlere geçirmek için bu tekniği kullanın.

::: moniker-end
