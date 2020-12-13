---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4263'
title: Derleyici Uyarısı (düzey 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: 7b7eb7fdf8e66ab5d09c8dc0f9511d3c88162084
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339151"
---
# <a name="compiler-warning-level-4-c4263"></a>Derleyici Uyarısı (düzey 4) C4263

' function ': üye işlev hiçbir taban sınıf sanal üye işlevini geçersiz kılmıyor

Sınıf işlevi tanımı, temel sınıftaki bir sanal işlevle aynı ada sahip ancak aynı sayıda veya bağımsız değişken türünde değil. Bu, temel sınıftaki sanal işlevi etkili bir şekilde gizler.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4263 oluşturur:

```cpp
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```
