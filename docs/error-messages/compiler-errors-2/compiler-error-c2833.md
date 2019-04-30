---
title: Derleyici Hatası C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408374"
---
# <a name="compiler-error-c2833"></a>Derleyici Hatası C2833

'operator işleci' tanınan bir işleç veya tür değil

Word `operator` geçersiz kılmak istediğiniz bir işleç veya dönüştürmek istediğiniz bir türe göre gelmelidir.

Yönetilen bir tür tanımlayabilirsiniz işleçleri bir listesi için bkz. [kullanıcı tanımlı işleçler](../../dotnet/user-defined-operators-cpp-cli.md).

Aşağıdaki örnek, C2833 oluşturur:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```