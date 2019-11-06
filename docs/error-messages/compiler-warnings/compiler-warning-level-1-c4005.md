---
title: Derleyici Uyarısı (düzey 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 71b23ec719198d15a99b4fcfd50db8b151e03226
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627365"
---
# <a name="compiler-warning-level-1-c4005"></a>Derleyici Uyarısı (düzey 1) C4005

' tanımlayıcı ': makro yeniden tanımı

Makro tanımlayıcısı iki kez tanımlanır. Derleyici ikinci makro tanımını kullanır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Komut satırında ve bir `#define` yönergesi ile kodda bir makro tanımlama.

1. İçerme dosyalarından içeri aktarılan makrolar.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Tanımlardan birini kaldırın.

1. İkinci tanımdan önce bir [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) yönergesi kullanın.

Aşağıdaki örnek C4005 oluşturur:

```cpp
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```