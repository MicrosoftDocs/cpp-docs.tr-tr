---
title: Derleyici Uyarısı (düzey 1) C4067
ms.date: 11/04/2016
f1_keywords:
- C4067
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
ms.openlocfilehash: 8bdd16f5c3182e4217e195475bdb4a9a0f60fa6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164124"
---
# <a name="compiler-warning-level-1-c4067"></a>Derleyici Uyarısı (düzey 1) C4067

> Önişlemci yönergesinin izleyen beklenmeyen belirteçler-bir yeni satır bekleniyordu

## <a name="remarks"></a>Açıklamalar

Derleyici, Önişlemci yönergesinin ardından ek karakterler buldu ve yoksaydı. Bu, beklenmeyen karakterlerden kaynaklanabilir, ancak yaygın bir neden, yönergesinden sonra bir çok noktalı virgüldür. Açıklamalar bu uyarıya neden olmaz. **/Za** derleyici seçeneği, varsayılan ayardan daha fazla Önişlemci yönergesi için bu uyarıya izin vermez.

## <a name="example"></a>Örnek

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

Bu uyarıyı çözmek için, boş karakterleri silin veya bir açıklama bloğuna taşıyın. **/Za** derleyici seçeneği kaldırılarak bazı C4067 uyarıları devre dışı bırakılabilir.

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```
