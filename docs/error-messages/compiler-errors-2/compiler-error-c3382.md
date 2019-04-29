---
title: Derleyici Hatası C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: c262ea963ae739fbb76211aae2622e98d5a9b6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328789"
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