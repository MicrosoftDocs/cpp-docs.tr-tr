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
ms.openlocfilehash: 2d5d028739bdf1b1ac31fafe3719b7f3a98fbb07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591904"
---
# <a name="outofmemory-class"></a>out_of_memory Sınıfı

Bir yöntem sistem ya da cihaz belleği olmaması nedeniyle başarısız olduğunda oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[out_of_memory Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `out_of_memory` sınıfı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** eşzamanlılık
## <a name="ctor"></a> out_of_memory

Sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir örneğini `out_of_memory` sınıfı.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
