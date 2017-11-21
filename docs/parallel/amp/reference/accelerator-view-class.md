---
title: "accelerator_view sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view:accelerator_view
- AMPRT/Concurrency::accelerator_view:create_marker
- AMPRT/Concurrency::accelerator_view:flush
- AMPRT/Concurrency::accelerator_view:get_accelerator
- AMPRT/Concurrency::accelerator_view:get_is_auto_selection
- AMPRT/Concurrency::accelerator_view:get_is_debug
- AMPRT/Concurrency::accelerator_view:get_queuing_mode
- AMPRT/Concurrency::accelerator_view:get_version
- AMPRT/Concurrency::accelerator_view:wait
- AMPRT/Concurrency::accelerator_view:accelerator
- AMPRT/Concurrency::accelerator_view:is_auto_selection
- AMPRT/Concurrency::accelerator_view:is_debug
- AMPRT/Concurrency::accelerator_view:queuing_mode
- AMPRT/Concurrency::accelerator_view:version
dev_langs: C++
helpviewer_keywords: accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66d98297d681f3c2c377a7bccb7b988169aca76d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="acceleratorview-class"></a>accelerator_view Sınıfı
C++ AMP verileri paralel Hızlandırıcı üzerinde bir sanal cihaz soyutlama temsil eder.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accelerator_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator_view` sınıfı.|  
|[~ accelerator_view yok Edicisi](#dtor)|Bozar `accelerator_view` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[create_marker](#create_marker)|Tamamlandığında şu ana kadar bu için gönderilen tüm komutlar, izlemek için gelecek döndürür `accelerator_view` nesnesi.|  
|[Temizleme](#flush)|Tüm komutları bekleyen kuyruğa gönderen `accelerator_view` yürütme için Hızlandırıcı nesnesine.|  
|[get_accelerator](#get_accelerator)|Döndürür `accelerator` için nesne `accelerator_view` nesne.|  
|[get_is_auto_selection](#get_is_auto_selection)|Çalışma zamanı uygun Hızlandırıcı otomatik olarak seçer olup olmadığını gösteren bir Boole değeri döndürür, `accelerator_view` nesne geçirilen bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[get_is_debug](#get_is_debug)|Gösteren bir Boole değeri döndürür olup olmadığını `accelerator_view` nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.|  
|[get_queuing_mode](#get_queuing_mode)|Sıralama modu için döndürür `accelerator_view` nesnesi.|  
|[get_version](#get_version)|Sürümünü döndürür `accelerator_view`.|  
|[bekleme](#wait)|Gönderilen tüm komutlar için bekleyeceği `accelerator_view` tamamlamak için nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator! =](#operator_neq)|Bu karşılaştırır `accelerator_view` başka bir nesneyle ve döndürür `false` aynı; olmaları durumunda hata verir `true`.|  
|[işleç =](#operator_eq)|Belirtilen içeriğini kopyalar `accelerator_view` bunu nesnesine.|  
|[operator ==](#operator_eq_eq)|Bu karşılaştırır `accelerator_view` başka bir nesneyle ve döndürür `true` aynı; olmaları durumunda hata verir `false`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Hızlandırıcı](#accelerator)|Alır `accelerator` için nesne `accelerator_view` nesne.|  
|[is_auto_selection](#is_auto_selection)|Çalışma zamanı uygun Hızlandırıcı otomatik olarak seçer olup olmadığını gösteren bir Boole değeri alır, `accelerator_view` nesne geçirilen bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[is_debug](#is_debug)|Gösteren bir Boole değeri alır olup olmadığını `accelerator_view` nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.|  
|[queuing_mode](#queuing_mode)|Sıraya alma modunu alır `accelerator_view` nesnesi.|  
|[Sürüm](#version)|Hızlandırıcı sürümünü alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `accelerator_view`  
  
### <a name="remarks"></a>Açıklamalar  
 Bir `accelerator_view` nesnesi Hızlandırıcı mantıksal, yalıtılmış bir görünümünü temsil eder. Tek bir fiziksel işlem aygıtı birçok mantıksal, yalıtılmış bulunabilir `accelerator_view` nesneleri. Her Hızlandırıcı varsayılan sahip `accelerator_view` nesnesi. Ek `accelerator_view` nesneleri oluşturulabilir.  
  
 Fiziksel aygıtların birçok istemci iş parçacıkları arasında paylaşılabilir. İstemci iş parçacıklarını işbirliği ile kullanabileceğiniz aynı `accelerator_view` Hızlandırıcı ya da her istemci nesnesinin bağımsız aracılığıyla işlem aygıtıyla iletişim `accelerator_view` diğer istemci iş parçacıklarından yalıtımı için nesne.  
  
 Bir `accelerator_view` nesnesi iki birine sahip olabilir [queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode) durumları. Sıralama modu ise `immediate`, gibi komutlar `copy` ve `parallel_for_each` karşılık gelen Hızlandırıcı aygıta çağırana döndürmeleri hemen sonra gönderilir. Sıralama modu ise `deferred`, bu tür komutları karşılık gelen bir komut sırasına kadar sıraya alınır `accelerator_view` nesnesi. Komut gerçekte gönderilmez kadar aygıt için `flush()` olarak adlandırılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  

## <a name="accelerator"></a>Hızlandırıcı 

Hızlandırıcı nesne için accelerator_view nesnesini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="ctor"></a>accelerator_view 

Var olan kopyalayarak accelerator_view sınıfının yeni bir örneğini başlatır `accelerator_view` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` Kopyalamak için nesne.  
  
