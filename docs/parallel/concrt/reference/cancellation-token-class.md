---
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
ms.openlocfilehash: 34743ce48510eec9d8f7862e5ed951a722932962
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422243"
---
# <a name="cancellation_token-class"></a>cancellation_token Sınıfı

`cancellation_token` sınıfı, bazı bir işlemin iptal edilip edilmeyeceğini belirleme yeteneğini temsil eder. Belirli bir belirteç, örtük iptal sağlamak için bir `task_group`, `structured_task_group`veya `task` ilişkilendirilebilir. Ayrıca, iptal için yoklanabilir ya da ilişkili `cancellation_token_source` iptal edildiğinde, ve için kayıtlı bir geri çağırma olur.

## <a name="syntax"></a>Sözdizimi

```cpp
class cancellation_token;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[cancellation_token](#ctor)||
|[~ cancellation_token yok edici](#dtor)||

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[deregister_callback](#deregister_callback)|Kayıt sırasında döndürülen `cancellation_token_registration` nesnesine göre `register` yöntemi aracılığıyla önceden kaydedilmiş bir geri aramayı kaldırır.|
|[is_cancelable](#is_cancelable)|Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge döndürür.|
|[is_canceled](#is_canceled)|Belirteç iptal edildiyse **true** döndürür.|
|[seçim](#none)|İptal 'e hiçbir şekilde tabi olmayan bir iptal belirteci döndürür.|
|[register_callback](#register_callback)|Belirteç ile bir geri çağırma işlevi kaydeder. Belirteç iptal edildiğinde, geri çağırma yapılır. Belirteç bu yöntemin çağrıldığı noktada zaten iptal edilirse, geri çağırma işlemi hemen ve zaman uyumlu olarak yapılır.|

### <a name="public-operators"></a>Genel İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[işleç =](#operator_eq)||
|[işleç = =](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`cancellation_token`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** pplcancellation_token. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ cancellation_token

```cpp
~cancellation_token();
```

## <a name="ctor"></a>cancellation_token

```cpp
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kopyalanacak veya taşınacak cancellation_token.

## <a name="deregister_callback"></a>deregister_callback

Kayıt sırasında döndürülen `cancellation_token_registration` nesnesine göre `register` yöntemi aracılığıyla önceden kaydedilmiş bir geri aramayı kaldırır.

```cpp
void deregister_callback(const cancellation_token_registration& _Registration) const;
```

### <a name="parameters"></a>Parametreler

*_Registration*<br/>
Kaydı kaldırılacak geri aramaya karşılık gelen `cancellation_token_registration` nesnesi. Bu belirtecin daha önce `register` metoduna yapılan çağrıdan döndürülmesi gerekir.

## <a name="is_cancelable"></a>is_cancelable

Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge döndürür.

```cpp
bool is_cancelable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belirtecin iptal edilip edilmeyeceğini belirten bir gösterge.

## <a name="is_canceled"></a>is_canceled

Belirteç iptal edildiyse **true** döndürür.

```cpp
bool is_canceled() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirteç iptal edilirse **true** değeri; Aksi takdirde, değeri **false**olur.

## <a name="none"></a>seçim

İptal 'e hiçbir şekilde tabi olmayan bir iptal belirteci döndürür.

```cpp
static cancellation_token none();
```

### <a name="return-value"></a>Dönüş Değeri

İptal edilmemiş bir iptal belirteci.

## <a name="operator_neq"></a>işleç! =

```cpp
bool operator!= (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Karşılaştırılacak `cancellation_token`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_eq"></a>işleç =

```cpp
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Atanacak `cancellation_token`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_eq_eq"></a>işleç = =

```cpp
bool operator== (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Karşılaştırılacak `cancellation_token`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="register_callback"></a>register_callback

Belirteç ile bir geri çağırma işlevi kaydeder. Belirteç iptal edildiğinde, geri çağırma yapılır. Belirteç bu yöntemin çağrıldığı noktada zaten iptal edilirse, geri çağırma işlemi hemen ve zaman uyumlu olarak yapılır.

```cpp
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Bu `cancellation_token` iptal edildiğinde geri çağrılacak işlev nesnesinin türü.

*_Func*<br/>
Bu `cancellation_token` iptal edildiğinde geri çağrılacak işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce kaydedilen bir geri aramanın kaydını silmek ve oluşmasını engellemek için `deregister` yönteminde kullanılabilecek `cancellation_token_registration` nesne. Yöntemi, [cancellation_token:: None](#none) yöntemi kullanılarak oluşturulan bir `cancellation_token` nesnesi üzerinde çağrılırsa [invalid_operation](invalid-operation-class.md) bir özel durum oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
