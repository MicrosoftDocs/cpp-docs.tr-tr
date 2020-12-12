---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4459'
title: Derleyici Uyarısı (düzey 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: cc074c0624a392ce058a284eb21661d7d34ae11f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251407"
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
