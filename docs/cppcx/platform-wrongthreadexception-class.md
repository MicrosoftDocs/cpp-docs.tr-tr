---
title: Platform::WrongThreadException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
dev_langs:
- C++
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe772f1c2925ce28d0e445023ab14d82b9b3f23
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107698"
---
# <a name="platformwrongthreadexception-class"></a>Platform::WrongThreadException sınıfı

Bir iş parçacığı için iş parçacığının grubunu ait değil bir proxy nesnesi için bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md).

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca Bkz.

[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)