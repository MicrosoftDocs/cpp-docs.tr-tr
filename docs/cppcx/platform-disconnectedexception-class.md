---
title: Platform::DisconnectedException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e46ddc82f867d3c126b9a7e8d259ba0c3c22bfde
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101982"
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