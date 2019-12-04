---
title: Derleyici hatası C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: f69d43bf50f5f13957e49d1e9ffa798a3db5a7b3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754699"
---
# <a name="compiler-error-c2632"></a>Derleyici hatası C2632

' type1 ' ve arkasından ' type2 ' geçersizdir

Bu hata, iki tür belirticisi arasında kod eksik olduğunda oluşabilir.

Aşağıdaki örnek C2632 oluşturur:

```cpp
// C2632.cpp
int float i;   // C2632
```

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin bir sonucu olarak da oluşturulabilir. `bool` artık uygun bir tür. Önceki sürümlerde, `bool` bir typedef idi ve bu adla tanımlayıcılar oluşturabilirsiniz.

Aşağıdaki örnek C2632 oluşturur:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Bu hatayı düzeltmek için, kodun hem Visual Studio .NET 2003 hem de Visual Studio .NET sürümlerinde C++geçerli olması için tanımlayıcıyı yeniden adlandırın.
