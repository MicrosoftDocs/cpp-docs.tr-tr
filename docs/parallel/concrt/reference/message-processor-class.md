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
ms.openlocfilehash: be6cb1c614a41919663a4cc063da66679556e498
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409960"
---
# <a name="messageprocessor-class"></a>message_processor Sınıfı

`message_processor` İşlenmesi için soyut temel sınıfı `message` nesneleri. İletilerin sıralama hakkında bir garanti yoktur.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Bu akıştaki yükün iletileri veri türü ele `message_processor` nesne.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Türetilen bir sınıfta geçersiz kılındığında, iletileri zaman uyumsuz olarak bloğu içine yerleştirir.|
|[sync_send](#sync_send)|Türetilen bir sınıfta geçersiz kılındığında, iletileri eşzamanlı olarak bloğu içine yerleştirir.|
|[bekleme](#wait)|Türetilen bir sınıfta geçersiz kılındığında, tamamlamak tüm için zaman uyumsuz işlemler bekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Türetilen bir sınıfta geçersiz kılındığında, iletme iletilerinin işlenmesini bloğuna gerçekleştirir. Yeni bir ileti eklendiğinde ve sıranın boş olacak şekilde bulunan her zaman bir kez çağrılır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`message_processor`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="async_send"></a> async_send

Türetilen bir sınıfta geçersiz kılındığında, iletileri zaman uyumsuz olarak bloğu içine yerleştirir.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
A `message` zaman uyumsuz olarak göndermek için nesne.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları, bu yöntemin üzerine yazması gerekir.

##  <a name="process_incoming_message"></a> process_incoming_message

Türetilen bir sınıfta geçersiz kılındığında, iletme iletilerinin işlenmesini bloğuna gerçekleştirir. Yeni bir ileti eklendiğinde ve sıranın boş olacak şekilde bulunan her zaman bir kez çağrılır.

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Açıklamalar

İleti bloğu uygulamalarında, bu yöntemin üzerine yazması gerekir.

##  <a name="sync_send"></a> sync_send

Türetilen bir sınıfta geçersiz kılındığında, iletileri eşzamanlı olarak bloğu içine yerleştirir.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
A `message` zaman uyumlu olarak göndermek için nesne.

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları, bu yöntemin üzerine yazması gerekir.

##  <a name="wait"></a> bekleme

Türetilen bir sınıfta geçersiz kılındığında, tamamlamak tüm için zaman uyumsuz işlemler bekler.

```
virtual void wait() = 0;
```

### <a name="remarks"></a>Açıklamalar

İşlemci uygulamaları, bu yöntemin üzerine yazması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ordered_message_processor Sınıfı](ordered-message-processor-class.md)
