---
title: Aşırı yükleme çözümlemesi işlev şablonu çağrılarının | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62041f78af18d6ac2f521fea763a11bb2859fbf5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401931"
---
# <a name="overload-resolution-of-function-template-calls"></a>İşlev Şablonu Çağrılarının Aşırı Yük Çözümü
Şablon Olmayandan işlevleri aynı ada sahip bir işlev şablonu aşırı yüklenebilir. Bu senaryoda, işlev çağrıları ilk tarafından çözümlenir benzersiz bir özelleştirmesi ile işlev şablonu oluşturmak için şablon bağımsız değişkeni kesintisi kullanarak. Şablon bağımsız değişkeni kesintisi başarısız olursa, diğer bir işlev aşırı yüklemelerinin çağrıyı çözümlemek için olarak kabul edilir. Aday kümesi olarak da bilinen bu diğer aşırı yüklemeler, şablon Olmayandan işlevleri ve diğer örneklenmiş işlev şablonları içerir. Şablon bağımsız değişkeni kesintisi başarılı olursa, oluşturulan işlev aşırı yükleme çözümlemesi için kuralları aşağıdaki en iyi eşleşmeyi belirlemek için diğer işlevler ile karşılaştırılır. Daha fazla bilgi için [işlev aşırı yüklemesi](function-overloading.md).  
  
## <a name="example"></a>Örnek

 Şablon Olmayandan işlevi bir şablon işlevine eşit derecede iyi bir eşleşme varsa (şablon bağımsız değişkenleri açıkça belirtilen sürece) sınıflarındaki işlevi, bir çağrıda olarak seçilen `f(1, 1)` aşağıdaki örnekte.  
  
```cpp
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
```Output  
f(int, int)  
void f(T1, T2)  
void f(T1, T2)  
```  
  
## <a name="example"></a>Örnek

 Sonraki örnekte, şablon Olmayandan işlevi bir dönüştürme gerektiriyorsa, tam olarak eşleşen şablon işlevi tercih edilir gösterilmektedir.  
  
```cpp
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
```Output  
void f(T1, T2)  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Ad çözümlemesi](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   