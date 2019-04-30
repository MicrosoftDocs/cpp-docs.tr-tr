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
ms.openlocfilehash: 3fcba210d4018d22487d234b437acfee3634cec6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386141"
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

*TDelegateInterface*<br/>
Temsilci arabirim türü.

*TCallback*<br/>
Olay işleyici işlevi türü.

*argCount*<br/>
Bağımsız değişken sayısı bir `InvokeHelper` özelleştirmesi.

## <a name="remarks"></a>Açıklamalar

Bir uygulamasını sağlar `Invoke()` tabanlı yöntemini belirtilen sayı ve bağımsız değişken türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad     | Açıklama
-------- | -----------------------------------------------------------------------------
`Traits` | Her olay işleyicisi bağımsız değişken türünü tanımlayan sınıf için bir eşanlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                        | Açıklama
------------------------------------------- | -------------------------------------------------------
[Invokehelper::ınvokehelper](#invokehelper) | Yeni bir örneğini başlatır `InvokeHelper` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                            | Açıklama
------------------------------- | -----------------------------------------------------------------------------------
[Invokehelper::Invoke](#invoke) | İmzası olan, belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                                 | Açıklama
------------------------------------ | ----------------------------------------------------------
[Invokehelper::callback_](#callback) | Bir olay oluştuğunda çağrılacak olay işleyicisini temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InvokeHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="callback"></a>Invokehelper::callback_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Açıklamalar

Bir olay oluştuğunda çağrılacak olay işleyicisini temsil eder.

`TCallback` Şablon parametresi, olay işleyicisi türünü belirtir.

## <a name="invoke"></a>Invokehelper::Invoke

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
Bağımsız değişkeni 1.

*arg2*<br/>
Bağımsız değişken 2.

*Arg3*<br/>
Bağımsız değişken 3.

*Arg4*<br/>
4 bağımsız değişkeni.

*arg5*<br/>
Bağımsız değişken 5.

*arg6*<br/>
Bağımsız değişken 6.

*arg7*<br/>
Bağımsız değişken 7.

*arg8*<br/>
8 bağımsız değişkeni.

*arg9*<br/>
Bağımsız değişken 9.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

İmzası olan, belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.

## <a name="invokehelper"></a>Invokehelper::ınvokehelper

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parametreler

*geri çağırma*<br/>
Bir olay işleyicisi.

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `InvokeHelper` sınıfı.

`TCallback` Şablon parametresi, olay işleyicisi türünü belirtir.
