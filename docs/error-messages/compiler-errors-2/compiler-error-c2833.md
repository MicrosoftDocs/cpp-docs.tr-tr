---
title: Derleyici Hatası C2833 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53360c1eaf81ad407589fbdb125d9e6fe017708e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070177"
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