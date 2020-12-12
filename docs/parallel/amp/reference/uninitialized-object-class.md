---
description: 'Hakkında daha fazla bilgi edinin: uninitialized_object sınıfı'
title: uninitialized_object Sınıfı
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 4929de9e865492c9fb468f5fac336f67fb307efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326396"
---
# <a name="uninitialized_object-class"></a>uninitialized_object Sınıfı

Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.

## <a name="syntax"></a>Syntax

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[uninitialized_object Oluşturucusu](#uninitialized_object)|`uninitialized_object` sınıfının yeni bir örneğini başlatır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="uninitialized_object"></a><a name="uninitialized_object"></a> uninitialized_object

Özel durumun yeni bir örneğini oluşturur `uninitialized_object` .

### <a name="syntax"></a>Sözdizimi

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

`uninitialized_object`Özel durum nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
