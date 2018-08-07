---
title: DeferrableEventArgs sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 72f5ee2beca3a3985258b12cea9091665eb74cfa
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571268"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs Sınıfı
Gönderilemeyenler için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
```  
  
#### <a name="parameters"></a>Parametreler  
 *TEventArgsInterface*  
 Ertelenmiş olay bağımsız değişkenleri bildirir arabirim türü.  
  
 *TEventArgsClass*  
 Uygulayan sınıfa *TEventArgsInterface*.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral Metodu](../windows/deferrableeventargs-getdeferral-method.md)|Bir başvuru edinir [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) ertelenmiş bir olayı temsil eden nesne.|  
|[DeferrableEventArgs::InvokeAllFinished Metodu](../windows/deferrableeventargs-invokeallfinished-method.md)|Ertelenmiş olayı işlemek için tüm işleme tamamlandığını göstermek için çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın örnekleri, ertelenmiş olayları için olay işleyicileri geçirilir. Şablon parametreleri, belirli türde bir ertelenmiş olayı için olay bağımsız değişkenlerinin ayrıntıları tanımlayan bir arabirim ve arabirimi uygulayan bir sınıfı temsil eder.  
  
 Sınıfı, ertelenmiş bir olay için bir olay işleyicisi için ilk bağımsız değişken olarak görünür. Çağırabilirsiniz [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) almak için yöntemi [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) nesne içinden alabilirsiniz ertelenmiş olayla ilgili tüm bilgileri. Olay işleme tamamlandıktan sonra erteleme nesne üzerinde tam çağırmanız gerekir. Ardından çağırmalıdır [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) olay işleyicisi yönteminin sonunda, hangi sağlar tamamlandığında tüm ertelenmiş olayları, düzgün bir şekilde bildiriliyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)