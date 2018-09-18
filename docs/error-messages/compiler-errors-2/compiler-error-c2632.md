---
title: Derleyici Hatası C2632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf03c35c60bebb52c94ed04cca2349f35c06fbc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093656"
---
# <a name="compiler-error-c2632"></a>Derleyici Hatası C2632

'type1 'type2' tarafından izlenen' geçersiz

Bu hata kodu arasında iki tür tanımlayıcıları vardır eksikse, neden olabilir.

Aşağıdaki örnek, C2632 oluşturur:

```
// C2632.cpp
int float i;   // C2632
```

Bu hata, Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir. `bool` düzgün türe sunulmuştur. Önceki sürümlerde, `bool` typedef oluştu ve bu ada sahip tanımlayıcılar oluşturabilirsiniz.

Aşağıdaki örnek, C2632 oluşturur:

```
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Kod Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümlerinde geçerli olmasını sağlayacak şekilde bu hatayı gidermek için tanımlayıcı yeniden adlandırın.