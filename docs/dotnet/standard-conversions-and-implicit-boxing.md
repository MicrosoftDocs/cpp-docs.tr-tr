---
description: Daha fazla bilgi için bkz. Standart dönüştürmeler ve Örtük kutulama
title: Standart Dönüştürmeler ve Örtük Kutulama
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, implicit
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
ms.openlocfilehash: 9775effdae92ac9689bc7c08f2ba7887e6b54dbc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335353"
---
# <a name="standard-conversions-and-implicit-boxing"></a>Standart Dönüştürmeler ve Örtük Kutulama

Standart dönüştürme, paketleme gerektiren bir dönüştürme üzerinde derleyici tarafından seçilir.

## <a name="example"></a>Örnek

```cpp
// clr_implicit_boxing_Std_conversion.cpp
// compile with: /clr
int f3(int ^ i) {   // requires boxing
   return 1;
}

int f3(char c) {   // no boxing required, standard conversion
   return 2;
}

int main() {
   int i = 5;
   System::Console::WriteLine(f3(i));
}
```

```Output
2
```

## <a name="see-also"></a>Ayrıca bkz.

[Kutulama](../extensions/boxing-cpp-component-extensions.md)
