---
title: "scheduler_ptr yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 257dcae6df4deb0a52f7dee4db98adba2b2b4f29
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
scheduler_interface* operator->() const;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);

Açık scheduler_ptr (_In_opt_ scheduler_interface * pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)
