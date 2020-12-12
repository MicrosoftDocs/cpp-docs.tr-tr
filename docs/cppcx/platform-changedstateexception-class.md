---
description: 'Daha fazla bilgi edinin: Platform:: ChangedStateException sınıfı'
title: 'Platform:: ChangedStateException sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
ms.openlocfilehash: baabf54cacfc4dd03256b569fb868c402ea98a97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284037"
---
# <a name="platformchangedstateexception-class"></a>Platform:: ChangedStateException sınıfı

Bir nesnenin iç durumu değiştiğinde oluşturulur, böylece yöntemin sonuçları geçersiz olur.

## <a name="syntax"></a>Syntax

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Bu özel durumun oluşturulduğu bir örnek, üst koleksiyon değiştirildikten sonra bir koleksiyon yineleyicisinin veya koleksiyon görünümünün yöntemleri çağrıldığında yönteminin sonuçları geçersiz kılınırken oluşur.

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfına bakın.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: COMException sınıfı](../cppcx/platform-comexception-class.md)
