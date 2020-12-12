---
description: 'Daha fazla bilgi edinin: Işlev şablonu çağrılarının aşırı yükleme çözümü'
title: İşlev Şablonu Çağrılarının Aşırı Yük Çözümü
ms.date: 11/04/2016
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
ms.openlocfilehash: 6174ac7fe4354f655a5c6a94c7493c6cc1a423cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146022"
---
# <a name="overload-resolution-of-function-template-calls"></a>İşlev Şablonu Çağrılarının Aşırı Yük Çözümü

Bir işlev şablonu aynı adda şablon olmayan işlevleri aşırı yükleyebilir. Bu senaryoda, işlev çağrıları öncelikle, benzersiz bir özelleşmeye sahip işlev şablonunu örneklemek için şablon bağımsız değişken kesintisi kullanılarak çözümlenir. Şablon bağımsız değişkeni kesintisi başarısız olursa, diğer işlev aşırı yüklemeleri çağrıyı çözümlemek için kabul edilir. Aday kümesi olarak da bilinen bu diğer aşırı yüklemeler, şablon olmayan işlevleri ve diğer örneklenmiş işlev şablonlarını içerir. Şablon bağımsız değişkeni kesintisi başarılı olursa oluşturulan işlev, en iyi eşleşmeyi tespit etmek için diğer işlevlerle karşılaştırılır ve aşırı yükleme çözümlemesi kurallarını takip edin. Daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md).

## <a name="example-choose-a-nontemplate-function"></a>Örnek: şablon olmayan bir işlev seçin

Şablon olmayan bir işlev, şablon işleviyle eşit derecede iyi bir eşleşmedir, aşağıdaki örnekteki çağrıda olduğu gibi şablon olmayan işlev seçilir (şablon bağımsız değişkenleri açıkça belirtilmediği sürece) `f(1, 1)` .

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

## <a name="example-exact-match-template-function-preferred"></a>Örnek: tam eşleştirme şablonu işlevi tercih edilir

Sonraki örnekte, şablon olmayan işlev bir dönüştürme gerektiriyorsa, tam olarak eşleşen şablon işlevinin tercih edildiği gösterilmektedir.

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

[Ad çözümlemesi](../cpp/templates-and-name-resolution.md)<br/>
[typename](../cpp/typename.md)
