---
title: initonly (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
f1_keywords:
- initonly_cpp
- initonly
dev_langs:
- C++
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1c98c2ab1391f65d31e64a60bf0bd86485776ad6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429968"
---
# <a name="initonly-ccli"></a>initonly (C++/CLI)

**initonly** olduğundan bu değişken ataması gösteren bir bağlama duyarlı anahtar sözcüğü, yalnızca bildirimin veya aynı sınıftaki statik bir oluşturucuda bir parçası olarak gerçekleşebilir.

Aşağıdaki örnek nasıl kullanılacağını gösterir `initionly`:

```
// mcpp_initonly.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst1;

   initonly
   static int staticConst2 = 0;

   static Y1() {
      staticConst1 = 0;
   }
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)