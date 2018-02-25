---
title: "Mutex sınıfı (Standart C++ Kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: acc1d6625bcf8d76f88e8571cba34ef974856177
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="mutex-class-c-standard-library"></a>Mutex sınıfı (Standart C++ Kitaplığı)
Temsil eden bir *mutex türü*. Bu tür nesneler bir programdan karşılıklı dışlama zorlamak için kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class mutex;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[mutex](#mutex)|Oluşturan bir `mutex` nesnesi.|  
|[mutex::~mutex Destructor](#dtormutex_destructor)|Tarafından kullanılan tüm kaynakları serbest `mutex` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[lock](#lock)|İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.|  
|[native_handle](#native_handle)|Mutex tanıtıcı temsil eden uygulamaya özel tür döndürür.|  
|[try_lock](#try_lock)|Sahipliğini almayı denediğinde `mutex` engelleme olmadan.|  
|[kilidini aç](#unlock)|Serbest sahipliğini `mutex`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<mutex >  
  
 **Namespace:** std  
  
##  <a name="lock"></a>  mutex::lock
 İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.  
  
##  <a name="mutex"></a>  Mutex::mutex Oluşturucusu  
 Oluşturan bir `mutex` nesnesi kilitli değil.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="dtormutex_destructor"></a>  mutex::~mutex Destructor  
 Tarafından kullanılan tüm kaynakları serbest `mutex` nesnesi.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi çalıştığında nesne kilitliyse tanımlanmamış bir davranıştır.  
  
##  <a name="native_handle"></a>  mutex::native_handle
 Mutex tanıtıcı temsil eden uygulamaya özel tür döndürür. Mutex tanıtıcı uygulamaya özel yollarla kullanılabilir.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `native_handle_type` olarak tanımlanan bir `Concurrency::critical_section *` olarak cast `void *`.  
  
##  <a name="try_lock"></a>  Mutex::try_lock
 Sahipliğini almayı denediğinde `mutex` engelleme olmadan.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Yöntem başarıyla sahipliğini elde ederse `mutex`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı zaten sahipse `mutex`, tanımlanmamış bir davranıştır.  
  
##  <a name="unlock"></a>  mutex::unlock
 Serbest sahipliğini `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı kendi değil, `mutex`, tanımlanmamış bir davranıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



