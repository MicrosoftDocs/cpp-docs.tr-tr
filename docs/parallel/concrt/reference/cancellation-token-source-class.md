---
title: cancellation_token_source sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5bda0dd4b756ba9228fac8cc5b0de70b6d71f7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053654"
---
# <a name="cancellationtokensource-class"></a>cancellation_token_source Sınıfı
`cancellation_token_source` Sınıfı, iptal edilebilir bazı işlemleri iptal etme yeteneğini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cancellation_token_source](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `cancellation_token_source`. Kaynak iptal edilebilir bazı işlemleri iptalini işaretlemek için kullanılabilir.|  
|[~ cancellation_token_source yok Edicisi](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Belirteci iptal eder. Tüm `task_group`, `structured_task_group`, veya `task` , belirteç kullanır, bu çağrıdan sonra iptal edilecek ve sonraki kesinti noktasında bir özel durum.|  
|[create_linked_source](#create_linked_source)|Fazla Yüklendi. Oluşturur bir `cancellation_token_source` sağlanan belirteç iptal edildiğinde İptal.|  
|[get_token](#get_token)|Bu kaynakla ilişkilendirilmiş iptal belirteci döndürür. Döndürülen belirteç iptal için yoklanabilir veya İptal gerçekleşirse ve gerçekleştiğinde geri çağırma sağlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `cancellation_token_source`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplcancellation_token.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ cancellation_token_source 

```
~cancellation_token_source();
```  
  
##  <a name="cancel"></a> İptal 

 Belirteci iptal eder. Tüm `task_group`, `structured_task_group`, veya `task` , belirteç kullanır, bu çağrıdan sonra iptal edilecek ve sonraki kesinti noktasında bir özel durum.  
  
```
void cancel() const;
```  
  
##  <a name="ctor"></a> cancellation_token_source 

 Yeni bir oluşturur `cancellation_token_source`. Kaynak iptal edilebilir bazı işlemleri iptalini işaretlemek için kullanılabilir.  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
Kopyalamak veya taşımak için nesne.  
  
##  <a name="create_linked_source"></a> create_linked_source 

 Oluşturur bir `cancellation_token_source` sağlanan belirteç iptal edildiğinde İptal.  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>Parametreler  
*_Iter*<br/>
Yineleyici türü.

*_Src*<br/>
İptal edilmesi, döndürülen belirteç kaynağının iptaline neden olacak bir belirteç. Döndürülen belirteç kaynağının bu parametrede bulunan kaynaktan bağımsız olarak iptal edilebilir olduğunu unutmayın.  
  
*_Begin*<br/>
İptali için dinlenecek belirteçler aralığının başlangıcına denk gelen C++ Standart Kitaplığı yineleyici.  
  
*_Bitiş*<br/>
İptali için dinlenecek belirteçler aralığının sonunu karşılık gelen C++ Standart Kitaplığı yineleyici.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `cancellation_token_source` tarafından sağlanan belirteç iptal `_Src` parametresi iptal edilir.  
  
##  <a name="get_token"></a> get_token 

 Bu kaynakla ilişkilendirilmiş iptal belirteci döndürür. Döndürülen belirteç iptal için yoklanabilir veya İptal gerçekleşirse ve gerçekleştiğinde geri çağırma sağlar.  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kaynakla ilişkilendirilmiş iptal belirteci.  
  
##  <a name="operator_neq"></a> işleç! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
İşlenen.
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
İşlenen.

### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> işleç == 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
İşlenen.
  
### <a name="return-value"></a>Dönüş Değeri  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
