---
title: scheduler_ptr yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd15238408f90f268a5fea96635136077c795779
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059114"
---
# <a name="schedulerptr-structure"></a>scheduler_ptr yapısı
Bir işaretçi için bir Zamanlayıcı'yı temsil eder. Shared_ptr veya yalnızca bir düz başvuru ham işaretçiyi kullanarak paylaşılan bir kullanım ömrünün belirtilmesine izin vermek için bu sınıfı var.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::scheduler_ptr](#ctor)|Fazla Yüklendi. Bir zamanlayıcı işaretçisi shared_ptr'den zamanlayıcıya oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::get](#get)|Zamanlayıcıya ham işaretçiyi döndürür|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::operator bool](#operator_bool)|Zamanlayıcı işaretçisinin null dışında değer olup olmadığını test edin|  
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Bir işaretçi gibi davranma|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplinterface.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="get"></a>  scheduler_ptr::GET yöntemi  
 Zamanlayıcıya ham işaretçiyi döndürür  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_bool"></a>  scheduler_ptr::operator bool   
 Zamanlayıcı işaretçisinin null dışında değer olup olmadığını test edin  
  
'''operator bool() const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
scheduler_interface * işleci (const) ->;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
Açık scheduler_ptr (std::shared_ptr < scheduler_interface > Zamanlayıcı);

Açık scheduler_ptr (_In_opt_ pScheduler scheduler_interface *);
```  
  
### Parameters  
*scheduler*<br/>
The scheduler to convert.

*pScheduler*<br/>
The scheduler pointer to convert.
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)
