---
title: Derleyici Uyarısı (düzey 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: 441d01eca7c8266b6d7948508eeb561341e64c57
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447762"
---
# <a name="compiler-warning-level-4-c4459"></a>Derleyici Uyarısı (düzey 4) C4459

> bildirimi '*tanımlayıcı*' genel bildirimi gizliyor

Bildirimi *tanımlayıcı* yerel kapsamda aynı adlı bildirimi gizler *tanımlayıcı* genel kapsamda. Bu uyarı, başvuruları size sağlar *tanımlayıcı* bu kapsamda amacınızla olmayabilir veya genel sürümünü değil, yerel olarak bildirilen sürümüne çözün. Genel olarak, iyi bir mühendislik uygulama olarak genel değişkenler kullanımını en aza öneririz. Genel ad alanı kirliliği en aza indirmek için genel değişkenler adlandırılmış bir ad alanı kullanılmasını öneririz.

Bu uyarıyı Microsoft Visual Studio 2015'te yeni C++ 18.00 derleyici sürümü. Bu sürüm derleyicinin veya kodunuzu geçirme sırasında daha sonra uyarıları bastırmak için kullanmak [/Wv:18](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4459 oluşturur:

```cpp
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() {
    int global_or_local; // warning C4459
    global_or_local = 2;
}
```

Bu sorunu çözmenin bir yolu olan bir ad alanı, globals oluşturulur, ancak özelliğini bir `using` tüm başvuruların belirsiz kullanmak için bu ad alanı, kapsama alınmak üzere yönergesi tam adları:

```cpp
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() {
    int global_or_local; // OK
    global_or_local = 2;
    globals::global_or_local = 3;
}
```
