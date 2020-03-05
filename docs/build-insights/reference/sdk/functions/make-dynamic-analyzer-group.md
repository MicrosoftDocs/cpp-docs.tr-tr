---
title: Makedynamicanaliz Zergroup
description: C++ BUILD Insights SDK Makedynamicanaliz zergroup işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f409d685c6af6514b73cd837d668a962c1a0d01a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332833"
---
# <a name="makedynamicanalyzergroup"></a>Makedynamicanaliz Zergroup

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeDynamicAnalyzerGroup` işlevi bir dinamik çözümleyici grubu oluşturmak için kullanılır. Bir çözümleyici grubunun üyeleri, bir izleme içindeki tüm olaylar çözümlenene kadar olayları bir veya soldan sağa doğru bir şekilde alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>Parametreler

*çözümleyiciler*\
Dinamik çözümleyici grubuna eklenen bir [ıanalyzer](../other-types/ianalyzer-class.md) işaretçileri vektörü. Bu işaretçiler ham, `std::unique_ptr`veya `std::shared_ptr`olabilir.

### <a name="return-value"></a>Dönüş Değeri

Dinamik çözümleyici grubu. Dönüş değerini yakalamak için **Auto** anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik çözümleyici gruplarının aksine, dinamik çözümleyici grubunun üyelerinin derleme zamanında bilinmesine gerek yoktur. Program girdisine göre veya derleme zamanında bilinmeyen diğer değerlere bağlı olarak çalışma zamanında çözümleyici grup üyelerini seçebilirsiniz. Statik çözümleyici gruplarından farklı olarak, dinamik çözümleyici grubundaki [ıçözümleyici](../other-types/ianalyzer-class.md) işaretçilerinin polimorfik davranışı vardır ve sanal işlev çağrıları doğru şekilde dağıtılır. Bu esneklik, büyük olasılıkla daha yavaş bir olay işleme süresinin maliyetiyle gelir. Tüm çözümleyici grubu üyeleri derleme zamanında bilindiğinde ve Polimorfik davranışa ihtiyacınız yoksa statik çözümleyici grubunu kullanmayı düşünün. Statik çözümleyici grubunu kullanmak için, bunun yerine [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın.

Dinamik çözümleyici grubu statik çözümleyici grubu içinde kapsüllenebilir. Bu, adresini [Makestaticanaliz Zergroup](make-static-analyzer-group.md)'a geçirerek yapılır. Dinamik çözümleyici gruplarını, yalnızca statik çözümleyici gruplarını kabul eden [Analyze](analyze.md)gibi işlevlere geçirmek için bu tekniği kullanın.

::: moniker-end
