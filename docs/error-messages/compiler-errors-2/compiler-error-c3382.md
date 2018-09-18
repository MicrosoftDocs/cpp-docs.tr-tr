---
title: Derleyici Hatası C3382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da27531b95950a12cb9aa95e8e89da94c556d2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035972"
---
# <a name="compiler-error-c3382"></a>Derleyici Hatası C3382

/ CLR: safe ile 'sizeof' desteklenmiyor

Çıktı dosyası bir **/CLR: safe** derleme doğrulanabilir şekilde güvenli yazın olan bir dosya olduğu ve sizeof size_t boyutu işletim sistemine göre farklılık gösterir, sizeof işleci dönüş değeri olduğu için desteklenmiyor.

Daha fazla bilgi için bkz:

- [sizeof İşleci](../../cpp/sizeof-operator.md)

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3382 oluşturur.

```
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```