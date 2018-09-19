---
title: Derleyici Hatası C3194 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3194
dev_langs:
- C++
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 923e4d5535a1be4f4c8a3f7b60730eb6a656ac33
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077106"
---
# <a name="compiler-error-c3194"></a>Derleyici Hatası C3194

'member': bir değer türünün bir atama işleci olamaz

Kopya Oluşturucusu veya kopya atama işleci gibi derleyici tarafından otomatik çağırma gerektiren özel üye işlevleri, bir değer sınıfı içinde desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3194 oluşturur.

```
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```