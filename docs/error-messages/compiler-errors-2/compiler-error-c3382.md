---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3382'
title: Derleyici hatası C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 582a807ac43d6110fb0f19aef5806e4118516db2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285662"
---
# <a name="compiler-error-c3382"></a>Derleyici hatası C3382

/clr: Safe ile ' sizeof ' desteklenmiyor

**/Clr: Safe** derlemesinin çıkış dosyası, doğruıolarak tür kullanımı güvenli olan bir dosyadır ve sizeof işlecinin dönüş değeri size_t olduğundan sizeof, boyutu işletim sistemine bağlı olarak değişir çünkü sizeof desteklenmez.

Daha fazla bilgi için bkz.,

- [sizeof Işleci](../../cpp/sizeof-operator.md)

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3382 oluşturur.

```cpp
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```
