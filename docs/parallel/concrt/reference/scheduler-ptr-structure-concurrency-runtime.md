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
ms.openlocfilehash: 672e4a0dd5f66ab613dde8877915c799d6c4b2f4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="schedulerptr-structure"></a>scheduler_ptr yapısı
Bir işaretçi bir zamanlayıcı temsil eder. Bu sınıf izin vermek için mevcut ham işaretçi kullanarak shared_ptr veya yalnızca düz başvurusu kullanarak paylaşılan bir yaşam süresi'nin belirtimine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::scheduler_ptr](#ctor)|Fazla Yüklendi. Bir zamanlayıcı işaretçi Zamanlayıcı ' shared_ptr oluşturur|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::get](#get)|Zamanlayıcı'ham işaretçi döndürür|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_ptr::operator bool](#operator_bool)|Zamanlayıcı işaretçisi null olmayan olup olmadığını sınamak|  
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Bir işaretçi gibi davranır|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplinterface.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="get"></a>  scheduler_ptr::GET yöntemi  
 Zamanlayıcı'ham işaretçi döndürür  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_bool"></a>  scheduler_ptr::operator bool   
 Zamanlayıcı işaretçisi null olmayan olup olmadığını sınamak  
  
''' işleci bool() const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
scheduler_interface * işleci () const ->;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
Açık scheduler_ptr (std::shared_ptr < scheduler_interface > Zamanlayıcı);

Açık scheduler_ptr (_In_opt_ scheduler_interface * pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)
