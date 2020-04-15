---
title: MakeDynamicReloggerGroup
description: C++ Build Insights SDK MakeDynamicReloggerGroup fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f49e37f8e1a8b9ca9a800d20b2891a54453095ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323946"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `MakeDynamicReloggerGroup` dinamik bir relogger grubu oluşturmak için kullanılır. Bir relogger grubunun üyeleri, bir izlemedeki tüm olaylar işlenene kadar olayları soldan sağa tektek alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>Parametreler

*reloggers*\
Dinamik relogger grubuna dahil [iRelogger](../other-types/irelogger-class.md) işaretçileri vektörü. Bu işaretçiler ham `std::unique_ptr`veya `std::shared_ptr`. [IAnalyzer](../other-types/ianalyzer-class.md) işaretçileri `IRelogger` de bir devralma ilişkisi nedeniyle işaretçiler olarak kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Dinamik bir relogger grubu. İade değerini yakalamak için **otomatik** anahtar sözcüğü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik relogger gruplarının aksine, dinamik bir relogger grubunun üyelerinin derleme zamanında bilinmesi gerekmez. Relogger grup üyelerini çalışma zamanında program girişine göre veya derleme zamanında bilinmeyen diğer değerleri temel alan seçebilirsiniz. Statik relogger gruplarının aksine, dinamik bir relogger grubu içindeki [IRelogger](../other-types/irelogger-class.md) işaretçileri çok biçimli davranışa sahiptir ve sanal işlev çağrıları doğru şekilde gönderilir. Bu esneklik, muhtemelen daha yavaş bir olay işleme süresi pahasına gelir. Tüm relogger grup üyeleri derleme zamanında biliniyorsa ve polimorfik davranışa ihtiyacınız yoksa, statik bir relogger grubu kullanmayı düşünün. Statik bir relogger grubu kullanmak için [MakeStaticReloggerGroup'u](make-static-relogger-group.md) arayın.

Dinamik bir relogger grubu statik relogger grubu içinde kapsüllenebilir. Adresini [MakeStaticReloggerGroup'a](make-static-relogger-group.md)geçersiniz. Bu tekniği, yalnızca statik relogger gruplarını kabul eden [Relog](relog.md)gibi işlevlere dinamik relogger gruplarını geçirmek için kullanın.

::: moniker-end
