---
description: 'Hakkında daha fazla bilgi edinin: cancellation_token sınıfı'
title: cancellation_token Sınıfı
ms.date: 11/04/2016
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
ms.openlocfilehash: 3f97d0f6e55f06b4b75b22cc1ae6eefa05b50f85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172199"
---
# <a name="cancellation_token-class"></a>cancellation_token Sınıfı

`cancellation_token`Sınıfı, bir işlemin iptal edilip edilmeyeceğini belirleme yeteneğini temsil eder. Belirli bir belirteç `task_group` , bir, `structured_task_group` veya `task` örtülü iptal sağlamak için ilişkilendirilebilir. Ayrıca, iptal için yoklanabilir veya varsa ve ilişkili bir geri çağırma `cancellation_token_source` işlemi iptal edilir.

## <a name="syntax"></a>Syntax

```cpp
class cancellation_token;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[cancellation_token](#ctor)||
|[~ cancellation_token yok edici](#dtor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[deregister_callback](#deregister_callback)|`register`Kayıt sırasında döndürülen nesneye göre yöntemi aracılığıyla önceden kaydedilmiş bir geri aramayı kaldırır `cancellation_token_registration` .|
|[is_cancelable](#is_cancelable)|Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge döndürür.|
|[is_canceled](#is_canceled)|**`true`** Belirtecin iptal edilip edilmediğinde döndürür.|
|[yok](#none)|İptal 'e hiçbir şekilde tabi olmayan bir iptal belirteci döndürür.|
|[register_callback](#register_callback)|Belirteç ile bir geri çağırma işlevi kaydeder. Belirteç iptal edildiğinde, geri çağırma yapılır. Belirteç bu yöntemin çağrıldığı noktada zaten iptal edilirse, geri çağırma işlemi hemen ve zaman uyumlu olarak yapılır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](#operator_neq)||
|[işleç =](#operator_eq)||
|[işleç = =](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`cancellation_token`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** pplcancellation_token. h

**Ad alanı:** eşzamanlılık

## <a name="cancellation_token"></a><a name="dtor"></a> ~ cancellation_token

```cpp
~cancellation_token();
```

## <a name="cancellation_token"></a><a name="ctor"></a> cancellation_token

```cpp
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kopyalanacak veya taşınacak cancellation_token.

## <a name="deregister_callback"></a><a name="deregister_callback"></a> deregister_callback

`register`Kayıt sırasında döndürülen nesneye göre yöntemi aracılığıyla önceden kaydedilmiş bir geri aramayı kaldırır `cancellation_token_registration` .

```cpp
void deregister_callback(const cancellation_token_registration& _Registration) const;
```

### <a name="parameters"></a>Parametreler

*_Registration*<br/>
`cancellation_token_registration`Kaydı kaldırılacak geri aramaya karşılık gelen nesne. Bu belirteç daha önce yönteme bir çağrıdan geri döndürülmüş olmalıdır `register` .

## <a name="is_cancelable"></a><a name="is_cancelable"></a> is_cancelable

Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge döndürür.

```cpp
bool is_cancelable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge.

## <a name="is_canceled"></a><a name="is_canceled"></a> is_canceled

**`true`** Belirtecin iptal edilip edilmediğinde döndürür.

```cpp
bool is_canceled() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Belirteç iptal edilirse değer; Aksi takdirde değer **`false`** .

## <a name="none"></a><a name="none"></a> seçim

İptal 'e hiçbir şekilde tabi olmayan bir iptal belirteci döndürür.

```cpp
static cancellation_token none();
```

### <a name="return-value"></a>Dönüş Değeri

İptal edilmemiş bir iptal belirteci.

## <a name="operator"></a><a name="operator_neq"></a> işleç! =

```cpp
bool operator!= (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
`cancellation_token`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_eq"></a> işleç =

```cpp
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
`cancellation_token`Atanacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_eq_eq"></a> işleç = =

```cpp
bool operator== (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
`cancellation_token`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="register_callback"></a><a name="register_callback"></a> register_callback

Belirteç ile bir geri çağırma işlevi kaydeder. Belirteç iptal edildiğinde, geri çağırma yapılır. Belirteç bu yöntemin çağrıldığı noktada zaten iptal edilirse, geri çağırma işlemi hemen ve zaman uyumlu olarak yapılır.

```cpp
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Bu iptal edildiğinde geri çağrılacak işlev nesnesinin türü `cancellation_token` .

*_Func*<br/>
Bu iptal edildiğinde geri çağrılacak işlev nesnesi `cancellation_token` .

### <a name="return-value"></a>Dönüş Değeri

`cancellation_token_registration` `deregister` Daha önce kaydedilen bir geri aramanın kaydını silmek ve oluşmasını engellemek için yönteminde kullanılabilen bir nesne. Yöntemi, [](invalid-operation-class.md) `cancellation_token` [cancellation_token:: None](#none) yöntemi kullanılarak oluşturulan bir nesne üzerinde çağrılırsa invalid_operation bir özel durum oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
