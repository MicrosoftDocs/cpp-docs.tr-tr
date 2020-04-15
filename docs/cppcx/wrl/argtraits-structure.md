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
ms.openlocfilehash: 16c44d861ebbbc98fa1bffb62a00d1989c0c803c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377165"
---
# <a name="argtraits-structure"></a>ArgTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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
Herhangi `Invoke` bir yöntem imzasıyla eşleşmeyen bir ArgTraits yapısı için ad adı parametresi.

*TDelegateArayüzü*<br/>
Temsilci arabirimi.

*TArg1*<br/>
`Invoke` Yöntemin ilk bağımsız değişkeninin türü.

*TArg2*<br/>
`Invoke` Yöntemin ikinci bağımsız değişkeninin türü.

*TArg3*<br/>
`Invoke` Yöntemin üçüncü bağımsız değişkeninin türü.

*TArg4*<br/>
`Invoke` Yöntemin dördüncü bağımsız değişkeninin türü.

*TArg5*<br/>
`Invoke` Yöntemin beşinci bağımsız değişkeninin türü.

*TArg6*<br/>
`Invoke` Yöntemin altıncı bağımsız değişkeninin türü.

*TArg7*<br/>
`Invoke` Yöntemin yedinci bağımsız değişkeninin türü.

*TArg8*<br/>
`Invoke` Yöntemin sekizinci bağımsız değişkeninin türü.

*TArg9*<br/>
`Invoke` Yöntemin dokuzuncu bağımsız değişkeninin türü.

## <a name="remarks"></a>Açıklamalar

Yapı, `ArgTraits` belirtilen sayıda parametreye sahip anonim bir temsilci arabirimi ve anonim bir üye işlev bildirir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı       | Açıklama
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

### <a name="public-constants"></a>Genel Sabitler

Adı                     | Açıklama
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits::args](#args) | Temsilci arabirimi `Invoke` yöntemindeki parametre sayısını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="argtraitsargs"></a><a name="args"></a>ArgTraits::args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Açıklamalar

Temsilci arabirimi `Invoke` yöntemindeki parametre sayısını tutar. -1 eşitolduğunda, `args` `Invoke` yöntem imzası için eşleşme olamaz.
