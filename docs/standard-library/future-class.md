---
title: "Future sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
dev_langs: C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.workload: cplusplus
ms.openlocfilehash: 1de870da42504494e672cff4272fd230d1346114
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="future-class"></a>future Sınıfı
Açıklayan bir *zaman uyumsuz dönüş nesnesi*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
class future;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her standart *zaman uyumsuz sağlayıcısı* türü olan bir örnek oluşturma bu şablonu bir nesne döndürür. A `future` nesne ile ilişkili zaman uyumsuz sağlayıcısına yalnızca erişim sağlar. Aynı zaman uyumsuz sağlayıcı ile ilişkili birden çok zaman uyumsuz dönüş nesneleri ihtiyacınız varsa, kopyalama `future` nesnesine bir [shared_future](../standard-library/shared-future-class.md) nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Gelecekteki](#future)|Oluşturan bir `future` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get](#get)|İlişkili zaman uyumsuz durumunda depolanan sonucu alır.|  
|[Paylaş](#share)|Nesnesine dönüştürür bir `shared_future`.|  
|[Geçerli](#valid)|Nesne boş değil olup olmadığını belirtir.|  
|[bekleme](#wait)|Zaman uyumsuz işlemin ilişkili durumu hazır olana kadar geçerli iş parçacığının engeller.|  
|[wait_for](#wait_for)|İlişkili zaman uyumsuz durum kadar blokları hazır veya belirtilen zamana kadar geçen.|  
|[wait_until](#wait_until)|Blokları ilişkili zaman uyumsuz durum kadar sürede hazır veya belirli bir noktaya kadar olur.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Future::operator =](#op_eq)|Zaman uyumsuz işlemin ilişkili durumu belirtilen bir nesneden aktarır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<gelecekteki >  
  
 **Namespace:** std  
  
##  <a name="future"></a>Future::Future Oluşturucusu  
 Oluşturan bir `future` nesnesi.  
  
```
future() noexcept;
future(future&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Other`  
 A `future` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu yapıları bir `future` zaman uyumsuz durum ilişkili hiç nesnesi.  
  
 İkinci oluşturucu yapıları bir `future` nesne ve ilişkili zaman uyumsuz durumundan aktarımı `Other`. `Other`artık ilişkili bir zaman uyumsuz durum yok.  
  
##  <a name="get"></a>Future::get  
 İlişkili zaman uyumsuz durumunda depolanan sonucu alır.  
  
```
Ty get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuç bir özel durum ise, yöntem, yeniden oluşturur. Aksi takdirde, sonuç döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç almadan önce ilişkili zaman uyumsuz durumu hazır olana kadar bu yöntem geçerli iş parçacığının engeller.  
  
 Kısmi uzmanlığı için `future<Ty&>`, saklı etkili bir şekilde dönüş değeri olarak zaman uyumsuz sağlayıcısına geçirilen nesneye bir başvurusu değerdir.  
  
 Özelleştirme için depolanan değer var olduğundan `future<void>`, yöntem `void`.  
  
 Diğer özelleştirmeleri, yöntemin dönüş değeri saklı değerinden taşır. Bu nedenle, bu yöntemi yalnızca bir kez çağırın.  
  
##  <a name="op_eq"></a>Future::operator =  
 İlişkili bir zaman uyumsuz durumu belirtilen bir nesneden aktarır.  
  
```
future& operator=(future&& Right) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Right`  
 A `future` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `*this`  
  
### <a name="remarks"></a>Açıklamalar  
 Aktarım sonra `Right` ilişkili bir zaman uyumsuz durum artık sahip değil.  
  
##  <a name="share"></a>Future::share  
 Nesnesine dönüştürür bir [shared_future](../standard-library/shared-future-class.md) nesnesi.  
  
```
shared_future<Ty> share();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `shared_future(move(*this))`  
  
##  <a name="valid"></a>Future::valid  
 Nesnenin ilişkili bir zaman uyumsuz durum olup olmadığını belirtir.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`nesnenin ilişkili bir zaman uyumsuz durum varsa; Aksi takdirde `false`.  
  
##  <a name="wait"></a>Future::wait  
 İlişkili zaman uyumsuz durum olana kadar geçerli iş parçacığının engeller *hazır*.  
  
```cpp  
void wait() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili bir zaman uyumsuz durum *hazır* zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanır.  
  
##  <a name="wait_for"></a>Future::wait_for  
 İlişkili zaman uyumsuz durum olana kadar geçerli iş parçacığının engeller *hazır* veya belirli bir zaman aralığı sona ermeden.  
  
```
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Rel_time`  
 A [chrono::duration](../standard-library/duration-class.md) en büyük zaman aralığını belirtir nesnesi, iş parçacığı engeller.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [future_status](../standard-library/future-enums.md#future_status) döndürmek için nedenini gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan ilişkili bir zaman uyumsuz durum hazırdır.  
  
##  <a name="wait_until"></a>Future::wait_until  
 İlişkili zaman uyumsuz durum olana kadar geçerli iş parçacığının engeller *hazır* veya belirtilen zaman noktası kadar sonra.  
  
```cpp  
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `Abs_time`  
 A [chrono::time_point](../standard-library/time-point-class.md) nesne geçmesi iş parçacığı engellemesini süreyi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [future_status](../standard-library/future-enums.md#future_status) döndürmek için nedenini gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili bir zaman uyumsuz durum *hazır* zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<sonraki >](../standard-library/future.md)



