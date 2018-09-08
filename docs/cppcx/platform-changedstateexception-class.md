---
title: Platform::ChangedStateException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fa22457626892e1ebbf02d6859577b2795f7d04
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105269"
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException sınıfı

Bir nesnenin iç durumu değiştiğinde, dolayısıyla yöntemin sonuçları geçersiz kılarak anında oluşturulur.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Açıklamalar

Yöntemin sonuçları geçersiz kılmalarını üst koleksiyon değiştikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü yöntemler çağrıldığında, bu özel durum burada örnek verilebilir.

Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfı.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca Bkz.

[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)