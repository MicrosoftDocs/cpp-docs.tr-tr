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
ms.openlocfilehash: 700d052b6f22c970387a3ab45d299538a5b74e1b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139535"
---
# <a name="message-class"></a>message Sınıfı

İleti blokları arasında geçilen veri yükünü içeren temel ileti zarfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
İleti içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|`T`için bir tür diğer adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[message](#ctor)|Fazla Yüklendi. `message` nesnesi oluşturur.|
|[~ ileti yok edicisi](#dtor)|`message` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add_ref](#add_ref)|`message` nesne için başvuru sayısına ekler. İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.|
|[msg_id](#msg_id)|`message` nesnesinin KIMLIĞINI döndürür.|
|[remove_ref](#remove_ref)|`message` nesne için başvuru sayısından çıkartır. İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[te](#payload)|`message` nesnesinin yükü.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`message`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add_ref"></a>add_ref

`message` nesne için başvuru sayısına ekler. İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.

```cpp
long add_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısının yeni değeri.

## <a name="ctor"></a>İleti

`message` nesnesi oluşturur.

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
`message` nesnesine bir başvuru veya işaretçi.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olarak bir `message` nesnesine işaretçi alan Oluşturucu, parametre `_Msg` `NULL`ise [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum oluşturur.

## <a name="dtor"></a>~ ileti

`message` nesnesini yok eder.

```cpp
virtual ~message();
```

## <a name="msg_id"></a>msg_id

`message` nesnesinin KIMLIĞINI döndürür.

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Dönüş Değeri

`message` nesnesinin `runtime_object_identity`.

## <a name="payload"></a>te

`message` nesnesinin yükü.

```cpp
T const payload;
```

## <a name="remove_ref"></a>remove_ref

`message` nesne için başvuru sayısından çıkartır. İleti ömrünü belirlemede başvuru saymayı gerektiren ileti blokları için kullanılır.

```cpp
long remove_ref();
```

### <a name="return-value"></a>Dönüş Değeri

Başvuru sayısının yeni değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
