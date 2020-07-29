---
title: MatchEventInMemberFunction
description: C++ Build Insights SDK 'Sı MatchEventInMemberFunction işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d3fdc015b0744cb5d0f98a1c9025343b93489ed9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224155"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlevi, bir `MatchEventInMemberFunction` olayı bir üye işlevinin ilk parametresi tarafından tanımlanan türe karşı eşleştirmek için kullanılır. Eşleşen olay, daha fazla işleme için üye işlevine iletilir.

## <a name="syntax"></a>Söz dizimi

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
Üye işlevini içeren tür.

*TReturn*\
Üye işlevinin dönüş türü.

*TEvent*\
Eşleştirilecek etkinliğin türü.

*TExtraParams*\
Eşleştirilecek olay türü ile birlikte, üye işlevi tarafından kabul edilen ek parametrelerin türleri.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin türleri `MatchEventInMemberFunction` .

*olay*\
*Tevent*tarafından tanımlanan olay türüyle eşleşecek olay.

*objectPtr*\
*Memberfunc* 'ın çağrıldığı nesne için bir işaretçi.

*memberFunc*\
Eşleştirilecek olay türünü açıklayan üye işlevi.

*extraArgs*\
Mükemmel şekilde olan bağımsız değişkenler, olay türü parametresiyle birlikte *Memberfunc* 'a iletilir.

### <a name="return-value"></a>Dönüş Değeri

**`bool`** **`true`** Eşleşmesinin başarılı olması veya **`false`** başka türlü bir değer.

## <a name="remarks"></a>Açıklamalar

*Tevent* parametresi için kullanılacak olay türü, *yakalama sınıfları*listesinden seçilebilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için bkz. [olay tablosu](../event-table.md).

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
