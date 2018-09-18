---
title: cancellation_token sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 125d08def4a1fb801cb1b6c911d8c8c9c154c296
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037982"
---
# <a name="cancellationtoken-class"></a>cancellation_token Sınıfı
`cancellation_token` Sınıfı, bazı işlemlerin iptal istendi olup olmadığını belirleme yeteneğini temsil eder. Verilen bir belirteç ile ilişkilendirilmiş bir `task_group`, `structured_task_group`, veya `task` örtük iptal sağlamak için. Ayrıca iptal için yoklanabilir veya bir geri çağırma için kayıtlı olan ilişkili `cancellation_token_source` iptal edilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cancellation_token](#ctor)||  
|[~ cancellation_token yok Edicisi](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[deregister_callback](#deregister_callback)|Aracılığıyla önceden kayıtlı bir geri çağırmayı kaldırır `register` dayalı `cancellation_token_registration` kayıt zamanında döndürülen nesnesi.|  
|[is_cancelable](#is_cancelable)|Bu belirteci veya iptal edilip bir göstergesini döndürür.|  
|[is_canceled](#is_canceled)|Döndürür `true` belirteç iptal edilmişse.|  
|[Yok](#none)|Hiçbir zaman iptale tabi olmayan bir iptal belirteci döndürür.|  
|[register_callback](#register_callback)|Belirteç ile bir geri çağırma işlevini kaydeder. Belirteç iptal edilirse, geri arama yapılır. Belirteç zaten burada bu yöntemin çağrıldığı noktada iptal edilirse, geri çağırma hemen ve eşzamanlı olarak yapılacağına dikkat edin.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `cancellation_token`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplcancellation_token.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="ctor"></a> cancellation_token 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
Kopyalanamaz veya taşınamaz cancellation_token.
  
##  <a name="deregister_callback"></a> deregister_callback 

 Aracılığıyla önceden kayıtlı bir geri çağırmayı kaldırır `register` dayalı `cancellation_token_registration` kayıt zamanında döndürülen nesnesi.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Registration*<br/>
`cancellation_token_registration` Çıkarılması gereken geri aramaya karşılık gelen nesne. Bu belirteç önceden bir çağrıdan iade edilmiş gerekir `register` yöntemi.  
  
##  <a name="is_cancelable"></a> is_cancelable 

 Bu belirteci veya iptal edilip bir göstergesini döndürür.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu belirteci veya iptal edilip bir göstergesi.  
  
##  <a name="is_canceled"></a> is_canceled 

 Döndürür `true` belirteç iptal edilmişse.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değer `true` belirteç iptal edildi; Aksi takdirde, değeri `false`.  
  
##  <a name="none"></a> Yok 

 Hiçbir zaman iptale tabi olmayan bir iptal belirteci döndürür.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İptal edilemez bir iptal belirteci.  
  
##  <a name="operator_neq"></a> işleç! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
`cancellation_token` Karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
`cancellation_token` Atamak için.
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> işleç == 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
`cancellation_token` Karşılaştırmak için.
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="register_callback"></a> register_callback 

 Belirteç ile bir geri çağırma işlevini kaydeder. Belirteç iptal edilirse, geri arama yapılır. Belirteç zaten burada bu yöntemin çağrıldığı noktada iptal edilirse, geri çağırma hemen ve eşzamanlı olarak yapılacağına dikkat edin.  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Function*<br/>
Çağrılacak işlev nesnesinin türü geri bu `cancellation_token` iptal edilir.  
  
*_Func*<br/>
Çağrılacak işlev nesnesi geri bu `cancellation_token` iptal edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `cancellation_token_registration` kullanılabilen nesne `deregister` önceden kaydedilmiş bir geri arama kaydını kaldırmak ve yapılmasını önlemek için yöntem. Yöntemi bir [invalid_operation](invalid-operation-class.md) üzerinde çağrılırsa bir özel durum bir `cancellation_token` kullanılarak oluşturulmuş nesne [cancellation_token::none](#none) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
