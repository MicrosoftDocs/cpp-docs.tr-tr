---
title: "cancellation_token sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e95bfb264b1c6fbc4230cf38fc26b7b6a2c12a1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cancellationtoken-class"></a>cancellation_token Sınıfı
`cancellation_token` Sınıfı, başka bir işlem iptal istendi olup olmadığını belirleme özelliğini temsil eder. Verilen bir belirteç ile ilişkili bir `task_group`, `structured_task_group`, veya `task` örtük iptal sağlamak için. Bu ayrıca iptalleri sorgulanmak veya bir geri çağırma için varsa ve kayıtlı sahip ilişkili `cancellation_token_source` iptal edilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cancellation_token](#ctor)||  
|[~cancellation_token Destructor](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[deregister_callback](#deregister_callback)|Aracılığıyla daha önce kaydedilen bir geri arama kaldırır `register` yöntemi temel alarak `cancellation_token_registration` kayıt zamanında nesne döndürdü.|  
|[is_cancelable](#is_cancelable)|Olup bu belirteç veya iptal edilebilir bir gösterge döndürür.|  
|[is_canceled](#is_canceled)|Döndürür `true` belirteci iptal ederseniz.|  
|[Yok](#none)|Hangi asla iptal tabi olabilir bir iptal belirteci döndürür.|  
|[register_callback](#register_callback)|Belirteçle bir geri çağırma işlevini kaydeder. Belirteci iptal zaman geri arama yapılır. Belirteç zaten burada bu yöntem çağrılır noktada iptal ederseniz, geri çağırma hemen ve eşzamanlı olarak yapılacak olduğunu unutmayın.|  
  
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
 `_Src`  
  
##  <a name="deregister_callback"></a> deregister_callback 

 Aracılığıyla daha önce kaydedilen bir geri arama kaldırır `register` yöntemi temel alarak `cancellation_token_registration` kayıt zamanında nesne döndürdü.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Registration`  
 `cancellation_token_registration` Kaydını sildi için geri çağırma karşılık gelen nesne. Bu belirteç önceden çağrısından verilinceye gerekir `register` yöntemi.  
  
##  <a name="is_cancelable">is_cancelable</a> 

 Olup bu belirteç veya iptal edilebilir bir gösterge döndürür.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bu belirteç veya iptal edilebilir bir göstergesi.  
  
##  <a name="is_canceled"></a> is_canceled 

 Döndürür `true` belirteci iptal ederseniz.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değer `true` belirteç olması durumunda iptal edildi; Aksi takdirde değer `false`.  
  
##  <a name="none">Yok</a> 

 Hangi asla iptal tabi olabilir bir iptal belirteci döndürür.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İptal edilemez bir iptal belirteci.  
  
##  <a name="operator_neq"></a> operator! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> operator == 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="register_callback"></a> register_callback 

 Belirteçle bir geri çağırma işlevini kaydeder. Belirteci iptal zaman geri arama yapılır. Belirteç zaten burada bu yöntem çağrılır noktada iptal ederseniz, geri çağırma hemen ve eşzamanlı olarak yapılacak olduğunu unutmayın.  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Çağrılacak işlevin nesne türünü ne zaman geri bu `cancellation_token` iptal edilir.  
  
 `_Func`  
 Çağrılacak işlev nesnesi ne zaman geri bu `cancellation_token` iptal edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `cancellation_token_registration` içinde kullanılabilir nesne `deregister` daha önce kaydedilen bir geri çağırma kaydını silmek ve kullanılmasını önlemek için yöntem. Yöntemi özel durum oluşturacak bir [invalid_operation](invalid-operation-class.md) üzerinde çağrıldıysa özel bir `cancellation_token` kullanılarak oluşturulmuş nesne [cancellation_token::none](#none) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
