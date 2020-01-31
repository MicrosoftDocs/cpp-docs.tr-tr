---
title: Callback Işlevi (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
ms.openlocfilehash: 10fb053ed97aaca0f4a31e3843d96aa194d8949d
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821694"
---
# <a name="callback-function-wrl"></a>Callback Işlevi (WRL)

Üye işlevi bir geri çağırma yöntemi olan bir nesne oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
   typename TDelegateInterface,
   typename TCallback
>
ComPtr<TDelegateInterface> Callback(
   TCallbackcallback
);
template<
   typename TDelegateInterface,
   typename TCallbackObject
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)()
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
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
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8,
   TArg9)
);
```

### <a name="parameters"></a>Parametreler

*Tdelegateınterface*<br/>
Bir olay gerçekleştiğinde çağrılacak temsilcinin arabirimini belirten bir şablon parametresi.

*TCallback*<br/>
Bir nesneyi ve geri çağırma üye işlevini temsil eden nesnenin türünü belirten bir şablon parametresi.

*TCallbackObject*<br/>
Bir olay gerçekleştiğinde, üye işlevi çağırma yöntemi olan nesneyi belirten bir şablon parametresi.

*TArg1*<br/>
İlk geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg2*<br/>
İkinci geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg3*<br/>
Üçüncü geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg4*<br/>
Dördüncü geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg5*<br/>
Beşinci geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg6*<br/>
Altıncı geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg7*<br/>
Yedinci geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg8*<br/>
Sekizinci geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*TArg9*<br/>
Dokuzuncu geri çağırma yöntemi bağımsız değişkeninin türünü belirten bir şablon parametresi.

*callback*<br/>
Geri çağırma nesnesini ve onun üye işlevini temsil eden nesne.

*object*<br/>
Bir olay gerçekleştiğinde üye işlevi çağrılan nesne.

*method*<br/>
Bir olay gerçekleştiğinde çağrılacak üye işlevi.

## <a name="return-value"></a>Dönüş Değeri

Üye işlevi belirtilen geri çağırma yöntemi olan nesne.

## <a name="remarks"></a>Açıklamalar

Temsilci nesnesinin temeli, `IInspectable`değil `IUnknown`olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)