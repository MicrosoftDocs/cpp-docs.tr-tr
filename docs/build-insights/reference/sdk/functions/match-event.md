---
title: Maç Etkinliği
description: C++ Build Insights SDK MatchEvent fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c60653641c676716bcdd60865433773da79325f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323865"
---
# <a name="matchevent"></a>Maç Etkinliği

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MatchEvent` bir olayı olay türleri listesiyle eşleştirmek için kullanılır. Olay listedeki bir türle eşleşiyorsa, daha fazla işlem için bir işleyiciye iletilir.

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
Eşleştirmek istediğiniz ilk etkinlik türü.

*TEvents*\
Eşleştirmek istediğiniz kalan olay türleri.

*TCallable*\
`operator()`Destekleyen bir tür. Hangi bağımsız değişkenlerin bu işleişle geçirildiği hakkında daha fazla bilgi için *çağrılabilir* parametre açıklamasına bakın.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin `MatchEvent`türleri.

*Olay*\
*Olay TEvent* ve *TEvents*tarafından açıklanan olay türleri karşı maç .

*Callable*\
`MatchEvent`etkinliği *TEvent* ve *TEvents*tarafından açıklanan olay türlerinden herhangi biriyle başarıyla eşleştirdikten sonra *çağrılabilir* çağırır. *Çağrılabilir'e* geçirilen ilk bağımsız değişken, eşleşen olay türünün r değeridir. *ExtraArgs* parametre paketi *çağrılabilir*kalan parametreleri mükemmel iletilir.  

*extraArgs*\
Eşleşen olay türüyle birlikte *çağrılabilir* için mükemmel iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Eşleştirme başarılı **veya** **yanlış** başka bir şekilde doğru bir **bool** değeri.

## <a name="remarks"></a>Açıklamalar

*TEvent* ve *TEvents* parametreleri için kullanılacak olay *türleri, yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için [olay tablosuna](../event-table.md)bakın.

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
