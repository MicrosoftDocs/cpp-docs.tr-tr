---
title: DeferrableEventArgs Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 066918bf2c76b17f06871ee08be674be9b36c161
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032466"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs Sınıfı

Ertelemeler için olay bağımsız değişkeni türleri için kullanılan şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Parametreler

*TEventArgsArayüz*<br/>
Ertelenmiş bir olay için bağımsız değişkenleri bildiren arabirim türü.

*TEventArgsSınıf*<br/>
*TEventArgsInterface*uygulayan sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

| Adı | Açıklama |
|--|--|
| [ErtelenebilirEventArgs::GetDeferral](#getdeferral) | Ertelenmiş bir olayı temsil eden [Erteleme](/uwp/api/windows.foundation.deferral) nesnesine bir başvuru alır. |
| [ErtelenebilirEventArgs::InvokeAllFinished](#invokeallfinished) | Ertelenmiş bir olayı işlemek için tüm işlemlerin tamamladığını belirtmek için çağrıldı. |

## <a name="remarks"></a>Açıklamalar

Bu sınıfın örnekleri ertelenmiş olaylar için olay işleyicilerine aktarılır. Şablon parametreleri, belirli bir ertelenmiş olay türü için olay bağımsız değişkenlerinin ayrıntılarını tanımlayan bir arabirimi ve bu arabirimi uygulayan bir sınıfı temsil eder.

Sınıf, ertelenmiş bir olay için bir olay işleyicisi için ilk bağımsız değişken olarak görünür. Ertelenmiş olay la ilgili tüm bilgileri alabileceğiniz [Erteleme](/uwp/api/windows.foundation.deferral) nesnesini almak için [GetDeferral](#getdeferral) yöntemini arayabilirsiniz. Olay işlemeyi tamamladıktan sonra, Erteleme nesnesi üzerinde Tamam'ı aramalısınız. Daha sonra, tüm ertelenmiş olayların tamamlanmasının düzgün bir şekilde iletilmesini sağlayan olay işleyicisi yönteminin sonunda [InvokeAllFinished'u](#invokeallfinished) aramalısınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a>ErtelenebilirEventArgs::GetDeferral

Ertelenmiş bir olayı temsil eden [Erteleme](/uwp/api/windows.foundation.deferral) nesnesine bir başvuru alır.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Parametreler

*Sonuç*<br/>
Çağrı tamamlandığında [Erteleme](/uwp/api/windows.foundation.deferral) nesnesi başvurur bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a>ErtelenebilirEventArgs::InvokeAllFinished

Ertelenmiş bir olayı işlemek için tüm işlemlerin tamamladığını belirtmek için çağrıldı.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Açıklamalar

Olay kaynağı [InvokeAll'ı](eventsource-class.md#invokeall)aradıktan sonra bu yöntemi aramalısınız. Bu yöntemin çağrılması, daha fazla erteleme alınmasını önler ve erteleme alınmadığı takdirde tamamlama işleyicisini yürütmeye zorlar.
