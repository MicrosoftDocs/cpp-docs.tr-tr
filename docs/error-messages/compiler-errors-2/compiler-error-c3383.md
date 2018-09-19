---
title: Derleyici Hatası C3383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3383
dev_langs:
- C++
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e35aa05dd037c7d8a5dfd9f7e8328f3644b901e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109398"
---
# <a name="compiler-error-c3383"></a>Derleyici Hatası C3383

/ CLR: safe ile 'operator new' desteklenmiyor

Çıktı dosyası bir **/CLR: safe** derleme doğrulanabilir şekilde güvenli yazın olan bir dosya olduğu ve işaretçiler desteklenmez.

Daha fazla bilgi için bkz:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3383 oluşturur.

```
// C3383.cpp
// compile with: /clr:safe
int main() {
   char* pCharArray = new char[256];  // C3383
}
```