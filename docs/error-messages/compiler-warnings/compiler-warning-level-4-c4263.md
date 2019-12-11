---
title: Derleyici Uyarısı (düzey 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: ed4b8561975f3d808781551e0d5f363d0d0088b8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991443"
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
