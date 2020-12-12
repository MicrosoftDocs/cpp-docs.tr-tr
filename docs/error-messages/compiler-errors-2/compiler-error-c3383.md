---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3383'
title: Derleyici hatası C3383
ms.date: 11/04/2016
f1_keywords:
- C3383
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
ms.openlocfilehash: fb5baf99c6738db1296cf4fb0a509c63d570ad78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285597"
---
# <a name="compiler-error-c3383"></a>Derleyici hatası C3383

/clr: Safe ile ' operator New ' desteklenmez

**/Clr: Safe** derlemesinin çıkış dosyası, doğruıolarak tür kullanımı güvenli olan bir dosyadır ve işaretçiler desteklenmez.

Daha fazla bilgi için bkz.,

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

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
