---
title: message Sınıfı
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 6b0c37f61ef437662a4e624c3a81edb526e7464c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636870"
---
# <a name="message-class"></a>message Sınıfı

İleti blokları arasında geçirilen veri yükü içeren temel ileti zarfı.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıştaki yükün yapılacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[message](#ctor)|Fazla Yüklendi. Oluşturur bir `message` nesne.|
|[~ message yok Edicisi](#dtor)|Yok eder `message` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add_ref](#add_ref)|Başvuru sayısı ekler `message` nesne. İleti yaşam süresi belirlemek için başvuru sayımını gereken ileti blokları için kullanılır.|
|[msg_id](#msg_id)|Kimliğini döndürür `message` nesne.|
|[remove_ref](#remove_ref)|Başvuru sayımını alanından çıkarır `message` nesne. İleti yaşam süresi belirlemek için başvuru sayımını gereken ileti blokları için kullanılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Yükü](#payload)|Yükü `message` nesne.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`message`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="add_ref"></a> add_ref

Başvuru sayısı ekler `message` nesne. İleti yaşam süresi belirlemek için başvuru sayımını gereken ileti blokları için kullanılır.

```
long add_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısı yeni değeri.

##  <a name="ctor"></a> İleti

Oluşturur bir `message` nesne.

```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>Parametreler

*_P*<br/>
Bu iletinin yükü.

*_Kimliği*<br/>
Bu iletinin benzersiz kimliği.

*_Msg*<br/>
Bir başvuru veya işaretçi bir `message` nesne.

### <a name="remarks"></a>Açıklamalar

Bir işaretçiye alan oluşturucu bir `message` nesnesini atan bir bağımsız değişken olarak bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_Msg` olduğu `NULL`.

##  <a name="dtor"></a> ~ iletisi

Yok eder `message` nesne.

```
virtual ~message();
```

##  <a name="msg_id"></a> msg_id

Kimliğini döndürür `message` nesne.

```
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Dönüş Değeri

`runtime_object_identity` , `message` Nesne.

##  <a name="payload"></a> Yükü

Yükü `message` nesne.

```
T const payload;
```

##  <a name="remove_ref"></a> remove_ref

Başvuru sayımını alanından çıkarır `message` nesne. İleti yaşam süresi belirlemek için başvuru sayımını gereken ileti blokları için kullanılır.

```
long remove_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısı yeni değeri.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
