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
ms.openlocfilehash: 15be5c26e5d4e976eaba7b6b24e1bf4f62c53aca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872104"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs Sınıfı
Deferrals için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TEventArgsInterface`  
 Ertelenmiş olay bağımsız değişkenleri bildirir arabirimi türü.  
  
 `TEventArgsClass`  
 Uygulayan sınıfa `TEventArgsInterface`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral Metodu](../windows/deferrableeventargs-getdeferral-method.md)|Bir başvuru edinir [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) ertelenmiş bir olayı temsil eden nesne.|  
|[DeferrableEventArgs::InvokeAllFinished Metodu](../windows/deferrableeventargs-invokeallfinished-method.md)|Ertelenmiş olayını işlemek için tüm işleme tamamlandığını göstermek için çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın örnekleri, ertelenmiş olayları için olay işleyicilerine geçirilir. Şablon parametreleri ertelenmiş olay belirli bir tür için olay bağımsız değişkenlerinin ayrıntıları tanımlayan bir arabirim ve arabirimi uygulayan bir sınıfı temsil eder.  
  
 Sınıfı, ertelenmiş olayı için bir olay işleyicisi için ilk bağımsız değişken olarak görünür. Çağırabilirsiniz [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) almak için yöntemi [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) içinden alabilirsiniz ertelenmiş olayla ilgili tüm bilgileri nesnesi. Olay işleme tamamladıktan sonra tam erteleme nesnesinde çağırmalıdır. Ardından çağırmalıdır [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) olay işleyicisi yöntemi sonunda da sağlar tüm Ertelenmiş Olaylar tamamlanmasından düzgün bildirilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)