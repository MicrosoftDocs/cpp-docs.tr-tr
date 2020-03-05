---
title: MatchEvent
description: C++ Build Insights SDK 'Sı matchevent işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f8022953e2f56f7c8917f161b094c50e0c5ecbdf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332777"
---
# <a name="matchevent"></a>MatchEvent

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEvent` işlevi bir olayı olay türleri listesiyle eşleştirmek için kullanılır. Olay listedeki bir türle eşleşiyorsa, daha fazla işleme için bir işleyiciye iletilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename        TEvent,
    typename...     TEvents,
    typename        TCallable,
    typename...     TExtraArgs>
bool MatchEvent(
    const RawEvent& event,
    TCallable&&     callable,
    TExtraArgs&&... extraArgs);
```

### <a name="parameters"></a>Parametreler

*TEvent*\
Eşleştirmek istediğiniz ilk olay türü.

*TEvents*\
Eşleştirmek istediğiniz kalan olay türleri.

# *Çağrılabilir*\
`operator()`destekleyen bir tür. Hangi bağımsız değişkenlerin bu işlece geçirildiği hakkında daha fazla bilgi için bkz. *çağrılabilir* parametre açıklaması.

*Textraargs*\
`MatchEvent`geçirilen ek bağımsız değişkenlerin türleri.

*olay*\
*Tevent* ve *TEvents*tarafından tanımlanan olay türleriyle eşleşecek olay.

*çağrılabilir*\
`MatchEvent`, olayını *tevent* ve *TEvents*tarafından tanımlanan herhangi bir olay türüyle başarılı bir şekilde eşleştirdikten sonra *çağrılabilir* . *Çağrılabilir* öğesine geçirilen ilk bağımsız değişken, eşleşen olay türünün bir r değeridir. *Extraargs* parametre paketi, kalan *çağrılabilir*parametrelerde kusursuz iletilir.  

*Extraargs*\
Kusursuz şekilde iletilen bağımsız değişkenler, eşleşen olay türüyle birlikte *çağrılabilir* .

### <a name="return-value"></a>Dönüş Değeri

Eşleşme başarılı olursa **true** olan bir **bool** değeri ya da aksi takdirde **false** .

## <a name="remarks"></a>Açıklamalar

*Tevent* ve *TEvents* parametreleri için kullanılacak olay türleri bir *yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için bkz. [olay tablosu](../event-table.md).

## <a name="example"></a>Örnek

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEvent<Function, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});

    bool b2 = MatchEvent<CodeGeneration, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});


    // b1: true because the list of types contains Function, which is
    //     the type of the event we are trying to match.
    // b2: false because the list of types doesn't contain Function.
}
```

::: moniker-end
