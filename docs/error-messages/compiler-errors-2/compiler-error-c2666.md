---
title: Derleyici Hatası C2666
ms.date: 11/04/2016
f1_keywords:
- C2666
helpviewer_keywords:
- C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
ms.openlocfilehash: 4a1d46f3b000b5054564b05ca2c3c94a9e7b6398
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386882"
---
# <a name="compiler-error-c2666"></a>Derleyici Hatası C2666

'identifier': sayı aşırı benzer dönüşümleri var

Bir aşırı yüklenmiş işlev ya da operatör belirsiz.   Biçimsel parametre listeleri derleyici belirsizliği çözmek çok benzer olabilir.  Bu hatayı gidermek için açıkça bir veya daha fazla gerçek parametre dönüştürün.

Aşağıdaki örnek, C2666 oluşturur:

```
// C2666.cpp
struct complex {
   complex(double);
};

void h(int,complex);
void h(double, double);

int main() {
   h(3,4);   // C2666
}
```

Bu hata, Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir:

- ikili işleçler ve işaretçi türleri için kullanıcı tanımlı dönüşümler

- Nitelik dönüştürme kimlik dönüştürme ile aynı değil

İkili işleçler için \<, >, \<= ve > =, bir geçirilen parametre örtük olarak dönüştürüldü işlenen türü için parametre türü işlenenin türe dönüştürmek için bir kullanıcı tanımlı dönüştürme işleci tanımlıyorsa. Var. Şimdi belirsizlik için olası

Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli kod için işlev sözdizimi kullanılarak açıkça sınıfı işleci çağırın.

## <a name="example"></a>Örnek

```
// C2666b.cpp
#include <string.h>
#include <stdio.h>

struct T
{
    T( const T& copy )
    {
        m_str = copy.m_str;
    }

    T( const char* str )
    {
        int iSize = (strlen( str )+ 1);
        m_str = new char[ iSize ];
        if (m_str)
            strcpy_s( m_str, iSize, str );
    }

    bool operator<( const T& RHS )
    {
        return m_str < RHS.m_str;
    }

    operator char*() const
    {
        return m_str;
    }

    char* m_str;
};

int main()
{
    T str1( "ABCD" );
    const char* str2 = "DEFG";

    // Error - Ambiguous call to operator<()
    // Trying to convert str1 to char* and then call
    // operator<( const char*, const char* )?
    //  OR
    // trying to convert str2 to T and then call
    // T::operator<( const T& )?

    if( str1 < str2 )   // C2666

    if ( str1.operator < ( str2 ) )   // Treat str2 as type T
        printf_s("str1.operator < ( str2 )\n");

    if ( str1.operator char*() < str2 )   // Treat str1 as type char*
        printf_s("str1.operator char*() < str2\n");
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C2666 oluşturur

```
// C2666c.cpp
// compile with: /c

enum E
{
    E_A,   E_B
};

class A
{
    int h(const E e) const {return 0; }
    int h(const int i) { return 1; }
    // Uncomment the following line to resolve.
    // int h(const E e) { return 0; }

    void Test()
    {
        h(E_A);   // C2666
        h((const int) E_A);
        h((int) E_A);
    }
};
```