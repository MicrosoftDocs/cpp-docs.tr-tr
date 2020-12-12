---
description: 'Hakkında daha fazla bilgi edinin: operation_timed_out sınıfı'
title: operation_timed_out Sınıfı
ms.date: 11/04/2016
f1_keywords:
- operation_timed_out
- CONCRT/concurrency::operation_timed_out
- CONCRT/concurrency::operation_timed_out::operation_timed_out
helpviewer_keywords:
- operation_timed_out class
ms.assetid: 963efe1d-a6e0-477c-9a70-d93d8412c897
ms.openlocfilehash: 476dfc2d7f29b2769c076ff525f3d0eb1e20a8f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236561"
---
# <a name="operation_timed_out-class"></a>operation_timed_out Sınıfı

Bu sınıf, bir işlem zaman aşımına uğramışsa oluşturulan özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class operation_timed_out : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[operation_timed_out](#ctor)|Fazla Yüklendi. Bir `operation_timed_out` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`operation_timed_out`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="operation_timed_out"></a><a name="ctor"></a> operation_timed_out

Bir `operation_timed_out` nesnesi oluşturur.

```cpp
explicit _CRTIMP operation_timed_out(_In_z_ const char* _Message) throw();

operation_timed_out() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
