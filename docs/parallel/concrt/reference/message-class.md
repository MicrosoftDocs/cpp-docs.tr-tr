---
description: 'Hakkında daha fazla bilgi edinin: ileti sınıfı'
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
ms.openlocfilehash: 0e15dafd9606e68f7a6ed1bed3795791c0f6870c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202320"
---
# <a name="message-class"></a>message Sınıfı

İleti blokları arasında geçilen veri yükünü içeren temel ileti zarfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
İleti içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[İleti](#ctor)|Fazla Yüklendi. Bir `message` nesnesi oluşturur.|
|[~ ileti yok edicisi](#dtor)|Nesneyi yok eder `message` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add_ref](#add_ref)|Nesnenin başvuru sayısına ekler `message` . İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.|
|[msg_id](#msg_id)|Nesnenin KIMLIĞINI döndürür `message` .|
|[remove_ref](#remove_ref)|Nesnenin başvuru sayısından çıkartır `message` . İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[yük](#payload)|`message`Nesnesinin yükü.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`message`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add_ref"></a><a name="add_ref"></a> add_ref

Nesnenin başvuru sayısına ekler `message` . İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.

```cpp
long add_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısının yeni değeri.

## <a name="message"></a><a name="ctor"></a> İleti

Bir `message` nesnesi oluşturur.

```cpp
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

*_Id*<br/>
Bu iletinin benzersiz KIMLIĞI.

*_Msg*<br/>
Bir nesnenin başvurusu veya işaretçisi `message` .

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olarak bir nesne işaretçisi alan Oluşturucu, `message` parametresi ise [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_Msg` `NULL` .

## <a name="message"></a><a name="dtor"></a> ~ ileti

Nesneyi yok eder `message` .

```cpp
virtual ~message();
```

## <a name="msg_id"></a><a name="msg_id"></a> msg_id

Nesnenin KIMLIĞINI döndürür `message` .

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Dönüş Değeri

`runtime_object_identity` `message` Nesnesinin.

## <a name="payload"></a><a name="payload"></a> te

`message`Nesnesinin yükü.

```cpp
T const payload;
```

## <a name="remove_ref"></a><a name="remove_ref"></a> remove_ref

Nesnenin başvuru sayısından çıkartır `message` . İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.

```cpp
long remove_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısının yeni değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
