---
title: AgileEventSource sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: 095c61dcef208028bf1c0f4b3443ba10110da8ed
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025872"
---
# <a name="agileeventsource-class"></a>AgileEventSource sınıfı

Herhangi bir iş parçacığından erişilebilir bir bileşen olan Çevik bir bileşen tarafından gerçekleştirilen bir olayı temsil eder. Devralınan [EventSource](eventsource-class.md) ve geçersiz kılmaları `Add` Çevik olayı çağırmak nasıl seçeneklerini belirtmek için bir ek tür parametresi ile üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename TDelegateInterface,
    typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>
>
class AgileEventSource :
    public Microsoft::WRL::EventSource<
        TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Parametreler

*TDelegateInterface*<br/>
Bir olay işleyicisi temsil eden bir temsilci için arabirim.

*TEventSourceOptions*<br/>
Bir [Invokemodeoptions](invokemodeoptions-structure.md) olan invokeMode alanı yapıda `InvokeMode::StopOnFirstError` veya `InvokeMode::FireAll`.

## <a name="remarks"></a>Açıklamalar

Windows çalışma zamanı bileşenlerinde büyük çoğunluğu, Çevik bileşenleridir. Daha fazla bilgi için [iş parçacığı oluşturma ve sıralama (C + +/ CX)](../../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::WRL

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AgileEventSource::Add yöntemi](#add)|Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen Çevik olay işleyicisi **AgileEventSource** nesne.|

## <a name="add"></a> AgileEventSource::Add yöntemi

Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisi [EventSource](eventsource-class.md) nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*delegateInterface*<br/>
Bir olay işleyicisi temsil eden bir temsilci nesnesi için arabirim.

*Belirteç*<br/>
Bu işlem tamamlandığında, olayı temsil eden bir işleyici. Parametre olarak bu belirteci kullanmasına `Remove()` olay işleyicisi atmak için yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)