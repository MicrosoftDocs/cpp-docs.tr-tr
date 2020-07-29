---
title: Derleyici hatası C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: 8ea3a106e8819bf067203f220ca51e17b87bfe46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225468"
---
# <a name="compiler-error-c2632"></a>Derleyici hatası C2632

' type1 ' ve arkasından ' type2 ' geçersizdir

Bu hata, iki tür belirticisi arasında kod eksik olduğunda oluşabilir.

Aşağıdaki örnek C2632 oluşturur:

```cpp
// C2632.cpp
int float i;   // C2632
```

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin bir sonucu olarak da oluşturulabilir. **`bool`** Artık uygun bir tür. Önceki sürümlerde, **`bool`** bir typedef idi ve bu adla tanımlayıcılar oluşturabilirsiniz.

Aşağıdaki örnek C2632 oluşturur:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Bu hatayı düzeltmek için, kodun hem Visual Studio .NET 2003 hem de Visual C++ Visual Studio .NET sürümlerinde geçerli olması için tanımlayıcıyı yeniden adlandırın.
