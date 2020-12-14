---
description: 'Hakkında daha fazla bilgi edinin: unsupported_os sınıfı'
title: unsupported_os Sınıfı
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: 1f9ee74db42d2b34c1b4e24a1951d84a442224bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188098"
---
# <a name="unsupported_os-class"></a>unsupported_os Sınıfı

Bu sınıf, desteklenmeyen bir işletim sistemi kullanıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class unsupported_os : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unsupported_os](#ctor)|Fazla Yüklendi. Bir `unsupported_os` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`unsupported_os`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="unsupported_os"></a><a name="ctor"></a> unsupported_os

Bir `unsupported_os` nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
