---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4005'
title: Derleyici Uyarısı (düzey 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: a8de4974d87eb5d8396085bb79dfbfe14a177602
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325993"
---
# <a name="compiler-warning-level-1-c4005"></a>Derleyici Uyarısı (düzey 1) C4005

' tanımlayıcı ': makro yeniden tanımı

Makro tanımlayıcısı iki kez tanımlanır. Derleyici ikinci makro tanımını kullanır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Komut satırında ve bir yönergeyle kodda bir makro tanımlama `#define` .

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
