---
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
ms.openlocfilehash: c13e7fec3289b66b40e44f91404a50cba7a473b1
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821720"
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
Herhangi bir `Invoke` yöntemi imzasıyla eşleşmeyen bir Argnitelikler yapısı için typeName parametresi.

*Tdelegateınterface*<br/>
Temsilci arabirimi.

*TArg1*<br/>
`Invoke` yönteminin ilk bağımsız değişkeninin türü.

*TArg2*<br/>
`Invoke` yönteminin ikinci bağımsız değişkeninin türü.

*TArg3*<br/>
`Invoke` yönteminin üçüncü bağımsız değişkeninin türü.

*TArg4*<br/>
`Invoke` yönteminin dördüncü bağımsız değişkeninin türü.

*TArg5*<br/>
`Invoke` yönteminin beşinci bağımsız değişkeninin türü.

*TArg6*<br/>
`Invoke` yönteminin altıncı bağımsız değişkeninin türü.

*TArg7*<br/>
`Invoke` yönteminin yedinci bağımsız değişkeninin türü.

*TArg8*<br/>
`Invoke` yönteminin Sekizinci bağımsız değişkeninin türü.

*TArg9*<br/>
`Invoke` yönteminin dokuzuncu bağımsız değişkeninin türü.

## <a name="remarks"></a>Açıklamalar

`ArgTraits` yapısı belirtilen bir temsilci arabirimini ve belirtilen sayıda parametreye sahip anonim bir üye işlevini bildirir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Name       | Açıklama
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

Name                     | Açıklama
------------------------ | ---------------------------------------------------------------------------------------
[Argnitelikler:: args](#args) | Bir temsilci arabiriminin `Invoke` yönteminde parametre sayısı sayısını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="args"></a>Argnitelikler:: args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Açıklamalar

Bir temsilci arabiriminin `Invoke` yönteminde parametre sayısı sayısını tutar. `args`-1 ' e eşitse, `Invoke` yöntemi imzasında eşleşme olamaz.