## <a name="accelerator_view__create_marker"></a>create_marker 

Tamamlandığında şu ana kadar bu için gönderilen tüm komutlar, izlemek için gelecek döndürür `accelerator_view` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlandığında şu ana kadar bu için gönderilen tüm komutlar, izlemek için gelecek `accelerator_view` nesnesi.  
  
## <a name="flush"></a>Temizleme 

Tüm bekleyen komutları yürütme için Hızlandırıcı accelerator_view nesnesine kuyruğa alınan gönderir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `void`.  

## <a name="accelerator_view__get_accelerator"></a>get_accelerator 

Accelerator_view nesnesi için Hızlandırıcı nesnesi döndürür.
### <a name="syntax"></a>Sözdizimi
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Dönüş Değeri
Accelerator_view nesnesi için Hızlandırıcı nesnesi.

## <a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun Hızlandırıcı seçip olup olmadığını gösteren bir Boole değeri döndürür bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`çalışma zamanı uygun Hızlandırıcı otomatik olarak seçer Aksi takdirde `false`.  
  
## <a name="accelerator_view__get_is_debug"></a>get_is_debug 

Accelerator_view nesne kapsamlı hata bildirimi için etkin hata ayıklama katman olup olmadığını gösteren bir Boole değeri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösteren bir Boole değeri olup olmadığını `accelerator_view` nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  

## <a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Accelerator_view nesnesi için sıraya alma modunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıralama modu için `accelerator_view` nesnesi.  
  
## <a name="accelerator_view__get_version"></a>get_version 

Accelerator_view sürümünü döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürümü `accelerator_view`.  
  
## <a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun Hızlandırıcı seçip olup olmadığını gösteren bir Boole değeri alır bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="accelerator_view__is_debug"></a>is_debug 

Accelerator_view nesne kapsamlı hata bildirimi için etkin hata ayıklama katman olup olmadığını gösteren bir Boole değeri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="accelerator_view__operator_neq"></a>operator! = 

Bu accelerator_view nesnesiyle başka karşılaştırır ve verir `false` aynı; olmaları durumunda hata verir `true`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `false`iki nesnenin aynı olup olmadığını; Aksi takdirde `true`.  
  
## <a name="accelerator_view__operator_eq"></a>işleç = 

Belirtilen accelerator_view nesnesinin içeriğini bunu kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru değiştirilmiş `accelerator_view` nesnesi.  
  
## <a name="accelerator_view__operator_eq_eq"></a>operator == 

Bu accelerator_view nesnesiyle başka karşılaştırır ve verir `true` aynı; olmaları durumunda hata verir `false`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`iki nesnenin aynı olup olmadığını; Aksi takdirde `false`.  
  
## <a name="accelerator_view__queuing_mode"></a>queuing_mode 

Sıralama modu için accelerator_view nesnesini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="accelerator_view__version"></a>Sürüm 

Accelerator_view sürümünü alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="accelerator_view__wait"></a>bekleme 

Tamamlanması accelerator_view nesnesine gönderilen tüm komutlar için bekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `void`.  
  
#### <a name="remarks"></a>Açıklamalar  
 Varsa [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) olan `immediate`, bu yöntem, hemen engellenmeden döndürür.  
  
##  <a name="dtor"></a>~ accelerator_view 

 Accelerator_view nesnesini yok eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
