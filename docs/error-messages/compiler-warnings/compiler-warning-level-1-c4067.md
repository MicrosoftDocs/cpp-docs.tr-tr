---
title: Derleyici Uyarısı (düzey 1) C4067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee6b48327e8754f9388e0df8f43009a5be70c97
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4067"></a>Derleyici Uyarısı (düzey 1) C4067

> Beklenmeyen belirteçleri aşağıdaki önişlemci yönergesi - beklenen bir satır başı karakteri

## <a name="remarks"></a>Açıklamalar

Derleyici bulundu ve önişlemci yönergesi sonraki fazladan karakterler yoksayıldı. Sık karşılaşılan bir nedeni parazit noktalı sonra yönergesi olmasına rağmen bu beklenmeyen bir karakterleriyle neden olabilir. Bu uyarı açıklamaları neden olmaz. **/Za** derleyici seçeneği bu uyarı için varsayılan ayar'den daha fazla önişlemci yönergeleri sağlar.

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

Bu uyarıyı çözmek için parazit karakterleri silin veya bir açıklama bloğuna taşıyabilirsiniz. Belirli C4067 uyarıları kaldırarak devre dışı bırakılabilir **/Za** derleyici seçeneği.

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