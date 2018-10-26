---
title: DeferrableEventArgs sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f5c117d0d65f86e4f4b69011457e166b6440820
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081569"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs Sınıfı

Gönderilemeyenler için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Parametreler

*TEventArgsInterface*<br/>
Ertelenmiş olay bağımsız değişkenleri bildirir arabirim türü.

*TEventArgsClass*<br/>
Uygulayan sınıfa *TEventArgsInterface*.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[DeferrableEventArgs::GetDeferral](#getdeferral)             | Bir başvuru edinir [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) ertelenmiş bir olayı temsil eden nesne.
[Deferrableeventargs::ınvokeallfinished](#invokeallfinished) | Ertelenmiş olayı işlemek için tüm işleme tamamlandığını göstermek için çağrılır.

## <a name="remarks"></a>Açıklamalar

Bu sınıfın örnekleri, ertelenmiş olayları için olay işleyicileri geçirilir. Şablon parametreleri, belirli türde bir ertelenmiş olayı için olay bağımsız değişkenlerinin ayrıntıları tanımlayan bir arabirim ve arabirimi uygulayan bir sınıfı temsil eder.

Sınıfı, ertelenmiş bir olay için bir olay işleyicisi için ilk bağımsız değişken olarak görünür. Çağırabilirsiniz [GetDeferral](#getdeferral) almak için yöntemi [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) nesne içinden alabilirsiniz ertelenmiş olayla ilgili tüm bilgileri. Olay işleme tamamlandıktan sonra erteleme nesne üzerinde tam çağırmanız gerekir. Ardından çağırmalıdır [InvokeAllFinished](#invokeallfinished) olay işleyicisi yönteminin sonunda, hangi sağlar tamamlandığında tüm ertelenmiş olayları, düzgün bir şekilde bildiriliyor.

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::WRL

## <a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

Bir başvuru edinir [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) ertelenmiş bir olayı temsil eden nesne.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Parametreler

*Sonuç*<br/>
Bakacağınız bir işaretçi [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) çağrısı tamamlandığında nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="invokeallfinished"></a>Deferrableeventargs::ınvokeallfinished

Ertelenmiş olayı işlemek için tüm işleme tamamlandığını göstermek için çağrılır.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Açıklamalar

Olay kaynağı çağrılarını sonra bu yöntemi çağırmanız gerekir [Invokeall](../windows/eventsource-invokeall-method.md). Bu yöntemi çağırmadan, daha fazla gönderilemeyenler gerçekleştirilmesini önler ve hiçbir gönderilemeyenler alınan, yürütülecek tamamlama işleyicisine zorlar.
