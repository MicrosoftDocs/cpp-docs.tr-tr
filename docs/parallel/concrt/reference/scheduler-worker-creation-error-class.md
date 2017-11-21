---
title: "scheduler_worker_creation_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
dev_langs: C++
helpviewer_keywords: scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a628d0ce3d85a2bdcae9c7d25550cbd36386e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error Sınıfı
Bu sınıf eşzamanlılık çalışma zamanı'nda çalışan yürütme bağlamı oluşturmak için bir hatadan dolayı oluşturulan bir özel açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scheduler_worker_creation_error](#ctor)|Fazla Yüklendi. Oluşturan bir `scheduler_worker_creation_error` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 İşletim sistemi içinde eşzamanlılık çalışma zamanı yürütme bağlamı gelen oluşturmak için bir çağrı başarısız olduğunda bu durum genellikle atılır. Yürütme bağlamı görevleri eşzamanlılık çalışma zamanı'nda yürütme iş parçacığı ' dir. Win32 yöntemine bir çağrı normalde döndürülen hata kodu `GetLastError` türünde bir değer dönüştürülür `HRESULT` ve temel sınıf yöntemi kullanılarak alınıp `get_error_code`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>scheduler_worker_creation_error 

 Oluşturan bir `scheduler_worker_creation_error` nesnesi.  
  
```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
 `_Hresult`  
 `HRESULT` Özel duruma neden hata değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
