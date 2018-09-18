---
title: Derleyici Uyarısı (düzey 4) C4263 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4263
dev_langs:
- C++
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf93a010ac10b8b55bd22b9ab2db12d77a02c13a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079641"
---
# <a name="compiler-warning-level-4-c4263"></a>Derleyici Uyarısı (düzey 4) C4263

'function': üye işlev hiçbir taban sınıfı sanal üye işlevini Geçersiz Kılmıyor

Sınıf işlev tanımı aynı sayıda veya bağımsız değişken türü bir temel sınıf sanal işlevi olarak aynı ada sahip. Bu, temel sınıfta sanal işlev etkili bir şekilde gizler.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4263 oluşturur:

```
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