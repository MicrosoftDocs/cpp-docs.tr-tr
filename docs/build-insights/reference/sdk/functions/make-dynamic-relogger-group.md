---
title: MakeDynamicReloggerGroup
description: C++ Build Insights SDK MakeDynamicReloggerGroup işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6bfa5bfbe8a61148f925ba185fccc035fd44d02d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920274"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`MakeDynamicReloggerGroup`İşlevi, dinamik bir yeniden günlükçü grubu oluşturmak için kullanılır. Bir yeniden günlükçü grubunun üyeleri, bir izleme içindeki tüm olaylar işlenene kadar olayları birer birer soldan sağa alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>Parametreler

*yeniden oturum defterleri*\
Dinamik yeniden günlükçüsü grubuna eklenen bir [ıregünlükçü](../other-types/irelogger-class.md) işaretçileri vektörü. Bu işaretçiler ham, veya olabilir `std::unique_ptr` `std::shared_ptr` . Bir devralma ilişkisi nedeniyle [ıanalyzer](../other-types/ianalyzer-class.md) işaretçileri de işaretçiler olarak kabul edilir `IRelogger` .

### <a name="return-value"></a>Dönüş Değeri

Dinamik bir yeniden günlükçüsü grubu. **`auto`** Dönüş değerini yakalamak için anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik yeniden günlükçü gruplarından farklı olarak, dinamik yeniden günlükçüsü grubunun üyelerinin derleme zamanında bilinmesine gerek yoktur. Program girdisine göre veya derleme zamanında bilinmeyen diğer değerlere bağlı olarak çalışma zamanında yeniden günlükçü grubu üyelerini seçebilirsiniz. Statik yeniden günlükçü gruplarından farklı olarak, [`IRelogger`](../other-types/irelogger-class.md) dinamik bir yeniden günlükçüsü grubundaki işaretçiler çok biçimli davranışlara sahiptir ve sanal işlev çağrıları doğru şekilde dağıtılır. Bu esneklik, büyük olasılıkla daha yavaş bir olay işleme süresinin maliyetiyle gelir. Tüm yeniden günlükçü grubu üyeleri derleme zamanında bilindiğinde ve Polimorfik davranışa ihtiyacınız yoksa, statik bir yeniden günlükçüsü grubu kullanmayı düşünün. Statik bir yeniden günlükçü grubunu kullanmak için [`MakeStaticReloggerGroup`](make-static-relogger-group.md) bunun yerine çağırın.

Dinamik bir yeniden günlükçüsü grubu statik bir yeniden günlükçü grubu içinde kapsüllenebilir. Adresine geçitirsiniz [`MakeStaticReloggerGroup`](make-static-relogger-group.md) . Dinamik yeniden günlükçüsü gruplarını gibi işlevlere ( [`Relog`](relog.md) yalnızca statik yeniden günlükçü gruplarını kabul eden) geçirmek için bu tekniği kullanın.

::: moniker-end
