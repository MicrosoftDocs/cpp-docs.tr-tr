---
title: MakeStaticReloggerGroup
description: C++ Build Insights SDK 'Sı MakeStaticReloggerGroup işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 06927af89b16d9de1148e555868dd2022c59b171
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332812"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeStaticReloggerGroup` işlevi, [relog](relog.md)gibi işlevlere geçirilebilecek bir statik yeniden günlükçüsü grubu oluşturmak için kullanılır. Bir yeniden günlükçü grubunun üyeleri, bir izleme içindeki tüm olaylar işlenene kadar olayları birer birer soldan sağa alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>Parametreler

*Treloggerptrs*\
Bu parametre her zaman çıkarılır.

*relogger*\
Statik yeniden günlükçüsü grubuna dahil edilen [ıregünlükçü](../other-types/irelogger-class.md) işaretçilerinin parametre paketi. Bu işaretçiler ham, `std::unique_ptr`veya `std::shared_ptr`olabilir. [Ianalyzer](../other-types/ianalyzer-class.md) işaretçileri, devralma ilişkisi nedeniyle işaretçiler `IRelogger` de kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Statik yeniden günlükçüsü grubu. Dönüş değerini yakalamak için **Auto** anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik yeniden günlükçü gruplarından farklı olarak, statik yeniden günlükçüsü grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, statik bir yeniden günlükçü grubu, çok biçimli davranışa sahip olmayan [ıregünlükçü](../other-types/irelogger-class.md) işaretçilerini içerir. Bir Windows için olay Izleme (ETW) izlemek için bir statik yeniden günlükçüsü grubu kullanırken, `IRelogger` arabirimine yapılan çağrılar her zaman doğrudan yeniden günlükçü grup üyesi tarafından işaret edilen nesneye çözümlenir. Bu esneklik kaybı, daha hızlı olay işleme süreleriyle birlikte gelir. Bir yeniden günlükçü grubunun üyeleri derleme zamanında tanınamaz veya `IRelogger` işaretçilerde polimorfik davranışa ihtiyaç duyuyorsanız, dinamik bir yeniden günlükçüsü grubu kullanmayı düşünün. Bunun yerine [Makedynamicreloggergroup](make-dynamic-relogger-group.md) öğesini çağırarak dinamik bir yeniden günlükçüsü grubu kullanabilirsiniz.

::: moniker-end
