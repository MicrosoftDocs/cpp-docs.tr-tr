---
title: Geri çağırma işlevi (Windows çalışma zamanı C++ Şablon kitaplığı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
dev_langs:
- C++
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 27d89f60f27c71cec0f158375805e3e8487fd7a6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860859"
---
# <a name="callback-function-windows-runtime-c-template-library"></a>Callback İşlevi (Windows Çalışma Zamanı C++ Şablon Kitaplığı)
Bir geri çağırma yöntemi, üye işlevi olan bir nesne oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `TDelegateInterface`  
 Bir olay gerçekleştiğinde çağrılacak temsilci arabiriminin belirten bir şablon parametresi.  
  
 `TCallback`  
 Şablon parametresi bir nesne ve onun geri çağırma üye işlevini temsil eden bir nesne türünü belirtir.  
  
 `TCallbackObject`  
 Şablon parametresi, üye işlevi bir olay gerçekleştiğinde çağrılacak yöntem nesnesini belirtir.  
  
 `TArg1`  
 Şablon parametresi ilk geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg2`  
 Şablon parametresi ikinci geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg3`  
 Şablon parametresi üçüncü geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg4`  
 Şablon parametresi dördüncü geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg5`  
 Şablon parametresi beşinci geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg6`  
 Şablon parametresi altıncı geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg7`  
 Şablon parametresi yedinci geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg8`  
 Şablon parametresi alt geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `TArg9`  
 Şablon parametresi dokuzuncu geri çağırma yöntemi bağımsız değişken türünü belirtir.  
  
 `callback`  
 Geri çağırma nesnesi ve onun üye işlevini temsil eden nesne.  
  
 `object`  
 Bir olay gerçekleştiğinde, üye işlev çağrılır nesnesi.  
  
 `method`  
 Bir olay gerçekleştiğinde çağrılacak üye işlevi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen geri çağırma yöntemi, üye işlevi olan bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir temsilci nesnesinin taban IUnknown, değil Iınspectable olmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)