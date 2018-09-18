---
title: Event sınıfı | Microsoft Docs
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
ms.openlocfilehash: 7f4156720d7d02b0c96ab36101d88c941dbfbfdd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071544"
---
# <a name="event-class"></a>event Sınıfı
Eşzamanlılık çalışma zamanının açıkça farkında olan el ile sıfırlama olayı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class event;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ event yok Edicisi](#dtor)|Bir olayı yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Sıfırlama](#reset)|Olay verilmemiş bir duruma sıfırlar.|  
|[set](#set)|Olay sinyalini verir.|  
|[bekleme](#wait)|Olayın sinyal haline bekler.|  
|[wait_for_multiple](#wait_for_multiple)|Birden fazla olayın sinyal haline bekler.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Beklemenin asla zaman aşımına uğramayacağını belirten değer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).  
  
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

 Bir olayı yok eder.  
  
```
~event();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Olan yıkıcı çalıştığında olayda bekleyen iş parçacığı olmaması beklenir. Hala bekliyor tanımlanmayan davranışla sonuçlanır iş parçacıklarıyla yok etmek üzere olaya izin verme.  
  
##  <a name="reset"></a> Sıfırlama 

 Olay verilmemiş bir duruma sıfırlar.  
  
```
void reset();
```  
  
##  <a name="set"></a> Ayarlayın 

 Olay sinyalini verir.  
  
```
void set();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Olayın sinyal çalıştırılabilir duruma gelmesine olayda bekleyen bağlamları rastgele bir sayıdan neden olabilir.  
  
##  <a name="timeout_infinite"></a> timeout_infinite 

 Beklemenin asla zaman aşımına uğramayacağını belirten değer.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a> bekleme 

 Olayın sinyal haline bekler.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
*_Zaman aşımı*<br/>
Zaman aşımını beklemeden önce milisaniye sayısını gösterir. Değer `COOPERATIVE_TIMEOUT_INFINITE` hiçbir zaman aşımı olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bekleme memnun ettiyse, değer `0` döndürülmüştür; Aksi takdirde değeri `COOPERATIVE_WAIT_TIMEOUT` bekleme olayın sinyalliye dönüşmesi zaman aşımına uğradığını belirtmek için.  
  
> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulaması çağırmayın `wait` üzerinde ASTA iş parçacığı çünkü bu çağrı geçerli iş parçacığını engelleyebildiğinden ve uygulamanın yanıt veremez duruma gelmesine neden olabilir.  
  
##  <a name="wait_for_multiple"></a> wait_for_multiple 

 Birden fazla olayın sinyal haline bekler.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
*_PPEvents*<br/>
Üzerinde beklenilen olaylar dizisi. Dizi içerisindeki olay sayısı tarafından belirtilen `count` parametresi.  
  
*Sayısı*<br/>
Sağlanan dizi içindeki olayların sayısı `_PPEvents` parametresi.  
  
*_FWaitAll*<br/>
Varsa değerine ayarlanırsa `true`, parametre olarak sağlanan dizi içindeki tüm olayların belirtir `_PPEvents` parametre sinyalliye dönüşmesi beklemeyi karşılamak için. Varsa değerine ayarlanırsa `false`, dizi içinde herhangi bir olayın sağlanan belirtir `_PPEvents` sinyalliye dönüşmesi parametresi, beklemeyi karşılamak.  
  
*_Zaman aşımı*<br/>
Zaman aşımını beklemeden önce milisaniye sayısını gösterir. Değer `COOPERATIVE_TIMEOUT_INFINITE` hiçbir zaman aşımı olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bekleme memnun ettiyse, dizin sağlanan `_PPEvents` bekleme koşulunu; memnun parametresini Aksi takdirde, değeri `COOPERATIVE_WAIT_TIMEOUT` bekleme memnun koşul olmadan zaman aşımına uğradığını belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre `_FWaitAll` değere ayarlanmış `true` tüm olaylar beklemeyi karşılamak amacıyla sinyalli hale dönüşmesi gereken belirtmek için işlevin döndürdüğü dizin, değer olmadığını olgu başka özel anlamlı değer taşır `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  Bir evrensel Windows Platformu (UWP) uygulaması çağırmayın `wait_for_multiple` üzerinde ASTA iş parçacığı çünkü bu çağrı geçerli iş parçacığını engelleyebildiğinden ve uygulamanın yanıt veremez duruma gelmesine neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
