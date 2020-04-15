---
title: MatchEventStackInmemberFonksiyonu
description: C++ Build Insights SDK MatchEventStackInMemberFunction fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28842a02e7edc2e00266d8c7941798f4ce714ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323879"
---
# <a name="matcheventstackinmemberfunction"></a>MatchEventStackInmemberFonksiyonu

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `MatchEventStackInMemberFunction` bir üye işlevin parametre listesiyle açıklanan belirli bir olay hiyerarşisi ile olay yığınını eşleştirmek için kullanılır. Eşleşen hiyerarşiler daha fazla işleme için üye işlevine iletilir. Olaylar, olay yığınları ve hiyerarşiler hakkında daha fazla bilgi edinmek için [olay tablosuna](../event-table.md)bakın.

## <a name="syntax"></a>Sözdizimi

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
Üye işlevi içeren tür.

*Geri Dönüş*\
Üye işlevin dönüş türü.

*T1*, ..., *T10*\
Eşleşmek için olay hiyerarşisini açıklayan türleri.

*TExtraParams*\
Üye işlev tarafından kabul edilen ek parametrelerin türleri ve olay hiyerarşisi türleri.

*TExtraArgs*\
Geçirilen ek bağımsız değişkenlerin `MatchEventStackInMemberFunction`türleri.

*eventStack*\
T1 ile *T10* arasında açıklanan olay türü *T10*hiyerarşisi ile eşleşecek olay yığını.

*objectPtr*\
*Üye Func'ın* çağrıldığı bir nesneye işaretçi.

*üyeFunc*\
Eşleşmek için olay türü hiyerarşisini açıklayan üye işlev.

*extraArgs*\
Olay türü hiyerarşi parametreleri ile birlikte *üyeFunc* mükemmel iletilir olsun bağımsız değişkenler.

### <a name="return-value"></a>Dönüş Değeri

Eşleştirme başarılı veya **yanlış** başka bir şekilde **doğru** bir **bool** değeri.

## <a name="remarks"></a>Açıklamalar

*eventStack'teki* son olay her zaman maç için olay türü hiyerarşisindeki son girişle eşleşir. Olay türü hiyerarşisindeki diğer tüm türler, aynı sırada olmaları koşuluyla, son uçağı dışında *eventStack'* teki herhangi bir konuma uYağabilir.

*T1* ile *T10* parametreleri için kullanılacak olay *türleri, yakalama sınıfları*listesinden seçilir. Olayların listesi ve bunları eşleştirmek için kullanabileceğiniz yakalama sınıfları için [olay tablosuna](../event-table.md)bakın.

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
