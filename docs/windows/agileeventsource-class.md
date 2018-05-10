---
title: AgileEventSource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58eb96e3a0268d3ba70b60d9c315e935e19485f3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="agileeventsource-class"></a>AgileEventSource sınıfı

Herhangi bir iş parçacığından erişilebilir bir bileşen olan bir Çevik bileşen tarafından gerçekleştirilen bir olayı temsil eder. Öğesinden devralınan [EventSource](eventsource-class.md) ve geçersiz kılmalar `Add` üye işlevi Çevik olay çağırmak nasıl seçeneklerini belirtmek için ek türü parametreye sahip.

## <a name="syntax"></a>Sözdizimi

```
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Parametreler  
 `TDelegateInterface`  

 Olay işleyici temsil eden bir temsilci için arabirim.

 `TEventSourceOptions`  
 Bir [InvokeModeOptions](invokemodeoptions-structure.md) , invokeMode alanı ayarlanmış yapıda `InvokeMode::StopOnFirstError` veya `InvokeMode::FireAll`.

## <a name="remarks"></a>Açıklamalar

Windows çalışma zamanı bileşenleri çoğunluğu, Çevik bileşenleridir. Daha fazla bilgi için bkz: [iş parçacığı oluşturma ve sıralama (C + +/ CX)](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

 `EventSource``AgileEventSource`

## <a name="requirements"></a>Gereksinimler

 **Başlık:** event.h

 **Namespace:** Microsoft::WRL

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AgileEventSource::Add yöntemi](#add)|Geçerli AgileEventSource nesnesi için olay işleyicileri kümesine tarafından belirtilen temsilci arabirimi temsil Çevik olay işleyicisi ekler.|

## <a name="add"></a> AgileEventSource::Add yöntemi

Olay işleyicileri geçerli kümesine tarafından belirtilen temsilci arabirimi temsil olay işleyicisi ekler [EventSource](eventsource-class.md) nesnesi.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*delegateInterface*

Olay işleyici temsil eden bir temsilci nesnesi için arabirim.

*belirteç* bu işlem tamamlandığında, olay temsil eden bir tanıtıcı. Olay işleyicisi atmak için Remove() kullanılmasına yöntemi için parametre olarak bu belirteci kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.


## <a name="see-also"></a>Ayrıca Bkz.

 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
