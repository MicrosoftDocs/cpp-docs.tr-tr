---
description: 'Daha fazla bilgi edinin: Argnitelikler yapısı'
title: ArgTraits Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: b44cd1ff8d5aa4355385629cc08321dfe353e24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175917"
---
# <a name="argtraits-structure"></a>ArgTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Parametreler

*TMemberFunction*<br/>
Herhangi bir yöntem imzasıyla eşleşmeyen bir Argnitelikler yapısı için typeName parametresi `Invoke` .

*Tdelegateınterface*<br/>
Temsilci arabirimi.

*TArg1*<br/>
Metodun ilk bağımsız değişkeninin türü `Invoke` .

*TArg2*<br/>
Metodun ikinci bağımsız değişkeninin türü `Invoke` .

*TArg3*<br/>
Metodun üçüncü bağımsız değişkeninin türü `Invoke` .

*TArg4*<br/>
Metodun dördüncü bağımsız değişkeninin türü `Invoke` .

*TArg5*<br/>
Metodun beşinci bağımsız değişkeninin türü `Invoke` .

*TArg6*<br/>
Metodun altıncı bağımsız değişkeninin türü `Invoke` .

*TArg7*<br/>
Metodun yedinci bağımsız değişkeninin türü `Invoke` .

*TArg8*<br/>
Metodun Sekizinci bağımsız değişkeninin türü `Invoke` .

*TArg9*<br/>
Metodun dokuzuncu bağımsız değişkeninin türü `Invoke` .

## <a name="remarks"></a>Açıklamalar

`ArgTraits`Yapı belirtilen bir temsilci arabirimini ve belirtilen sayıda parametreye sahip anonim bir üye işlevini bildirir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad       | Açıklama
---------- | ----------------------
`Arg1Type` | TArg1 için typedef.
`Arg2Type` | TArg2 için typedef.
`Arg3Type` | TArg3 için typedef.
`Arg4Type` | TArg4 için typedef.
`Arg5Type` | TArg5 için typedef.
`Arg6Type` | TArg6 için typedef.
`Arg7Type` | TArg7 için typedef.
`Arg8Type` | TArg8 için typedef.
`Arg9Type` | TArg9 için typedef.

### <a name="public-constants"></a>Genel sabitler

Ad                     | Açıklama
------------------------ | ---------------------------------------------------------------------------------------
[Argnitelikler:: args](#args) | `Invoke`Bir temsilci arabiriminin yöntemindeki parametre sayısının sayısını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="argtraitsargs"></a><a name="args"></a> Argnitelikler:: args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Açıklamalar

`Invoke`Bir temsilci arabiriminin yöntemindeki parametre sayısının sayısını tutar. `args`Eşittir-1 olduğunda, yöntem imzası için eşleşme olamaz `Invoke` .
