---
title: olay sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb02865b20d1603be38192e770eb26627e6900e7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692873"
---
# <a name="event-class"></a>event Sınıfı
Eşzamanlılık Çalışma zamanı açıkça farkındadır elle sıfırlama olayı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class event;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ event yok Edicisi](#dtor)|Bir olay yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Sıfırla](#reset)|Olay işaret olmayan bir durumuna sıfırlar.|  
|[set](#set)|Olay işaret eder.|  
|[bekleme](#wait)|Olay işaret hale bekler.|  
|[wait_for_multiple](#wait_for_multiple)|Birden çok olay işaret hale bekler.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Bekleme zaman aşımı hiçbir zaman gerektiğini belirten değer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `event`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> Olay 

 Yeni bir olay oluşturur.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dtor"></a> ~ Olay 

 Bir olay yok eder.  
  
```
~event();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yıkıcı çalıştığında olay üzerinde bekleyen iş parçacığı vardır beklenir. Olay tanımsız davranışa neden olur hala üzerinde bekleyen iş parçacığı ile destruct izin verme.  
  
##  <a name="reset"></a> Sıfırla 

 Olay işaret olmayan bir durumuna sıfırlar.  
  
```
void reset();
```  
  
##  <a name="set"></a> ayarlama 

 Olay işaret eder.  
  
```
void set();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Olayı sinyali runnable olmasını olayında beklerken bağlamları rastgele sayıda neden olabilir.  
  
##  <a name="timeout_infinite"></a> timeout_infinite 

 Bekleme zaman aşımı hiçbir zaman gerektiğini belirten değer.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a> bekleme 

 Olay işaret hale bekler.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Timeout`  
 Bekleme zaman aşımına uğramadan önce milisaniye sayısını gösterir. Değer `COOPERATIVE_TIMEOUT_INFINITE` hiçbir zaman aşımı olduğunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bekleme memnun, değer `0` döndürülen; Aksi takdirde, değer `COOPERATIVE_WAIT_TIMEOUT` bekleme işaret olma olay zaman aşımına uğradı olduğunu belirtmek için.  
  
> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulamasını çağırmayın `wait` üzerinde ASTA iş parçacığı çünkü bu çağrıyı geçerli iş parçacığının engelleyebilir ve uygulama yanıt veremez duruma neden olabilir.  
  
##  <a name="wait_for_multiple"></a> wait_for_multiple 

 Birden çok olay işaret hale bekler.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PPEvents`  
 Beklemesi olaylar dizisi. Dizi içinde olayların sayısının belirtilir `count` parametresi.  
  
 `count`  
 İçinde sağlanan dizi etkinliklerin sayısını `_PPEvents` parametresi.  
  
 `_FWaitAll`  
 Varsa değerine ayarlayın `true`, dizi içinde tüm olayları içinde sağlanan parametre belirtir `_PPEvents` parametre gerekir duruma işaret bekleme karşılamak için. Varsa değerine ayarlayın `false`, dizi içinde herhangi bir olay olarak sağlanan belirtir `_PPEvents` işaret olma parametre bekleme belirtimini.  
  
 `_Timeout`  
 Bekleme zaman aşımına uğramadan önce milisaniye sayısını gösterir. Değer `COOPERATIVE_TIMEOUT_INFINITE` hiçbir zaman aşımı olduğunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bekleme memnun, dizi dizini içinde sağlanan `_PPEvents` bekleme koşulu; memnun parametresini Aksi halde değer `COOPERATIVE_WAIT_TIMEOUT` bekleme memnun koşul olmadan zaman aşımına uğradı olduğunu belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa parametresi `_FWaitAll` değerine ayarlayın `true` tüm olayları, bekleme karşılamak için sinyal hale olduğunu belirtmek için işlev tarafından döndürülen dizin değeri olmadığını olgu dışında özel bir önemi taşır `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulamasını çağırmayın `wait_for_multiple` üzerinde ASTA iş parçacığı çünkü bu çağrıyı geçerli iş parçacığının engelleyebilir ve uygulama yanıt veremez duruma neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
