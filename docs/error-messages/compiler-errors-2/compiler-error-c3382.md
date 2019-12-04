---
title: Derleyici hatası C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 419577ddd5b5d7d2d21a91f500070cb190c72117
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760471"
---
# <a name="compiler-error-c3382"></a>Derleyici hatası C3382

/clr: Safe ile ' sizeof ' desteklenmiyor

**/Clr: Safe** derlemesinin çıkış dosyası, doğruıolarak tür kullanımı güvenli olan bir dosyadır ve sizeof işlecinin dönüş değeri size_t olduğundan sizeof, boyutu işletim sistemine bağlı olarak değişir çünkü sizeof desteklenmez.

Daha fazla bilgi için bkz.,

- [sizeof İşleci](../../cpp/sizeof-operator.md)

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

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
