---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2872'
title: Derleyici hatası C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: b1b1bc09917e499b3b9e1c72070c4a6b19e9c523
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320567"
---
# <a name="compiler-error-c2872"></a>Derleyici hatası C2872

'*symbol*': belirsiz simge

Derleyici hangi simgeye başvuruyorsanız belirleyemiyor. Kapsam içinde, belirtilen ada sahip birden fazla sembol vardır. Dosya konumları ve derleyicinin belirsiz simge için bulduğu bildirimler için hata iletisini izleyen notlara bakın. Bu sorunu çözebilmeniz için, veya gibi ad alanını kullanarak belirsiz sembolü tamamen niteleyebilirsiniz `std::byte` `::byte` . Ayrıca, bir ad alanı [diğer adını](../../cpp/namespaces-cpp.md#namespace_aliases) , eklenen bir ad alanına, kaynak kodunuzda sembolleri ayırt etmek için uygun bir kısa ad vermek üzere kullanabilirsiniz.

Bir üst bilgi dosyası bir [using yönergesi](../../cpp/namespaces-cpp.md#using_directives)içeriyorsa ve yönergede belirtilen ad alanında da olan bir türü içeren sonraki bir üst bilgi dosyası varsa, C2872 oluşabilir **`using`** . **`using`** Yalnızca tüm üst bilgi dosyalarınız ile birlikte belirtildiğinde bir yönerge belirtin `#include` .

`Windows::Foundation::Metadata::Platform`Enum türü ve C++/CX-defined ad alanı arasındaki bir çakışma nedeniyle, C2872 Visual Studio 2013 oluşabilir `Platform` . Bu sorunu geçici olarak çözmek için şu adımları izleyin:

- Proje dosyalarından "using namespace Windows:: Foundation:: Metadata" yan tümcesini kaldırın.

- Bu ad alanına dahil olan herhangi bir tür için tam nitelikli adı belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, adlı bir değişkene belirsiz bir başvuru yapıldığından, C2872 oluşturur `i` ; aynı ada sahip iki değişken kapsam içinde olur:

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```
