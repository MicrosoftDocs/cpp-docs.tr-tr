---
title: MakeDynamicAnalyzerGroup
description: C++ Build Insights SDK Makedynamicanaliz Zergroup işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4a10c175cf41bb0e867a9211a11595c8abaca18a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920287"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`MakeDynamicAnalyzerGroup`İşlevi bir dinamik çözümleyici grubu oluşturmak için kullanılır. Bir çözümleyici grubunun üyeleri, bir izleme içindeki tüm olaylar çözümlenene kadar olayları bir veya soldan sağa doğru bir şekilde alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>Parametreler

*Çözümleyicileri*\
Dinamik çözümleyici grubuna eklenen bir [ıanalyzer](../other-types/ianalyzer-class.md) işaretçileri vektörü. Bu işaretçiler ham, veya olabilir `std::unique_ptr` `std::shared_ptr` .

### <a name="return-value"></a>Dönüş Değeri

Dinamik çözümleyici grubu. **`auto`** Dönüş değerini yakalamak için anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik çözümleyici gruplarının aksine, dinamik çözümleyici grubunun üyelerinin derleme zamanında bilinmesine gerek yoktur. Program girdisine göre veya derleme zamanında bilinmeyen diğer değerlere bağlı olarak çalışma zamanında çözümleyici grup üyelerini seçebilirsiniz. Statik çözümleyici gruplarından farklı olarak, [`IAnalyzer`](../other-types/ianalyzer-class.md) dinamik çözümleyici grubundaki işaretçiler polimorfik davranışa sahiptir ve sanal işlev çağrıları doğru şekilde dağıtılır. Bu esneklik, büyük olasılıkla daha yavaş bir olay işleme süresinin maliyetiyle gelir. Tüm çözümleyici grubu üyeleri derleme zamanında bilindiğinde ve Polimorfik davranışa ihtiyacınız yoksa statik çözümleyici grubunu kullanmayı düşünün. Statik çözümleyici grubunu kullanmak için [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md) bunun yerine çağırın.

Dinamik çözümleyici grubu statik çözümleyici grubu içinde kapsüllenebilir. Adresi adresine geçirerek yapılır [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md) . Dinamik çözümleyici gruplarını [`Analyze`](analyze.md) yalnızca statik çözümleyici gruplarını kabul eden gibi işlevlere geçirmek için bu tekniği kullanın.

::: moniker-end
