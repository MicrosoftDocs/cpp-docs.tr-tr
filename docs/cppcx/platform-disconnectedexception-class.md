---
title: Platform::DisconnectedException sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
ms.openlocfilehash: 2d4f8f4cb52fdb7e50c36eb3f0255bd85c15dbb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477148"
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException sınıfı

Bir COM proxy nesnesi artık bir COM sunucusu başvuru denediğinde

## <a name="syntax"></a>Sözdizimi

```
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Ne zaman sınıf b tutan sınıf A başvuruları, sınıfı gibi ayrı bir işlem içinde başka bir sınıf (sınıf B) işlem dışı COM sunucusu ile iletişim kurmak için bir proxy nesnesi gerektirir. Bazen sunucu yetersiz bellek sınıfı olmadan bir yazabilmesidir gidebilirsiniz. Bu durumda RPC_E_DISCONNECTED özel durum ve için Platform::DisconnectedException çevrilir. Bir senaryoda olduğunu ortaya olay kaynağı kendisine geçirilen bir temsilciyi çağırır, ancak belirli bir noktada temsilci olaya abone sonra edilmiş andır. Bu durumda, olay kaynağı bu temsilciyi çağırma listesinden kaldırır.

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfı.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca Bkz.

[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)