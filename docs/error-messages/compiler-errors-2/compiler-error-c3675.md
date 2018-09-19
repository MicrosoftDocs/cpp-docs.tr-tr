---
title: Derleyici Hatası C3675 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4b6656753ab4a611dcb80d1473e0b44bf47a270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094786"
---
# <a name="compiler-error-c3675"></a>Derleyici Hatası C3675

'function': 'property' tanımlı olduğundan ayrıldı

Basit bir özelliğin bildirdiğinizde, derleyici alma ve ayarlama erişimci yöntemlerinin ve bu oluşturur adlardır programınızı kapsamı içinde mevcut.  Derleyicinin ürettiği adları get_ ve set_ özellik adının önüne eklenerek oluşturulur.  Bu nedenle, İşlevler derleyici tarafından oluşturulan erişimcileri aynı ada sahip bildiremezsiniz.

Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3675 oluşturur.

```
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```