---
title: critical_section sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0287c74155e7b4fe827bb015b43cfca3384f3b1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="criticalsection-class"></a>critical_section Sınıfı
Eşzamanlılık Çalışma zamanı açıkça farkındadır yeniden girme olmayan mutex.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class critical_section;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`native_handle_type`|Bir başvuru bir `critical_section` nesnesi.|  
  
### <a name="public-classes"></a>Genel sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[critical_section::scoped_lock sınıfı](#critical_section__scoped_lock_class)|Bir özel durum güvenli RAII için sarmalayıcı bir `critical_section` nesnesi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[critical_section](#ctor)|Yeni kritik bir bölüm oluşturur.|  
|[~ critical_section yok Edicisi](#dtor)|Önemli bir bölümü yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[lock](#lock)|Bu kritik bölüm edinir.|  
|[native_handle](#native_handle)|Varsa bir platform özel yerel tanıtıcı döndürür.|  
|[try_lock](#try_lock)|Engellenmeden kilidi dener.|  
|[try_lock_for](#try_lock_for)|Belirli bir milisaniye sayısı için engellenmeden kilidi dener.|  
|[kilidini aç](#unlock)|Kritik bölüm kilidini açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `critical_section`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> critical_section 

 Yeni kritik bir bölüm oluşturur.  
  
```
critical_section();
```  
  
##  <a name="dtor"></a> ~ critical_section 

 Önemli bir bölümü yok eder.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi çalıştığında kilidi artık tutulan beklenir. Kilidiyle destruct için önemli bir bölümü izin verme hala sonuçları tanımsız davranışını tutulur.  
  
##  <a name="lock"></a> kilitleme 

 Bu kritik bölüm edinir.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Faydalanmak genellikle güvenlidir [scoped_lock](#critical_section__scoped_lock_class) edinmeli ve yayın için yapı bir `critical_section` bir özel durum nesnesinde güvenli yolu.  
  
 Kilit çağıran bağlamını tarafından zaten tutulursa bir [improper_lock](improper-lock-class.md) özel durum.  
  
##  <a name="native_handle"></a> native_handle 

 Varsa bir platform özel yerel tanıtıcı döndürür.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kritik bölüm referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 A `critical_section` nesne platform belirli yerel işleyici Windows işletim sistemi ile ilişkili değil. Yöntem yalnızca nesnesine bir başvuru döndürür.  
  
##  <a name="critical_section__scoped_lock_class"></a>  critical_section::scoped_lock sınıfı  
 Bir özel durum güvenli RAII için sarmalayıcı bir `critical_section` nesnesi.  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock 

 Oluşturan bir `scoped_lock` nesne ve edinir `critical_section` nesnesi geçirildi `_Critical_section` parametresi. Kritik bölüm başka bir iş parçacığı tarafından tutulan bu çağrıyı engeller.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Critical_section`  
 Kilitlemek için kritik bölüm.  
  
##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock 

 Bozar bir `scoped_lock` nesne ve kurucusunda sağlanan kritik bölüm serbest bırakır.  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a> try_lock 

 Engellenmeden kilidi dener.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit aldıysanız değeri `true`; Aksi halde değer `false`.  
  
##  <a name="try_lock_for"></a> try_lock_for 

 Belirli bir milisaniye sayısı için engellenmeden kilidi dener.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Timeout`  
 Zaman aşımına uğramadan önce beklenmesi gereken milisaniye sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit aldıysanız değeri `true`; Aksi halde değer `false`.  
  
##  <a name="unlock"></a> kilidini aç 

 Kritik bölüm kilidini açar.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [reader_writer_lock Sınıfı](reader-writer-lock-class.md)
