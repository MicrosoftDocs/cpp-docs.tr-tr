---
title: Derleyici Uyarısı (düzey 1) C4067
ms.date: 11/04/2016
f1_keywords:
- C4067
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
ms.openlocfilehash: 012866e328433ec9511782c26a39265481ff4940
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541199"
---
# <a name="compiler-warning-level-1-c4067"></a>Derleyici Uyarısı (düzey 1) C4067

> Beklenmeyen belirteçler aşağıdaki önişlemci yönergesi - satır sonu bekleniyordu

## <a name="remarks"></a>Açıklamalar

Derleyici bulundu ve ön işlemci yönergesinden sonra ek karakterler yoksayılır. Yaygın bir nedeni yönergesinden sonra noktalı virgüldür olsa bu beklenmeyen bir karakterleriyle kaynaklanabilir. Açıklamalar bu uyarıyı neden olmaz. **/Za** derleyici seçeneği, bu uyarı için varsayılan ayar'den daha çok önişlemci yönergeleri sağlar.

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

Bu uyarıyı çözmek için geçirilmeyen karakterleri silin veya açıklama bloğu içine taşıyabilirsiniz. Belirli C4067 uyarıları kaldırarak devre dışı bırakılabilir **/Za** derleyici seçeneği.

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