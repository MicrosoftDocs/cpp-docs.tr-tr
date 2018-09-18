---
title: Derleyici Uyarısı (düzey 1) C4005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8be172086e316c991f461b3ac42f58739801cfa7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022974"
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