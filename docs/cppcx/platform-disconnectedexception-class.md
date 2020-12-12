---
description: 'Daha fazla bilgi edinin: Platform::D isconnectedException sınıfı'
title: Platform::D isconnectedException sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
ms.openlocfilehash: 6ccfedc143d0245582c7c1f95110207d583949fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195326"
---
# <a name="platformdisconnectedexception-class"></a>Platform::D isconnectedException sınıfı

COM proxy nesnesi artık mevcut olmayan bir COM sunucusuna başvurmasına çalıştığında oluşturulur

## <a name="syntax"></a>Syntax

```
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Sınıf A, ayrı bir işlemde olan başka bir sınıfa (Sınıf B) başvurduğunda, A sınıfı, B sınıfını tutan işlem dışı COM sunucusu ile iletişim kurmak için bir proxy nesnesi gerektirir. Bazen sunucu, bunu bilmeden bir sınıf olmadan belleğin dışına geçebilir. Bu durumda RPC_E_DISCONNECTED özel durumu oluşturulur ve platforma çevrilir::D isconnectedException. İçindeki bir senaryo, bir olay kaynağı kendisine geçirilen bir temsilciyi çağırdığında, ancak bu temsilci olaya abone olduktan sonra bir noktada yok edilmediğinde oluşur. Bu durumda, olay kaynağı o temsilciyi kendi çağırma listesinden kaldırır.

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfına bakın.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: COMException sınıfı](../cppcx/platform-comexception-class.md)
