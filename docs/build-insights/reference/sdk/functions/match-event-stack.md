---
title: MatchEventStack
description: C++ Build Insights SDK 'Sı MatchEventStack işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08627b6af601f6894aa228683ffb51232b015310
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922816"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`MatchEventStack`İşlevi, bir olay yığınını belirli bir olay hiyerarşisine göre eşleştirmek için kullanılır. Eşleşen hiyerarşiler daha fazla işleme için bir işleyiciye iletilir. Olaylar, olay yığınları ve Hiyerarşiler hakkında daha fazla bilgi için bkz. [olay tablosu](../event-table.md).

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
Olay yığınında eşleştirilecek Eldest üst öğesinin türü.

*TEvents*\
Olay yığınında eşleştirmek istediğiniz kalan türler.

*# Çağrılabilir*\
Tarafından desteklenen bir tür `operator()` . Hangi bağımsız değişkenlerin bu işlece geçirildiği hakkında daha fazla bilgi için bkz. *çağrılabilir* parametre açıklaması.

*TExtraArgs*\
Öğesine geçirilen fazladan bağımsız değişkenlerin türleri `MatchEventStack` .

*eventStack*\
*Tevent* ve *TEvents* tarafından tanımlanan olay türü hiyerarşisine göre eşleştirilecek olay yığını.

*çağrılabilir*\
Olay yığınını, *tevent* ve *TEvents* tarafından tanımlanan olay türü hiyerarşisine başarıyla eşleştirdikten sonra `MatchEventStack` *çağrılabilir* çağırır. Olay hiyerarşisindeki her tür için *çağrılabilir* bir r-value bağımsız değişkenine geçirilir. *Extraargs* parametre paketi, kalan *çağrılabilir* parametrelerde kusursuz iletilir.

*extraArgs*\
Kusursuz şekilde iletilen bağımsız değişkenler, eşleşen olay türüyle birlikte *çağrılabilir* .

### <a name="return-value"></a>Dönüş Değeri

**`bool`** **`true`** Eşleşmesinin başarılı olması veya **`false`** başka türlü bir değer.

## <a name="remarks"></a>Açıklamalar

*Eventstack* 'teki son olay her zaman birleştirilmiş \[ *tevent* , *TEvents...* Type listesindeki son girdiye göre eşleşir \] . Diğer tüm *tevent* ve *TEvents* girişleri, en son dışında, aynı sırada olmaları şartıyla *eventstack* 'teki herhangi bir konumla eşleşir.

*Tevent* ve *TEvents* parametreleri için kullanılacak olay türleri bir *yakalama sınıfları* listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için bkz. [olay tablosu](../event-table.md).

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
