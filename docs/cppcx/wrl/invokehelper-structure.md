---
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
ms.openlocfilehash: 9cb4e166628a6b5e7671494446d467e73c9f8cc3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371381"
---
# <a name="invokehelper-structure"></a>InvokeHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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

*TDelegateArayüzü*<br/>
Temsilci arabirimi türü.

*TCallback*<br/>
Olay işleyicisi işlevinin türü.

*argCount*<br/>
Uzmanlık alanındaki `InvokeHelper` bağımsız değişkenlerin sayısı.

## <a name="remarks"></a>Açıklamalar

Belirtilen sayı ve `Invoke()` bağımsız değişken türüne dayalı yöntemin uygulanmasını sağlar.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı     | Açıklama
-------- | -----------------------------------------------------------------------------
`Traits` | Her olay işleyicisi bağımsız değişkeninin türünü tanımlayan sınıfın eşanlamlısı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                        | Açıklama
------------------------------------------- | -------------------------------------------------------
[InvokeHelper::InvokeHelper](#invokehelper) | `InvokeHelper` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                            | Açıklama
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper::Invoke](#invoke) | İmzası belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Adı                                 | Açıklama
------------------------------------ | ----------------------------------------------------------
[InvokeHelper::callback_](#callback) | Bir olay gerçekleştiğinde çağırılabilmek için olay işleyicisini temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InvokeHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="invokehelpercallback_"></a><a name="callback"></a>InvokeHelper::callback_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Açıklamalar

Bir olay gerçekleştiğinde çağırılabilmek için olay işleyicisini temsil eder.

Şablon `TCallback` parametresi olay işleyicisinin türünü belirtir.

## <a name="invokehelperinvoke"></a><a name="invoke"></a>InvokeHelper::Invoke

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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
Argüman 4.

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

S_OK başarılı olursa; aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İmzası belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a>InvokeHelper::InvokeHelper

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parametreler

*Geri*<br/>
Olay işleyicisi.

### <a name="remarks"></a>Açıklamalar

`InvokeHelper` sınıfının yeni bir örneğini başlatır.

Şablon `TCallback` parametresi olay işleyicisinin türünü belirtir.
