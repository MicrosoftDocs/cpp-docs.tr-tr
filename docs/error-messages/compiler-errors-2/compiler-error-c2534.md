---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2534'
title: Derleyici hatası C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: fbdc4c292a8eb59ee9ab51de0100455139473f7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302081"
---
# <a name="compiler-error-c2534"></a>Derleyici hatası C2534

' tanımlayıcı ': Oluşturucu bir değer döndüremez

Oluşturucu bir değer döndüremez veya dönüş türüne sahip olamaz ( **`void`** dönüş türü bile).

Bu hata, **`return`** Oluşturucu tanımından deyimleri kaldırarak düzeltilebilir.

Aşağıdaki örnek C2534 oluşturur:

```cpp
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
