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
ms.openlocfilehash: 122a60496a92b3844f4e439e40650c429035dc33
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="cancellationtokensource-class"></a>cancellation_token_source Sınıfı
`cancellation_token_source` Sınıfı, bazı İptal işlemi iptal etme yeteneğini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cancellation_token_source](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `cancellation_token_source`. Kaynak başka bir iptal edilebilen işlem iptaline bayrak için kullanılabilir.|  
|[~ cancellation_token_source yok Edicisi](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Belirteç iptal eder. Tüm `task_group`, `structured_task_group`, veya `task` hangi belirteç kullanır, bu çağrı sırasında iptal edilir ve sonraki kesinti noktada bir özel durum.|  
|[create_linked_source](#create_linked_source)|Fazla Yüklendi. Oluşturur bir `cancellation_token_source` sağlanan belirteci iptal edildiğinde İptal.|  
|[get_token](#get_token)|Bu kaynağı ile ilişkili iptal belirtecini döndürür. Döndürülen belirteç iptalleri sorgulanan veya iptal gerçekleşir açmadıklarını ve ne zaman bir geri çağırma sağlayın.|  
  
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

 Belirteç iptal eder. Tüm `task_group`, `structured_task_group`, veya `task` hangi belirteç kullanır, bu çağrı sırasında iptal edilir ve sonraki kesinti noktada bir özel durum.  
  
```
void cancel() const;
```  
  
##  <a name="ctor"></a> cancellation_token_source 

 Yeni bir oluşturur `cancellation_token_source`. Kaynak başka bir iptal edilebilen işlem iptaline bayrak için kullanılabilir.  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
##  <a name="create_linked_source"></a> create_linked_source 

 Oluşturur bir `cancellation_token_source` sağlanan belirteci iptal edildiğinde İptal.  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Iter`  
 `_Src`  
 Bir belirteç olan iptal döndürülen belirteci kaynağı iptaline neden olur. Döndürülen belirteci kaynağı bu parametrede bulunan kaynak bağımsız olarak iptal edilebilir olduğunu unutmayın.  
  
 `_Begin`  
 İptali için dinlenecek belirteçleri aralığını başlangıcına karşılık gelen C++ Standart Kitaplığı yineleyici.  
  
 `_End`  
 İptali için dinlenecek belirteçleri aralığı bitiş için karşılık gelen C++ Standart Kitaplığı yineleyici.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `cancellation_token_source` belirteç tarafından sağlandığında iptal `_Src` parametresi iptal edilir.  
  
##  <a name="get_token"></a> get_token 

 Bu kaynağı ile ilişkili iptal belirtecini döndürür. Döndürülen belirteç iptalleri sorgulanan veya iptal gerçekleşir açmadıklarını ve ne zaman bir geri çağırma sağlayın.  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kaynağı ile ilişkili iptal belirteci.  
  
##  <a name="operator_neq"></a> operator! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> operator == 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
