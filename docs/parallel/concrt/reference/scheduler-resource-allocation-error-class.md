---
title: "scheduler_resource_allocation_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b84533fb578ed0e2988f88420d46aeb2ed7c9657
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error Sınıfı
Bu sınıf eşzamanlılık çalışma zamanı kritik kaynak edinmeye bir hatadan dolayı oluşturulan bir özel açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_resource_allocation_error](#ctor)|Fazla Yüklendi. Oluşturan bir `scheduler_resource_allocation_error` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_error_code](#get_error_code)|Özel duruma neden hata kodunu döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı içinde işletim sisteminden çağrısı başarısız olduğunda bu durum genellikle atılır. Win32 yöntemine bir çağrı normalde döndürülen hata kodu `GetLastError` türünde bir değer dönüştürülür `HRESULT` ve kullanılarak alınabilir `get_error_code` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="get_error_code"></a> get_error_code 

 Özel duruma neden hata kodunu döndürür.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `HRESULT` Özel duruma neden hata değeri.  
  
##  <a name="ctor"></a> scheduler_resource_allocation_error 

 Oluşturan bir `scheduler_resource_allocation_error` nesnesi.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
 `_Hresult`  
 `HRESULT` Özel duruma neden hata değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
