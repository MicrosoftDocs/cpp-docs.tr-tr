---
title: Derleyici Hatası C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: 38aea188eeac90cd23d9203a53b4e630be2f115b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367349"
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