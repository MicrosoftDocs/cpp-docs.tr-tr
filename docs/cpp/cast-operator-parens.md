---
title: 'Atama İşleci: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- cast operators [C++]
- () cast operator
ms.assetid: 4c99eb92-1b19-4a5d-9840-5d8c29b8453e
ms.openlocfilehash: 54345637665736085d812b88f5822a94014eaa74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516967"
---
# <a name="cast-operator-"></a>Atama İşleci: ()

Bir tür ataması, belirli bir durumda bir nesne türünün açık dönüştürmesine ilişkin bir yöntem sağlar.

## <a name="syntax"></a>Sözdizimi

```
unary-expression ( type-name ) cast-expression
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir tekli ifade atama ifadesi olarak kabul edilir.

Derleyici işler *atama ifadesini* türü olarak *tür adı* bir tür ataması yapıldıktan sonra. Atamalar, herhangi bir skaler türdeki nesneleri başka bir skaler türe veya skaler türden dönüştürmek için kullanılabilir. Açık tür atamaları, örtük dönüştürmelerin etkilerini belirleyen aynı kuralları tarafından kısıtlanmıştır. Gerçek boyutlar veya belirli türlerin gösterimi, atamalara ilişkin ek kısıtlamalara neden olabilir.

## <a name="example"></a>Örnek

```cpp
// expre_CastOperator.cpp
// compile with: /EHsc
// Demonstrate cast operator
#include <iostream>

using namespace std;

int main()
{
    double x = 3.1;
    int i;
    cout << "x = " << x << endl;
    i = (int)x;   // assign i the integer part of x
    cout << "i = " << i << endl;
}
```

## <a name="example"></a>Örnek

```cpp
// expre_CastOperator2.cpp
// The following sample shows how to define and use a cast operator.
#include <string.h>
#include <stdio.h>

class CountedAnsiString
{
public:
    // Assume source is not null terminated
    CountedAnsiString(const char *pStr, size_t nSize) :
                      m_nSize(nSize)
    {
        m_pStr = new char[sizeOfBuffer];

        strncpy_s(m_pStr, sizeOfBuffer, pStr, m_nSize);
        memset(&m_pStr[m_nSize], '!', 9); // for demonstration purposes.
    }

    // Various string-like methods...

    const char *GetRawBytes() const
    {
        return(m_pStr);
    }

    //
    // operator to cast to a const char *
    //
    operator const char *()
    {
        m_pStr[m_nSize] = '\0';
        return(m_pStr);
    }

    enum
    {
        sizeOfBuffer = 20
    } size;

private:
    char *m_pStr;
    const size_t m_nSize;
};

int main()
{
    const char *kStr = "Excitinggg";
    CountedAnsiString myStr(kStr, 8);

    const char *pRaw = myStr.GetRawBytes();
    printf_s("RawBytes truncated to 10 chars:   %.10s\n", pRaw);

    const char *pCast = myStr; // or (const char *)myStr;
    printf_s("Casted Bytes:   %s\n", pCast);

    puts("Note that the cast changed the raw internal string");
    printf_s("Raw Bytes after cast:   %s\n", pRaw);
}
```

```Output
RawBytes truncated to 10 chars:   Exciting!!
Casted Bytes:   Exciting
Note that the cast changed the raw internal string
Raw Bytes after cast:   Exciting
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Açık Tür Dönüştürme İşleci: ()](../cpp/explicit-type-conversion-operator-parens.md)<br/>
[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Atama İşleçleri](../c-language/cast-operators.md)