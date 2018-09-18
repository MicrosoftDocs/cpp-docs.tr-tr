---
title: Derleyici Uyarısı (düzey 1) C4674 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b2f945982e80b49403387241f29a50876274e66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024885"
---
# <a name="compiler-warning-level-1-c4674"></a>Derleyici Uyarısı (düzey 1) C4674

'method', 'static' olarak bildirilmeli ve tam olarak bir parametreye sahip

Bir dönüştürme operatörünün imzası doğru değil. Kullanıcı tanımlı bir dönüştürme yöntemi olarak kabul edilmez. İşleçleri tanımlama hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md) ve [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4674 oluşturur.

```
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
