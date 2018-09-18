---
title: Derleyici Uyarısı (düzey 1) C4677 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6a3f57ba0e3d4c15c83711a86bb8482fa8b0596
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049396"
---
# <a name="compiler-warning-level-1-c4677"></a>Derleyici Uyarısı (düzey 1) C4677

'function': özel üyenin olmayan imzası 'private_type' derleme özel türünü içeriyor

Genel erişilebilirlik derlemenin dışında olan bir türü derleme dışından özel erişimi olan bir türü kullanır. Genel bütünleştirilmiş kod türe başvuran bir bileşen türü üyesi veya derleme özel türünü başvuran üyeleri kullanmanız mümkün olmayacaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4677 oluşturur.

```
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```