---
description: 'Hakkında daha fazla bilgi edinin: message_processor Sınıfı'
title: message_processor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: f74314bde6e12ea8b00bfc7bfd2567ca15864f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202203"
---
# <a name="message_processor-class"></a>message_processor Sınıfı

`message_processor`Sınıfı, nesneleri işlemek için soyut temel sınıftır `message` . İleti sıralaması hakkında garanti yoktur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bu nesne tarafından işlenen iletiler içindeki yükün veri türü `message_processor` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Türetilmiş bir sınıfta geçersiz kılınırsa, iletileri zaman uyumsuz olarak bloğa koyar.|
|[sync_send](#sync_send)|Türetilmiş bir sınıfta geçersiz kılındıklarında, iletileri zaman uyumlu olarak bloğa koyar.|
|[bekleneceğini](#wait)|Türetilmiş bir sınıfta geçersiz kılınırsa, tüm zaman uyumsuz işlemlerin tamamlanmasını bekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, iletilerin bloğa iletme işlemini gerçekleştirir. Her yeni ileti eklendiğinde ve kuyruğun boş olduğu her seferinde bir kez çağırılır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`message_processor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="async_send"></a><a name="async_send"></a> async_send

Türetilmiş bir sınıfta geçersiz kılınırsa, iletileri zaman uyumsuz olarak bloğa koyar.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
`message`Zaman uyumsuz olarak gönderilmek üzere bir nesne.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="process_incoming_message"></a><a name="process_incoming_message"></a> process_incoming_message

Türetilmiş bir sınıfta geçersiz kılınırsa, iletilerin bloğa iletme işlemini gerçekleştirir. Her yeni ileti eklendiğinde ve kuyruğun boş olduğu her seferinde bir kez çağırılır.

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Açıklamalar

İleti bloğu uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

Türetilmiş bir sınıfta geçersiz kılındıklarında, iletileri zaman uyumlu olarak bloğa koyar.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
`message`Zaman uyumlu olarak gönderilmek üzere bir nesne.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="wait"></a><a name="wait"></a> bekleneceğini

Türetilmiş bir sınıfta geçersiz kılınırsa, tüm zaman uyumsuz işlemlerin tamamlanmasını bekler.

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[ordered_message_processor sınıfı](ordered-message-processor-class.md)
