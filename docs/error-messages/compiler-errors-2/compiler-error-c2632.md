---
title: Derleyici Hatası C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b92d44bcfd04d4de7b39c5bdab5ee146d9b6693b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257640"
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