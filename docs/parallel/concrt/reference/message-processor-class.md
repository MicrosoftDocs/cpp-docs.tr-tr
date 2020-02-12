---
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
ms.openlocfilehash: 88944b2d935eebd0e031be1431c2a0f4efa3d760
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139475"
---
# <a name="message_processor-class"></a>message_processor Sınıfı

`message_processor` sınıfı, `message` nesnelerinin işlenmesine yönelik soyut temel sınıftır. İleti sıralaması hakkında garanti yoktur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bu `message_processor` nesnesi tarafından işlenen iletiler içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|`T`için bir tür diğer adı.|

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

## <a name="async_send"></a>async_send

Türetilmiş bir sınıfta geçersiz kılınırsa, iletileri zaman uyumsuz olarak bloğa koyar.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Zaman uyumsuz olarak gönderilmek üzere bir `message` nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="process_incoming_message"></a>process_incoming_message

Türetilmiş bir sınıfta geçersiz kılınırsa, iletilerin bloğa iletme işlemini gerçekleştirir. Her yeni ileti eklendiğinde ve kuyruğun boş olduğu her seferinde bir kez çağırılır.

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Açıklamalar

İleti bloğu uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="sync_send"></a>sync_send

Türetilmiş bir sınıfta geçersiz kılındıklarında, iletileri zaman uyumlu olarak bloğa koyar.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Zaman uyumlu olarak göndermek için bir `message` nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="wait"></a>bekleneceğini

Türetilmiş bir sınıfta geçersiz kılınırsa, tüm zaman uyumsuz işlemlerin tamamlanmasını bekler.

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları bu yöntemi geçersiz kılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ordered_message_processor Sınıfı](ordered-message-processor-class.md)
