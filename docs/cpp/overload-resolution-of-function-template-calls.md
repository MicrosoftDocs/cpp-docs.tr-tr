---
title: "İşlev şablonu çağrılarının aşırı yük çözümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 64bc9371fcddad5f76f1474832a8d69188b60583
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overload-resolution-of-function-template-calls"></a>İşlev Şablonu Çağrılarının Aşırı Yük Çözümü
İşlev şablonu aynı ada sahip şablon Olmayandan işlevleri aşırı yüklenebilir. Bu senaryoda, ilk işlev çağrılarını çözümlenir benzersiz uzmanlık işlevi şablonla örneği oluşturmak için şablon bağımsız değişken kesintisi kullanma. Şablon bağımsız değişken kesintisi başarısız olursa, diğer bir işlev aşırı yüklemelerinin çağrı çözümlemek için olarak kabul edilir. Aday kümesi olarak da bilinen bu diğer aşırı yüklemeler, şablon Olmayandan işlevler ve diğer başlatılan işlev şablonları içerir. Şablon bağımsız değişken kesintisi başarılı olursa, oluşturulan işlev kuralları aşırı yükleme çözümü için aşağıdaki en iyi eşleşmeyi belirlemek için diğer işlevleri ile karşılaştırılır. Daha fazla bilgi için bkz: [işlev aşırı yüklemesi](function-overloading.md).  
  
## <a name="example"></a>Örnek

 Şablon Olmayandan işlevi bir şablon işlevi için eşit oranda iyi bir eşleşme varsa (şablon değişkenleri açıkça belirtildi sürece) şablon Olmayandan işlevi, çağrı olarak seçilir `f(1, 1)` aşağıdaki örnekte.  
  
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

 Şablon Olmayandan işlev dönüştürme gerektiriyorsa, tam olarak eşleşen şablon işlevi tercih edilir sonraki örnek gösterilmektedir.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.

 [Ad çözümlemesi](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   
 
