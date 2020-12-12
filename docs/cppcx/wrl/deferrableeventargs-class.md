---
description: 'Daha fazla bilgi edinin: Deferoybleeventargs sınıfı'
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
ms.openlocfilehash: 23dae7fef88ff7978790e79a0486a83815467f5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272935"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs Sınıfı

Erteleme için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Parametreler

*Teventargsarabirimi*<br/>
Ertelenmiş bir olayın bağımsız değişkenlerini bildiren arabirim türü.

*TEventArgsClass*<br/>
*Teventargsınterface* uygulayan sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

| Ad | Açıklama |
|--|--|
| [Deferraybleeventargs:: GetDeferral](#getdeferral) | Ertelenmiş olayı temsil eden [deferral](/uwp/api/windows.foundation.deferral) nesnesine bir başvuru alır. |
| [Deferraybleeventargs:: InvokeAllFinished](#invokeallfinished) | Ertelenmiş bir olayı işleyen tüm işlemenin tamamlandığını göstermek için çağırılır. |

## <a name="remarks"></a>Açıklamalar

Bu sınıfın örnekleri, ertelenmiş olaylar için olay işleyicilerine geçirilir. Şablon parametreleri, belirli bir ertelenmiş olay türü ve bu arabirimi uygulayan bir sınıf için olay bağımsız değişkenlerinin ayrıntılarını tanımlayan bir arabirimi temsil eder.

Sınıfı, ertelenmiş bir olay için bir olay işleyicisinin ilk bağımsız değişkeni olarak görünür. Ertelenmiş olayla ilgili tüm bilgileri alabileceğiniz [erteleme](/uwp/api/windows.foundation.deferral) nesnesini almak Için [GetDeferral](#getdeferral) yöntemini çağırabilirsiniz. Olay işlemeyi tamamladıktan sonra, deferral nesnesinde tamamlananı çağırmalısınız. Daha sonra, tüm ertelenmiş olayların tamamlanmasını sağlayan olay işleyicisi yönteminin sonunda [InvokeAllFinished](#invokeallfinished) ' ı çağırmanız gerekir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a> Deferraybleeventargs:: GetDeferral

Ertelenmiş olayı temsil eden [deferral](/uwp/api/windows.foundation.deferral) nesnesine bir başvuru alır.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Parametreler

*kaynaklanan*<br/>
Çağrı tamamlandığında [erteleme](/uwp/api/windows.foundation.deferral) nesnesine başvuracak bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a> Deferraybleeventargs:: InvokeAllFinished

Ertelenmiş bir olayı işleyen tüm işlemenin tamamlandığını göstermek için çağırılır.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Açıklamalar

Olay kaynağı [InvokeAll](eventsource-class.md#invokeall)çağrısından sonra bu yöntemi çağırmalısınız. Bu yöntemi çağırmak, daha fazla erteleme yapılmasını önler ve bir erteleme gerçekleştirilmediğinde tamamlama işleyicisini yürütmeye zorlar.
