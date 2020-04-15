---
title: out_of_memory Sınıfı
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: e716d4952bdb9634cc0d195285d3a65c5c06b0a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336812"
---
# <a name="out_of_memory-class"></a>out_of_memory Sınıfı

Sistem veya aygıt belleği eksikliği nedeniyle bir yöntem başarısız olduğunda atılan özel durum.

## <a name="syntax"></a>Sözdizimi

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[out_of_memory Yapıcı](#ctor)|`out_of_memory` sınıfının yeni bir örneğini başlatır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt.h

**Ad alanı:** Eşzamanlılık

## <a name="out_of_memory"></a><a name="ctor"></a>out_of_memory

Sınıfın yeni bir örneğini başolarak adlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın yeni bir `out_of_memory` örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
