---
title: Derleyici hatası C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: ceae17689cbcb9585fb3722580042187ff64a6ee
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755635"
---
# <a name="compiler-error-c3383"></a>Derleyici hatası C3383

/clr: Safe ile ' operator New ' desteklenmez

**/Clr: Safe** derlemesinin çıkış dosyası, doğruıolarak tür kullanımı güvenli olan bir dosyadır ve işaretçiler desteklenmez.

Daha fazla bilgi için bkz.,

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3383 oluşturur.

```cpp
// C3383.cpp
// compile with: /clr:safe
int main() {
   char* pCharArray = new char[256];  // C3383
}
```
