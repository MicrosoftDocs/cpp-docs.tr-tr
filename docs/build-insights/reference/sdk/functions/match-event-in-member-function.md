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
ms.openlocfilehash: eabbb8a91609b1447ebcc19af32df2ffed347c24
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332805"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEventInMemberFunction` işlevi, bir olayı bir üye işlevinin ilk parametresi tarafından tanımlanan türe karşı eşleştirmek için kullanılır. Eşleşen olay, daha fazla işleme için üye işlevine iletilir.

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
Üye işlevini içeren tür.

*TReturn*\
Üye işlevinin dönüş türü.

*TEvent*\
Eşleştirilecek etkinliğin türü.

*Textraparams*\
Eşleştirilecek olay türü ile birlikte, üye işlevi tarafından kabul edilen ek parametrelerin türleri.

*Textraargs*\
`MatchEventInMemberFunction`geçirilen ek bağımsız değişkenlerin türleri.

*olay*\
*Tevent*tarafından tanımlanan olay türüyle eşleşecek olay.

*objectPtr*\
*Memberfunc* 'ın çağrıldığı nesne için bir işaretçi.

*Memberfunc*\
Eşleştirilecek olay türünü açıklayan üye işlevi.

*Extraargs*\
Mükemmel şekilde olan bağımsız değişkenler, olay türü parametresiyle birlikte *Memberfunc* 'a iletilir.

### <a name="return-value"></a>Dönüş Değeri

Eşleşme başarılı olursa **true** olan bir **bool** değeri veya aksi takdirde **false** .

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
