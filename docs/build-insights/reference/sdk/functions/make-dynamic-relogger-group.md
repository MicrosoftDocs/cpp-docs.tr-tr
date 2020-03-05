---
title: MakeDynamicReloggerGroup
description: C++ BUILD Insights SDK MakeDynamicReloggerGroup işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4ad394d3ba2982e7ee4f2a497fef2ea65a3c1769
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332826"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MakeDynamicReloggerGroup` işlevi, dinamik bir yeniden günlükçüsü grubu oluşturmak için kullanılır. Bir yeniden günlükçü grubunun üyeleri, bir izleme içindeki tüm olaylar işlenene kadar olayları birer birer soldan sağa alır.

## <a name="syntax"></a>Sözdizimi

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>Parametreler

*relogger*\
Dinamik yeniden günlükçüsü grubuna eklenen bir [ıregünlükçü](../other-types/irelogger-class.md) işaretçileri vektörü. Bu işaretçiler ham, `std::unique_ptr`veya `std::shared_ptr`olabilir. [Ianalyzer](../other-types/ianalyzer-class.md) işaretçileri, devralma ilişkisi nedeniyle işaretçiler `IRelogger` de kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Dinamik bir yeniden günlükçüsü grubu. Dönüş değerini yakalamak için **Auto** anahtar sözcüğünü kullanın.

## <a name="remarks"></a>Açıklamalar

Statik yeniden günlükçü gruplarından farklı olarak, dinamik yeniden günlükçüsü grubunun üyelerinin derleme zamanında bilinmesine gerek yoktur. Program girdisine göre veya derleme zamanında bilinmeyen diğer değerlere bağlı olarak çalışma zamanında yeniden günlükçü grubu üyelerini seçebilirsiniz. Statik yeniden günlükçü gruplarından farklı olarak, dinamik bir yeniden günlükçüsü grubundaki [ıregünlükçü](../other-types/irelogger-class.md) işaretçilerinin polimorfik davranışı vardır ve sanal işlev çağrıları doğru şekilde dağıtılır. Bu esneklik, büyük olasılıkla daha yavaş bir olay işleme süresinin maliyetiyle gelir. Tüm yeniden günlükçü grubu üyeleri derleme zamanında bilindiğinde ve Polimorfik davranışa ihtiyacınız yoksa, statik bir yeniden günlükçüsü grubu kullanmayı düşünün. Statik bir yeniden günlükçü grubu kullanmak için, bunun yerine [Makestaticreloggergroup](make-static-relogger-group.md) çağırın.

Dinamik bir yeniden günlükçüsü grubu statik bir yeniden günlükçü grubu içinde kapsüllenebilir. Adresini [Makestaticreloggergroup](make-static-relogger-group.md)öğesine iletirsiniz. Dinamik yeniden günlükçüsü gruplarını yalnızca statik yeniden günlükçüsü gruplarını kabul eden [relog](relog.md)gibi işlevlere geçirmek için bu tekniği kullanın.

::: moniker-end
