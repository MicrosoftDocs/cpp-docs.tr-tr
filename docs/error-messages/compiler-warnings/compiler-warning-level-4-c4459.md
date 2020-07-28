---
title: Derleyici Uyarısı (düzey 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: d6d0a802f9f628145fbc5910aca805a5b01b94d2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214379"
---
# <a name="compiler-warning-level-4-c4459"></a>Derleyici Uyarısı (düzey 4) C4459

> '*Identifier*' bildirimi genel bildirimi gizliyor

Yerel kapsamdaki *tanımlayıcının* bildirimi, genel kapsamdaki özdeş olarak adlandırılmış *tanımlayıcının* bildirimini gizler. Bu uyarı, bu kapsamdaki *tanımlayıcıya* yapılan başvuruların, genel sürümü değil, yerel olarak belirtilen sürüme çözümlendiğine, sizin amacınızı etkileyebilecek veya bu olmayabilir. Genellikle, genel değişkenlerin iyi bir mühendislik uygulaması olarak kullanımını en aza indirmenizi öneririz. Genel ad alanının kirlenmesini en aza indirmek için, genel değişkenler için adlandırılmış bir ad alanı kullanmanızı öneririz.

Bu uyarı, Microsoft C++ derleyicisi sürüm 18,00 ' de Visual Studio 2015 ' de yenidir. Kodunuzu geçirirken derleyicinin veya daha sonraki sürümden gelen uyarıları gizlemek için [/WV: 18](../../build/reference/compiler-option-warning-level.md) derleyici seçeneğini kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4459 oluşturur:

```cpp
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() {
    int global_or_local; // warning C4459
    global_or_local = 2;
}
```

Bu sorunu gidermenin bir yolu, Globals 'niz için bir ad alanı oluşturmaktır, ancak **`using`** Bu ad alanını kapsama getirmek için bir yönerge kullanmaz, bu nedenle tüm başvuruların belirsiz nitelikli adları kullanması gerekir:

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
