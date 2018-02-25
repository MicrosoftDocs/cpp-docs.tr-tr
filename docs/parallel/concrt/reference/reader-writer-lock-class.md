---
title: "reader_writer_lock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75bea63c6e2f73ebd58434874758c4f20444958a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="readerwriterlock-class"></a>reader_writer_lock Sınıfı
Yalnızca dönmesini yerel yazıcı tercih Okuyucu-Yazıcı sırası tabanlı kilidi. Kilidi okuyucular yazıcılarının sürekli yükü altında starves ve daha önce yazıcılarının - ilk (FIFO) erişimi verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-classes"></a>Genel sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[reader_writer_lock::scoped_lock Class](#scoped_lock_class)|Almak üzere kullanılabilecek bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` nesneleri yazan kilitleyin.|  
|[reader_writer_lock::scoped_lock_read Class](#scoped_lock_read_class)|Almak üzere kullanılabilecek bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` nesneleri okuyucu olarak kilitleyin.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|Yeni bir oluşturur `reader_writer_lock` nesnesi.|  
|[~ reader_writer_lock yok Edicisi](#dtor)|Bozar `reader_writer_lock` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[lock](#lock)|Okuyucu-Yazıcı kilit bir yazıcı alır.|  
|[lock_read](#lock_read)|Okuyucu-Yazıcı kilit okuyucu olarak alır. Yazarları varsa, etkin okuyucular bunlar yapılır kadar beklemek zorunda. Okuyucu sadece kilidi ilgi kaydeder ve serbest yazarlar için bekler.|  
|[try_lock](#try_lock)|Okuyucu-Yazıcı yazan engellenmeden kilidi dener.|  
|[try_lock_read](#try_lock_read)|Okuyucu-Yazıcı okuyucu olarak engellenmeden kilidi dener.|  
|[kilidini aç](#unlock)|Kim, okuyucu veya yazan kilitli üzerinde temel Okuyucu-Yazıcı kilitleme kilidini açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `reader_writer_lock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="lock"></a> kilitleme 

 Okuyucu-Yazıcı kilit bir yazıcı alır.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Faydalanmak genellikle güvenlidir [scoped_lock](#scoped_lock_class) edinmeli ve yayın için yapı bir `reader_writer_lock` nesnesi yazan bir özel durum olarak güvenli yolu.  
  
 Kilidi bir yazıcı denemesinden sonra yazıcılarının başarıyla alındı ve kilidi serbest kadar gelecekteki tüm okuyucular engeller. Bu kilit yazıcılarının ağırlıklı ve okuyucular yazıcılarının sürekli yükü altında tamamen Kaynaksız bırakabilir.  
  
 Böylece kilit çıkış yazıcısı satırda sonraki yazan yayımları yazıcılarının zincirlenir.  
  
 Kilit çağıran bağlamını tarafından zaten tutulursa bir [improper_lock](improper-lock-class.md) özel durum.  
  
##  <a name="lock_read"></a> lock_read 

 Okuyucu-Yazıcı kilit okuyucu olarak alır. Yazarları varsa, etkin okuyucular bunlar yapılır kadar beklemek zorunda. Okuyucu sadece kilidi ilgi kaydeder ve serbest yazarlar için bekler.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Faydalanmak genellikle güvenlidir [scoped_lock_read](#scoped_lock_read_class) edinmeli ve yayın için yapı bir `reader_writer_lock` nesnesi bir okuyucu bir özel durum olarak güvenli yolu.  
  
 Kilit üzerinde bekleyen yazıcılarının varsa, okuyucu satırdaki tüm yazıcılarının edinilen ve kilidi serbest kadar bekler. Bu kilit yazıcılarının ağırlıklı ve okuyucular yazıcılarının sürekli yükü altında tamamen Kaynaksız bırakabilir.  
  
##  <a name="ctor"></a> reader_writer_lock 

 Yeni bir oluşturur `reader_writer_lock` nesnesi.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a> ~ reader_writer_lock 

 Bozar `reader_writer_lock` nesnesi.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi çalıştığında kilidi artık tutulan beklenir. Okuyucu Yazıcı lock kilidiyle destruct izin vererek hala sonuçları tanımsız davranışını tutulan.  
  
##  <a name="scoped_lock_class"></a>  reader_writer_lock::scoped_lock sınıfı  
 Almak üzere kullanılabilecek bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` nesneleri yazan kilitleyin.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock 

Oluşturan bir `scoped_lock` nesne ve edinir `reader_writer_lock` nesnesi geçirildi `_Reader_writer_lock` parametre olarak bir yazıcı. Kilidi başka bir iş parçacığı tarafından tutulan bu çağrıyı engeller.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Reader_writer_lock`  
 `reader_writer_lock` Yazan edinmeye nesnesi.  
  
## <a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock 

Bozar bir `reader_writer_lock` nesne ve kurucusunda sağlanan kilidi serbest bırakır.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>  reader_writer_lock::scoped_lock_read sınıfı  
 Almak üzere kullanılabilecek bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` nesneleri okuyucu olarak kilitleyin.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a> try_lock 

 Okuyucu-Yazıcı yazan engellenmeden kilidi dener.  

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read 

Oluşturan bir `scoped_lock_read` nesne ve edinir `reader_writer_lock` nesnesi geçirildi `_Reader_writer_lock` parametre olarak bir okuyucu. Kilit bir yazıcı olarak başka bir iş parçacığı tarafından tutulan veya yazıcılarının vardır, bu çağrıyı engeller.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Reader_writer_lock`  
 `reader_writer_lock` Okuyucu olarak edinmeye nesnesi.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock::scoped_lock_read::~scoped_lock_read Destructor
Bozar bir `scoped_lock_read` nesne ve kurucusunda sağlanan kilidi serbest bırakır.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a> try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit aldıysanız değeri `true`; Aksi halde değer `false`.  
  
##  <a name="try_lock_read"></a> try_lock_read 

 Okuyucu-Yazıcı okuyucu olarak engellenmeden kilidi dener.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit aldıysanız değeri `true`; Aksi halde değer `false`.  
  
##  <a name="unlock">kilidini aç</a> 

 Kim, okuyucu veya yazan kilitli üzerinde temel Okuyucu-Yazıcı kilitleme kilidini açar.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kilit üzerinde bekleyen yazıcılarının varsa, kilidi sürümü her zaman FIFO sırayla sonraki yazıcı geçer. Bu kilit yazıcılarının ağırlıklı ve okuyucular yazıcılarının sürekli yükü altında tamamen Kaynaksız bırakabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [critical_section Sınıfı](critical-section-class.md)
