---
title: "DeferrableEventArgs sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ce2c554ac6d959df868b80c1959a286fb0ef307
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
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