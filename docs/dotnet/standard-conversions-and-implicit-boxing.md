---
title: Standart Dönüştürmeler ve Örtük Kutulama
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, implicit
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
ms.openlocfilehash: 35d5cbbec8d1364fbc954457b42470f82a01ed35
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744430"
---
# <a name="standard-conversions-and-implicit-boxing"></a>Standart Dönüştürmeler ve Örtük Kutulama

Standart bir dönüşüm kutulama gerektiren bir dönüştürme derleyici tarafından seçilir.

## <a name="example"></a>Örnek

```
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

[Kutulama](../windows/boxing-cpp-component-extensions.md)
