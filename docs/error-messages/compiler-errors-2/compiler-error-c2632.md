---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2632'
title: Derleyici hatası C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b6f1091b512d3a01efa933c998bde3d0885bbff1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123519"
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
