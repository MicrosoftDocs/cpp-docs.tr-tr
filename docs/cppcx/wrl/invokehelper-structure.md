---
description: 'Daha fazla bilgi edinin: InvokeHelper yapısı'
title: InvokeHelper Yapısı
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 0b9bb8abb59cce5a3c25d795d0946ffbe88d0076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299026"
---
# <a name="invokehelper-structure"></a>InvokeHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>Parametreler

*Tdelegateınterface*<br/>
Temsilci arabirim türü.

*TCallback*<br/>
Olay işleyicisi işlevinin türü.

*argCount*<br/>
Bir özelleşmenin bağımsız değişken sayısı `InvokeHelper` .

## <a name="remarks"></a>Açıklamalar

`Invoke()`Yöntemin, belirtilen sayı ve bağımsız değişken türüne göre bir uygulamasını sağlar.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad     | Açıklama
-------- | -----------------------------------------------------------------------------
`Traits` | Her olay işleyicisi bağımsız değişkeninin türünü tanımlayan sınıf için bir eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                        | Açıklama
------------------------------------------- | -------------------------------------------------------
[InvokeHelper:: InvokeHelper](#invokehelper) | `InvokeHelper` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                            | Açıklama
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper:: Invoke](#invoke) | İmzasında belirtilen sayıda bağımsız değişken bulunan olay işleyicisini çağırır.

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                                 | Açıklama
------------------------------------ | ----------------------------------------------------------
[InvokeHelper:: callback_](#callback) | Bir olay gerçekleştiğinde çağrılacak olay işleyicisini temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InvokeHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="invokehelpercallback_"></a><a name="callback"></a> InvokeHelper:: callback_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Açıklamalar

Bir olay gerçekleştiğinde çağrılacak olay işleyicisini temsil eder.

`TCallback`Şablon parametresi, olay işleyicisinin türünü belirtir.

## <a name="invokehelperinvoke"></a><a name="invoke"></a> InvokeHelper:: Invoke

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>Parametreler

*arg1*<br/>
Bağımsız değişken 1.

*arg2*<br/>
Bağımsız değişken 2.

*arg3*<br/>
Bağımsız değişken 3.

*arg4*<br/>
Bağımsız değişken 4.

*arg5*<br/>
Bağımsız değişken 5.

*arg6*<br/>
Bağımsız değişken 6.

*arg7*<br/>
Bağımsız değişken 7.

*arg8*<br/>
Bağımsız değişken 8.

*arg9*<br/>
Bağımsız değişken 9.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İmzasında belirtilen sayıda bağımsız değişken bulunan olay işleyicisini çağırır.

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a> InvokeHelper:: InvokeHelper

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parametreler

*callback*<br/>
Bir olay işleyicisi.

### <a name="remarks"></a>Açıklamalar

`InvokeHelper` sınıfının yeni bir örneğini başlatır.

`TCallback`Şablon parametresi, olay işleyicisinin türünü belirtir.
