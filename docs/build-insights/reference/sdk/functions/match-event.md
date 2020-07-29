---
title: MatchEvent
description: C++ Build Insights SDK 'Sı MatchEvent işlevi başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ec2c6bfcacf28998058dc66b5f363fbf1ea5d70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224116"
---
# <a name="matchevent"></a>MatchEvent

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEvent`İşlevi bir olayı olay türleri listesiyle eşleştirmek için kullanılır. Olay listedeki bir türle eşleşiyorsa, daha fazla işleme için bir işleyiciye iletilir.

## <a name="syntax"></a>Söz dizimi

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

*# Çağrılabilir*\
Tarafından desteklenen bir tür `operator()` . Hangi bağımsız değişkenlerin bu işlece geçirildiği hakkında daha fazla bilgi için bkz. *çağrılabilir* parametre açıklaması.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin türleri `MatchEvent` .

*olay*\
*Tevent* ve *TEvents*tarafından tanımlanan olay türleriyle eşleşecek olay.

*çağrılabilir*\
`MatchEvent`olay, *tevent* ve *TEvents*tarafından tanımlanan herhangi bir olay türüyle başarılı bir şekilde eşleştirdikten sonra *çağrılabilir* çağırır. *Çağrılabilir* öğesine geçirilen ilk bağımsız değişken, eşleşen olay türünün bir r değeridir. *Extraargs* parametre paketi, kalan *çağrılabilir*parametrelerde kusursuz iletilir.  

*extraArgs*\
Kusursuz şekilde iletilen bağımsız değişkenler, eşleşen olay türüyle birlikte *çağrılabilir* .

### <a name="return-value"></a>Dönüş Değeri

**`bool`** **`true`** Eşleşmesinin başarılı olduğu veya **`false`** başka türlü bir değer.

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
