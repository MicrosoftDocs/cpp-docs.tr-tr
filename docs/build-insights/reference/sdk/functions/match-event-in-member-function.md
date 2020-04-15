---
title: MatchEventInmemberFunction
description: C++ Build Insights SDK MatchEventInMemberFunction fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 522630da16e3f4a1294316d88140f4bc25dca2c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323894"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInmemberFunction

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MatchEventInMemberFunction` bir olayı bir üye işlevin ilk parametresi tarafından açıklanan türle eşleştirmek için kullanılır. Eşleşen olay daha fazla işleme için üye işlevine iletilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>Parametreler

*TInterface*\
Üye işlevi içeren tür.

*Geri Dönüş*\
Üye işlevin dönüş türü.

*TEvent*\
Eşleşecek olayın türü.

*TExtraParams*\
Üye işlev tarafından kabul edilen ekstra parametrelerin türleri ve eşleşecek olay türü.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin `MatchEventInMemberFunction`türleri.

*Olay*\
*TEvent*tarafından açıklanan olay türüne göre eşleşecek olay.

*objectPtr*\
*Üye Func'ın* çağrıldığı bir nesneye işaretçi.

*üyeFunc*\
Eşleşmek için olay türünü açıklayan üye işlev.

*extraArgs*\
Olay türü parametresi ile birlikte *üyeFunc* için mükemmel iletilir olsun argümanlar.

### <a name="return-value"></a>Dönüş Değeri

Eşleştirme başarılı veya **yanlış** başka bir şekilde **doğru** bir **bool** değeri.

## <a name="remarks"></a>Açıklamalar

*TEvent* parametresi için kullanılacak olay *türü, yakalama sınıfları*listesinden seçilebilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için [olay tablosuna](../event-table.md)bakın.

## <a name="example"></a>Örnek

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
