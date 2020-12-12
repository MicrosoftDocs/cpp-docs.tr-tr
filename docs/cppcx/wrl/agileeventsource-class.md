---
description: ': AgileEventSource sınıfı hakkında daha fazla bilgi'
title: AgileEventSource sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: d2e48d59d8706eb65828bc5b77ffaf9d4158bc1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204582"
---
# <a name="agileeventsource-class"></a>AgileEventSource sınıfı

Herhangi bir iş parçacığından erişilebilen bir bileşen olan çevik bir bileşen tarafından oluşturulan bir olayı temsil eder. [EventSource](eventsource-class.md) 'tan devralır ve `Add` çevik olayını çağırma seçeneklerini belirtmek için ek bir tür parametresiyle üye işlevini geçersiz kılar.

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

*Tdelegateınterface*<br/>
Bir olay işleyicisini temsil eden bir temsilci için arabirim.

*TEventSourceOptions*<br/>
Invokemode alanı veya olarak ayarlanan [ınvokemodeoptions](invokemodeoptions-structure.md) yapısı `InvokeMode::StopOnFirstError` `InvokeMode::FireAll` .

## <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı bileşenlerin büyük çoğunluğu çevik bileşenlerdir. Daha fazla bilgi için bkz. [Threading and Marshal (C++/CX)](../../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[AgileEventSource:: Add yöntemi](#add)|Belirtilen temsilci arabirimiyle temsil edilen çevik olay işleyicisini geçerli **Agileeventsource** nesnesinin olay işleyicileri kümesine ekler.|

## <a name="agileeventsourceadd-method"></a><a name="add"></a> AgileEventSource:: Add yöntemi

Belirtilen temsilci arabirimiyle temsil edilen olay işleyicisini geçerli [EventSource](eventsource-class.md) nesnesinin olay işleyicileri kümesine ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*Delegateınterface*<br/>
Bir olay işleyicisini temsil eden bir temsilci nesnesine arabirim.

*simgesinde*<br/>
Bu işlem tamamlandığında, olayı temsil eden bir tanıtıcı. `Remove()`Olay işleyicisini atmak için bu belirteci yönteme parametre olarak kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
