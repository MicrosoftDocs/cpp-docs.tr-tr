---
title: Variadic makrolar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0e3832ab334d31b50edbe0cc1fd5dccbffb61bf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="variadic-macros"></a>Variadic Makrolar
Değişen sayıda bağımsız değişken içeren makrolar, değişken sayıda bağımsız değişken içeren işlev benzeri makrolardır.  
  
## <a name="remarks"></a>Açıklamalar  
 Variadic makrolar kullanmak için üç nokta son biçimsel bağımsız değişken olarak bir makro tanımı ve değiştirme tanımlayıcısı belirtilebilir `__VA_ARGS__` tanımında ek bağımsız değişkenleri eklemek için kullanılabilir.  `__VA_ARGS__` Tüm bunlar arasında virgül dahil olmak üzere üç nokta eşleşen bağımsız değişkenleri ile değiştirilir.  
  
 C Standardı, makronun arkasından virgül gelen bir ifadeye çözümlenmemesini sağlamak için üç noktaya en az bir bağımsız değişkenin geçirilmesi gerektiğini belirtir.  Üç noktaya hiçbir bağımsız değişken geçirilmezse, Visual C++ uygulaması sondaki virgülü gizler.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)