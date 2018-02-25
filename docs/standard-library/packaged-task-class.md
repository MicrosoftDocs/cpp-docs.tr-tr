---
title: "packaged_task sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::packaged_task [C++]
- std::packaged_task [C++], packaged_task
- std::packaged_task [C++], get_future
- std::packaged_task [C++], make_ready_at_thread_exit
- std::packaged_task [C++], reset
- std::packaged_task [C++], swap
- std::packaged_task [C++], valid
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce3db6f4685d8448efd88bf2203d541cc864abd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="packagedtask-class"></a>packaged_task Sınıfı
Açıklayan bir *zaman uyumsuz sağlayıcısı* diğer bir deyişle, çağrı imzası çağrısı sarmalayıcı `Ty(ArgTypes...)`. Kendi *zaman uyumsuz durum ilişkili* olası sonuç yanı sıra kendi aranabilir nesnesinin bir kopyasını tutar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[packaged_task](#packaged_task)|Oluşturan bir `packaged_task` nesnesi.|  
|[packaged_task::~packaged_task Destructor](#dtorpackaged_task_destructor)|Bozar bir `packaged_task` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_future](#get_future)|Döndürür bir [gelecekteki](../standard-library/future-class.md) aynı olan nesneyi ilişkili zaman uyumsuz durumu.|  
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|İlişkili zaman uyumsuz durumunda depolanır ve otomatik olarak döndürülen değer depolayan aranabilir nesnesi çağırır.|  
|[reset](#reset)|Zaman uyumsuz işlemin ilişkili durumu değiştirir.|  
|[Değiştirme](#swap)|Belirtilen bir nesneye değeriyle ilişkili zaman uyumsuz durum değiş tokuş eder.|  
|[valid](#valid)|Nesnenin ilişkili bir zaman uyumsuz durum olup olmadığını belirtir.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[packaged_task::operator=](#op_eq)|İlişkili bir zaman uyumsuz durumu belirtilen bir nesneden aktarır.|  
|[packaged_task::operator()](#op_call)|İlişkili zaman uyumsuz durumunda depolanır, otomatik olarak döndürülen değer depolayan ve durumunu ayarlar aranabilir nesnesi çağırır *hazır*.|  
|[packaged_task::operator bool](#op_bool)|Nesnenin ilişkili bir zaman uyumsuz durum olup olmadığını belirtir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<gelecekteki >  
  
 **Namespace:** std  
  
##  <a name="get_future"></a>  packaged_task::get_future  
 Türünde bir nesne döndürür `future<Ty>` aynı olan *zaman uyumsuz durum ilişkili*.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `packaged_task` nesnesinin ilişkili bir zaman uyumsuz durumu yok, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.  
  
 Bu yöntem için zaten çağrılmış bir `packaged_task` aynı olan nesneyi ilişkili zaman uyumsuz durumu, yöntemi atar bir `future_error` hata kodunu olan `future_already_retrieved`.  
  
##  <a name="make_ready_at_thread_exit"></a>  packaged_task::make_ready_at_thread_exit  
 Depolanan aranabilir nesnesi çağırır *zaman uyumsuz durum ilişkili* ve döndürülen değer otomatik olarak depolar.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `packaged_task` nesnesi, ilişkili bir zaman uyumsuz durum yoksa, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.  
  
 Varsa bu yöntemi veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) için zaten çağrılmış bir `packaged_task` aynı olan nesneyi ilişkili zaman uyumsuz durumu, yöntemi atar bir `future_error` hata kodunu olan `promise_already_satisfied`.  
  
 Aksi takdirde, bu işleç çağırır `INVOKE(fn, args..., Ty)`, burada *fn* ilişkili zaman uyumsuz durumunda depolanan aranabilir nesnesidir. Herhangi bir döndürülen değer otomatik olarak ilişkili zaman uyumsuz durum döndürülen sonuç depolanır.  
  
 Tersine için [packaged_task:: operator()](#op_call), ilişkili zaman uyumsuz durum ayarlanmazsa `ready` kadar tüm iş parçacığı yerel nesneleri çağıran iş parçacığı yok. Genellikle, çağıran iş parçacığı çıkar kadar ilişkili zaman uyumsuz durumunu engellenmiş iş parçacıklarının engeli değildir.  
  
##  <a name="op_eq"></a>  packaged_task::operator=  
 Aktarımları *zaman uyumsuz durum ilişkili* belirtilen bir nesneden.  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>Parametreler  
 `Right`  
 A `packaged_task` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `*this`  
  
### <a name="remarks"></a>Açıklamalar  
 İşleminden sonra `Right` ilişkili bir zaman uyumsuz durum artık sahip değil.  
  
##  <a name="op_call"></a>  packaged_task::operator()  
 Depolanan aranabilir nesnesi çağırır *zaman uyumsuz durum ilişkili*, otomatik olarak döndürülen değer depolar ve durumunu ayarlar *hazır*.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `packaged_task` nesnesi, ilişkili bir zaman uyumsuz durum yoksa, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.  
  
 Varsa bu yöntemi veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) için zaten çağrılmış bir `packaged_task` aynı olan nesneyi ilişkili zaman uyumsuz durumu, yöntemi atar bir `future_error` hata kodunu olan `promise_already_satisfied`.  
  
 Aksi takdirde, bu işleç çağırır `INVOKE(fn, args..., Ty)`, burada *fn* ilişkili zaman uyumsuz durumunda depolanan aranabilir nesnesidir. Herhangi bir değeri otomatik olarak ilişkili zaman uyumsuz durum döndürülen sonuç depolanır ve durumu döndürülen için hazır. Sonuç olarak, ilişkili zaman uyumsuz durumunu engellenmiş iş parçacığı sayısı engeli haline gelir.  
  
##  <a name="op_bool"></a>  packaged_task::operator bool  
 Nesne sahip olup olmadığını belirten bir `associated asynchronous state`.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` nesnenin ilişkili bir zaman uyumsuz durum varsa; Aksi takdirde `false`.  
  
##  <a name="packaged_task"></a>  packaged_task::packaged_task Oluşturucusu  
 Oluşturan bir `packaged_task` nesnesi.  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>Parametreler  
 `Right`  
 A `packaged_task` nesnesi.  
  
 `alloc`  
 Bellek ayırıcısında. Daha fazla bilgi için bkz: [ \<allocators >](../standard-library/allocators-header.md).  
  
 `fn`  
 Bir işlev nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu yapıları bir `packaged_task` hiçbir nesne *zaman uyumsuz durum ilişkili*.  
  
 İkinci oluşturucu yapıları bir `packaged_task` nesne ve ilişkili zaman uyumsuz durumundan aktarımı `Right`. İşleminden sonra `Right` ilişkili bir zaman uyumsuz durum artık sahip değil.  
  
 Üçüncü Oluşturucusu yapıları bir `packaged_task` bir kopyasına sahip nesne `fn` ilişkili zaman uyumsuz durumundayken depolanır.  
  
 Dördüncü Oluşturucusu yapıları bir `packaged_task` bir kopyasına sahip nesne `fn` ilişkili zaman uyumsuz durumundayken depolanır ve kullandığı `alloc` bellek ayırma için.  
  
##  <a name="dtorpackaged_task_destructor"></a>  packaged_task:: ~ packaged_task yıkıcısı  
 Bozar bir `packaged_task` nesnesi.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *zaman uyumsuz durum ilişkili* değil *hazır*, yıkıcı depoları bir [future_error](../standard-library/future-error-class.md) hata kodunu sahip özel durum `broken_promise` sonucu olarak ilişkili zaman uyumsuz durumu ve engeli hale ilişkili zaman uyumsuz durumunu engellenmiş iş parçacığı sayısı.  
  
##  <a name="reset"></a>  packaged_task::reset  
 Yeni bir kullanan *zaman uyumsuz durum ilişkili* varolan değiştirmek için zaman uyumsuz durum ilişkilendirilmiş.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gerçekte, bu yöntem yürütür `*this = packaged_task(move(fn))`, burada *fn* bu nesne için ilişkili zaman uyumsuz durumunda depolanan işlev nesnesidir. Bu nedenle, nesnenin durumunu temizlenir, ve [get_future](#get_future), [operator()](#op_call), ve [make_ready_at_thread_exit](#make_ready_at_thread_exit) yeni oluşturulan gibi bir nesne üzerinde çağrılabilir.  
  
##  <a name="swap"></a>  packaged_task::Swap  
 Belirtilen bir nesneye değeriyle ilişkili zaman uyumsuz durum değiş tokuş eder.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Right`  
 A `packaged_task` nesnesi.  
  
##  <a name="valid"></a>  packaged_task::valid  
 Nesne sahip olup olmadığını belirten bir `associated asynchronous state`.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` nesnenin ilişkili bir zaman uyumsuz durum varsa; Aksi takdirde `false`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<sonraki >](../standard-library/future.md)



