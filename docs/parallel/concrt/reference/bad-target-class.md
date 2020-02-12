---
title: bad_target Sınıfı
ms.date: 11/04/2016
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
ms.openlocfilehash: 023607ff142b7fa39165cc9b5280a8e9345a3645
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142850"
---
# <a name="bad_target-class"></a>bad_target Sınıfı

Bu sınıf, bir ileti bloğuna gerçekleştirilen işlem için geçersiz olan bir hedefe işaretçi verildiğinde oluşan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_target : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[bad_target](#ctor)|Fazla Yüklendi. `bad_target` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum tipik olarak, bir hedef gibi farklı bir hedef için ayrılmış bir iletiyi kullanmaya çalışan veya tutamayan bir ayırmayı serbest bırakan bir iletiyi kullanmaya çalışan nedenlerle oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`bad_target`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>bad_target

`bad_target` nesnesi oluşturur.

```cpp
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)
