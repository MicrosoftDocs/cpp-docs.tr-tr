---
title: MatchEventStack
description: C++ Build Insights SDK MatchEventStack fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a223d420e8c48667fbd1c6569f02d0486f597b5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323868"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MatchEventStack` olay yığınını belirli bir olay hiyerarşisi ile eşleştirmek için kullanılır. Eşleşen hiyerarşiler daha fazla işleme için bir işleyiciye iletilir. Olaylar, olay yığınları ve hiyerarşiler hakkında daha fazla bilgi edinmek için [olay tablosuna](../event-table.md)bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename          TEvent,
    typename...       TEvents,
    typename          TCallable,
    typename...       TExtraArgs>
bool MatchEventStack(
    const EventStack& eventStack,
    TCallable&&       callable,
    TExtraArgs&&...   extraArgs);
```

### <a name="parameters"></a>Parametreler

*TEvent*\
Olay yığınında eşleşecek en büyük ebeveynin türü.

*TEvents*\
Olay yığınında eşleştirmek istediğiniz kalan türler.

*TCallable*\
`operator()`Destekleyen bir tür. Hangi bağımsız değişkenlerin bu işleişle geçirildiği hakkında daha fazla bilgi için *çağrılabilir* parametre açıklamasına bakın.

*TExtraArgs*\
Ek bağımsız değişken türleri' `MatchEventStack`ne geçti.

*eventStack*\
*TEvent* ve *TEvents*tarafından açıklanan olay türü hiyerarşisi ile eşleşecek olay yığını.

*Callable*\
Olay yığınını *TEvent* ve *TEvents* `MatchEventStack` tarafından açıklanan olay türü hiyerarşisi ile başarıyla eşleştirildikten *sonra, çağrılabilir*çağırır. Olay hiyerarşisinde her tür için *çağrılabilir* bir r değeri bağımsız değişkenine geçer. *ExtraArgs* parametre paketi *çağrılabilir*kalan parametreleri mükemmel iletilir.

*extraArgs*\
Eşleşen olay türüyle birlikte *çağrılabilir* için mükemmel iletilen bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Eşleştirme başarılı veya **yanlış** başka bir şekilde **doğru** bir **bool** değeri.

## <a name="remarks"></a>Açıklamalar

*EventStack* son olay her zaman concatenated \[ *TEvent*son giriş karşı eşleşir , *TEvents ...* \] türü listesi. Diğer tüm *TEvent* ve *TEvents* girişleri, aynı sırada olmaları koşuluyla, son hariç *eventStack'teki* herhangi bir konumla eşleşebilir.

*TEvent* ve *TEvents* parametreleri için kullanılacak olay *türleri, yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için [olay tablosuna](../event-table.md)bakın.

## <a name="example"></a>Örnek

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStack<Compiler, BackEndPass, C2DLL,
                CodeGeneration, Thread, Function>(
        eventStack, [](Compiler cl, BackEndPass bep, C2DLL c2,
            CodeGeneration cg, Thread t, Function f){ /* Do something ... */ });

    bool b2 = MatchEventStack<Compiler, Function>(
        eventStack, [](Compiler cl, Function f){ /* Do something... */ });

    bool b3 = MatchEventStack<Thread, Compiler, Function>(
        eventStack, [](Thread t, Compiler cl Function f){ /* Do something... */ });

    bool b4 = MatchEventStack<Compiler>(
        eventStack, [](Compiler cl){ /* Do something... */ });


    // b1: true because the list of types matches the eventStack exactly.
    // b2: true because Function is the last entry in both the type list
    //     and 'eventStack', and also because Compiler comes before
    //     Function in 'eventStack' and in the type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', they aren't listed in the
    //     right order in the type list.
    // b4: false because the last entry in the type list is Compiler,
    //     which doesn't match the last entry in 'eventStack' (Function).
}
```

::: moniker-end
