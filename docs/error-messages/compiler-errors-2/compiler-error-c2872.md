---
title: Derleyici Hatası C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: 103998c7872b683c7405796ee28bd550246ae9bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257620"
---
# <a name="compiler-error-c2872"></a>Derleyici Hatası C2872

'*sembol*': belirsiz simge

Derleyici başvurduğunuz hangi sembol belirlenemiyor. Belirtilen ada sahip birden fazla sembol kapsamdadır. Dosya konumları ve bildirimler için hata iletisi aşağıdaki notlar, belirsiz simgesi bulunan derleyici bakın. Bu sorunu gidermek için tam olarak belirsiz simge ad alanı, örneğin, kullanarak belirtebilme `std::byte` veya `::byte`. Ayrıca bir [ad alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) eklenen bir ad kullanmak için kullanışlı bir kısa ad simgeleri, kaynak kodunuzdaki belirsizliğini sunmak için.

Bir üstbilgi dosyası içeriyorsa C2872 oluşabilir bir [using yönergesi](../../cpp/namespaces-cpp.md#using_directives), ve bir sonraki üstbilgi dosyasına dahildir ayrıca belirtilen ad uzayında bir tür içeren `using` yönergesi. Belirtin bir `using` yönergesi yalnızca tüm ile belirtilen üst bilgi dosyalarınız sonra `#include`.

C2872 Visual Studio 2013'te arasında bir çakışma nedeniyle oluşabilir `Windows::Foundation::Metadata::Platform` sabit listesi türü ve C++/CX tanımlı `Platform` ad alanı. Bu sorunu çözmek için şu adımları izleyin:

- "Ad alanı Windows::Foundation::Metadata kullanma" yan tümcesi konumundan proje dosyaları kaldırın.

- Bu ad alanında bulunan herhangi bir türü için tam adı belirtin.

## <a name="example"></a>Örnek

Adlı bir değişkene belirsiz bir başvuru yapıldığı için aşağıdaki örnek, C2872 oluşturur `i`; iki aboneliklerinin kapsamda aynı ada sahip değişkenler:

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
