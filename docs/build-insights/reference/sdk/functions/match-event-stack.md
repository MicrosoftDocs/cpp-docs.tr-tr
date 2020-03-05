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
ms.openlocfilehash: 445c2d00c24da10754d32256de0c691e82b557e1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332784"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEventStack` işlevi, belirli bir olay hiyerarşisine karşı bir olay yığınını eşleştirmek için kullanılır. Eşleşen hiyerarşiler daha fazla işleme için bir işleyiciye iletilir. Olaylar, olay yığınları ve Hiyerarşiler hakkında daha fazla bilgi için bkz. [olay tablosu](../event-table.md).

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

# *Çağrılabilir*\
`operator()`destekleyen bir tür. Hangi bağımsız değişkenlerin bu işlece geçirildiği hakkında daha fazla bilgi için bkz. *çağrılabilir* parametre açıklaması.

*Textraargs*\
`MatchEventStack`öğesine geçirilen ek bağımsız değişkenlerin türleri.

*Eventstack*\
*Tevent* ve *TEvents*tarafından tanımlanan olay türü hiyerarşisine göre eşleştirilecek olay yığını.

*çağrılabilir*\
Olay yığınını, *tevent* ve *TEvents*tarafından tanımlanan olay türü hiyerarşisi ile başarılı bir şekilde eşleştirdikten sonra `MatchEventStack` *çağrılabilir*çağırır. Olay hiyerarşisindeki her tür için *çağrılabilir* bir r-value bağımsız değişkenine geçirilir. *Extraargs* parametre paketi, kalan *çağrılabilir*parametrelerde kusursuz iletilir.

*Extraargs*\
Kusursuz şekilde iletilen bağımsız değişkenler, eşleşen olay türüyle birlikte *çağrılabilir* .

### <a name="return-value"></a>Dönüş Değeri

Eşleşme başarılı olursa **true** olan bir **bool** değeri veya aksi takdirde **false** .

## <a name="remarks"></a>Açıklamalar

*Eventstack* 'teki son olay her zaman birleştirilmiş \[*tevent*, *TEvents...* \] tür listesindeki son girişle eşleştirilir. Diğer tüm *tevent* ve *TEvents* girişleri, en son dışında, aynı sırada olmaları şartıyla *eventstack* 'teki herhangi bir konumla eşleşir.

*Tevent* ve *TEvents* parametreleri için kullanılacak olay türleri bir *yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için bkz. [olay tablosu](../event-table.md).

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
