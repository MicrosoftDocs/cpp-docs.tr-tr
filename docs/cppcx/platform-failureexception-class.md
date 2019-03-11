---
title: Platform::FailureException sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
helpviewer_keywords:
- Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
ms.openlocfilehash: f527271b50382a9aec1585e139a0083135315473
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750330"
---
# <a name="platformfailureexception-class"></a>Platform::FailureException sınıfı

İşlemi başarısız olduğunda oluşturulur. Bunu E_FAIL HRESULT eşdeğerdir.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfı.

### <a name="requirements"></a>Gereksinimler

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca bkz.

[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)
