---
title: Derleyici Uyarısı (düzey 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 76aab2160bd5f7918771dcf63b7297a869da751e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187345"
---
# <a name="compiler-warning-level-1-c4005"></a>Derleyici Uyarısı (düzey 1) C4005

'identifier': makro yeniden tanımlama

Makro tanımlayıcı, iki kez tanımlanmış. Derleyici ikinci Makro tanımında kullanır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Makro, komut satırında ve kodla tanımlarken bir `#define` yönergesi.

1. Makroları dahil etme dosyaları içeri aktarıldı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Tanımlardan birini kaldırın.

1. Kullanım bir [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) ikinci tanımından önce yönergesi.

Aşağıdaki örnek, C4005 oluşturur:

```
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