---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4067'
title: Derleyici Uyarısı (düzey 1) C4067
ms.date: 11/04/2016
f1_keywords:
- C4067
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
ms.openlocfilehash: b11167ba5648e71be16197ecfb418d92cb5d879a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267670"
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
