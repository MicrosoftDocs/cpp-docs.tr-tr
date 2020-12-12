---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2953'
title: Derleyici hatası C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 3bfc51d08318a4870f993a1d0cfe86eb1a38929e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210625"
---
# <a name="compiler-error-c2953"></a>Derleyici hatası C2953

' tanımlayıcı ': sınıf şablonu zaten tanımlanmış

Kaynak dosyayı denetleyin ve diğer tanımlar için dosyaları ekleyin.

Aşağıdaki örnek C2953 oluşturur:

```cpp
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```
