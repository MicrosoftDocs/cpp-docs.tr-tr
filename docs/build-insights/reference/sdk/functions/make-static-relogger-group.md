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
ms.openlocfilehash: 1d49f15a14675f265e1f63ef8795f442f49ad5d4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920209"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`MakeStaticReloggerGroup`İşlevi, [relog](relog.md)gibi işlevlere geçirilebilecek bir statik yeniden günlükçüsü grubu oluşturmak için kullanılır. Bir yeniden günlükçü grubunun üyeleri, bir izleme içindeki tüm olaylar işlenene kadar olayları birer birer soldan sağa alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>Parametreler

*TReloggerPtrs*\
Bu parametre her zaman çıkarılır.

*yeniden oturum defterleri*\
[`IRelogger`](../other-types/irelogger-class.md)Statik yeniden günlükçüsü grubuna dahil edilen işaretçilerin parametre paketi. Bu işaretçiler ham, veya olabilir `std::unique_ptr` `std::shared_ptr` . [`IAnalyzer`](../other-types/ianalyzer-class.md) Ayrıca, `IRelogger` bir devralma ilişkisi nedeniyle işaretçiler de kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Statik yeniden günlükçüsü grubu. **`auto`** Dönüş değerini yakalamak için anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Dinamik yeniden günlükçü gruplarından farklı olarak, statik yeniden günlükçüsü grubunun üyeleri derleme zamanında bilinmelidir. Ayrıca, statik bir yeniden günlükçü grubu [`IRelogger`](../other-types/irelogger-class.md) polimorfik davranışa sahip olmayan işaretçiler içerir. Bir Windows için olay Izleme (ETW) izlemek için bir statik yeniden günlükçüsü grubu kullanırken, arabirime yapılan çağrılar `IRelogger` her zaman yeniden günlükçü grubu üyesi tarafından işaret edilen nesneye çözümlenir. Bu esneklik kaybı, daha hızlı olay işleme süreleriyle birlikte gelir. Bir yeniden günlükçü grubunun üyeleri derleme zamanında tanınamaz veya işaretçilerde polimorfik davranışa ihtiyaç duyuyorsanız `IRelogger` , dinamik bir yeniden günlükçüsü grubu kullanmayı düşünün. Bunun yerine çağırarak dinamik bir yeniden günlükçüsü grubu kullanabilirsiniz [`MakeDynamicReloggerGroup`](make-dynamic-relogger-group.md) .

::: moniker-end
