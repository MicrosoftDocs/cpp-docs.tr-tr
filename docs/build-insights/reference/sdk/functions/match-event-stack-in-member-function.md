---
title: MatchEventStackInMemberFunction
description: C++ Build Insights SDK 'Sı MatchEventStackInMemberFunction işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: db02ce5656bf8970ead7b49d5580f7d81bebb1b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224142"
---
# <a name="matcheventstackinmemberfunction"></a>MatchEventStackInMemberFunction

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlevi, bir `MatchEventStackInMemberFunction` üye işlevinin parametre listesi tarafından tanımlanan belirli bir olay hiyerarşisine karşı bir olay yığınını eşleştirmek için kullanılır. Eşleşen hiyerarşiler, daha fazla işleme için üye işlevine iletilir. Olaylar, olay yığınları ve Hiyerarşiler hakkında daha fazla bilgi için bkz. [olay tablosu](../event-table.md).

## <a name="syntax"></a>Söz dizimi

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, TExtraParams...),
    TExtraArgs&&...           extraArgs);

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, TExtraParams...),
    TExtraArgs&&...           extraArgs);

// Etc...

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename     T3,
    typename     T4,
    typename     T5,
    typename     T6,
    typename     T7,
    typename     T8,
    typename     T9,
    typename     T10,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TExtraParams...),
    TExtraArgs&&...           extraArgs);
```

### <a name="parameters"></a>Parametreler

*TInterface*\
Üye işlevini içeren tür.

*TReturn*\
Üye işlevinin dönüş türü.

*T1*,..., *T10*\
Eşleştirilecek olay hiyerarşisini tanımlayan türler.

*TExtraParams*\
Üye işlevi tarafından kabul edilen ek parametrelerin türleri ve olay hiyerarşisi türleri.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin türleri `MatchEventStackInMemberFunction` .

*eventStack*\
*T1* tarafından *T10*aracılığıyla tanımlanan olay türü hiyerarşisine göre eşleştirilecek olay yığını.

*objectPtr*\
*Memberfunc* 'ın çağrıldığı nesne için bir işaretçi.

*memberFunc*\
Eşleştirilecek olay türü hiyerarşisini açıklayan üye işlevi.

*extraArgs*\
Mükemmel şekilde olan bağımsız değişkenler, olay türü hiyerarşisi parametreleriyle birlikte *Memberfunc* 'a iletilir.

### <a name="return-value"></a>Dönüş Değeri

**`bool`** **`true`** Eşleşmesinin başarılı olması veya **`false`** başka türlü bir değer.

## <a name="remarks"></a>Açıklamalar

*Eventstack* 'teki son olay her zaman eşleşecek şekilde olay türü hiyerarşisinde son girişle eşleştirilir. Olay türü hiyerarşisindeki diğer tüm türler, en son dışında, aynı sırada olmaları şartıyla *Eventstack* 'teki herhangi bir konumla eşleştirebilir.

*T1* aracılığıyla *T10* parametreleri için kullanılacak olay türleri bir *yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için bkz. [olay tablosu](../event-table.md).

## <a name="example"></a>Örnek

```cpp
void MyClass::Foo1(Compiler cl, BackEndPass bep, C2DLL c2,
    CodeGeneration cg, Thread t, Function f) { }

void MyClass::Foo2(Compiler cl, Function f) { }

void MyClass::Foo3(Thread t, Compiler cl, Function f) { }

void MyClass::Foo4(Compiler cl) { }

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo1);

    bool b2 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo2);

    bool b3 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo3);

    bool b4 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo4);

    // b1: true because the parameter types of Foo1 match the eventStack
    //     exactly.
    // b2: true because Function is the last entry in both the member
    //     function parameter list and 'eventStack', and also because
    //     Compiler comes before Function in 'eventStack' and in the
    //     parameter type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', the member function parameter
    //     list doesn't list them in the right order.
    // b4: false because the last entry in the member function parameter
    //     list is Compiler, which doesn't match the last entry in 'eventStack'
    //     (Function).
}
```

::: moniker-end
