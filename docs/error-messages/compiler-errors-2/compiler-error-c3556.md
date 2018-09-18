---
title: Derleyici Hatası C3556 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3556
dev_langs:
- C++
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 043c7e6a20cc914c36ecae4c54d772a3f6145a73
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061129"
---
# <a name="compiler-error-c3556"></a>Derleyici Hatası C3556

> '*ifade*': 'decltype' için geçersiz bağımsız değişken

Derleyici bağımsız değişkeni için olan ifade türü çıkarılamıyor `decltype(` *ifade* `)` tür tanımlayıcısı.

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde, derleyicinin türü çıkarılamıyor `myFunction` bağımsız değişken olduğundan `myFunction` aşırı yüklendi. Bu sorunu gidermek için kullanabileceğinizi `static_cast` işlevi belirtmek için bir işaretçi belirli bir örneğini oluşturmak için aşırı `decltype` ifade.

```cpp
// C3556.cpp
// compile with: cl /W4 /EHsc C3556.cpp
#include <iostream>

void myFunction(int);
void myFunction(float, float);

void callsMyFunction(decltype(myFunction) fn); // C3556
// One way to fix is to comment out the line above, and
// use static_cast to create specialized function pointer
// instances:
auto myFunctionInt = static_cast<void(*)(int)>(myFunction);
auto myFunctionFloatFloat = static_cast<void(*)(float,float)>(myFunction);
void callsMyFunction(decltype(myFunctionInt) fn, int n);
void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g);

void myFunction(int i) {
    std::cout << "called myFunction(" << i << ")" << std::endl;
}

void myFunction(float f, float g) {
    std::cout << "called myFunction(" << f << ", " << g << ")" << std::endl;
}

void callsMyFunction(decltype(myFunctionInt) fn, int n) {
    fn(n);
}

void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g) {
    fn(f, g);
}

int main() {
    callsMyFunction(myFunction, 42);
    callsMyFunction(myFunction, 0.1f, 2.3f);
}
```