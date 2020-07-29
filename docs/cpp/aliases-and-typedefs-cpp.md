---
title: Diğer adlar ve tür tanımları (C++)
ms.date: 11/04/2016
f1_keywords:
- typedef_cpp
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
ms.openlocfilehash: 6054b7119614d9325bd099dd39b8aa1365d97ed7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227679"
---
# <a name="aliases-and-typedefs-c"></a>Diğer adlar ve tür tanımları (C++)

Daha önce tanımlanan bir tür için eş anlamlı olarak kullanılacak bir ad bildirmek üzere bir *diğer ad bildirimi* kullanabilirsiniz. (Bu mekanizma bir *tür diğer adı*olarak da bilinir). Bu mekanizmayı Ayrıca, özel ayrıcılar için özellikle yararlı olabilecek bir *diğer ad şablonu*oluşturmak için de kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
using identifier = type;
```

## <a name="remarks"></a>Açıklamalar

*Tanımlayıcısını*<br/>
Diğer adın adı.

*türüyle*<br/>
İçin bir diğer ad oluşturduğunuz tür tanımlayıcısı.

Diğer ad yeni bir tür sunmaz ve var olan bir tür adının anlamını değiştiremezler.

Diğer adın en basit biçimi, **`typedef`** c++ 03 mekanizmasına eşdeğerdir:

```cpp
// C++11
using counter = long;

// C++03 equivalent:
// typedef long counter;
```

Her ikisi de "Counter" türünde değişkenlerin oluşturulmasını etkinleştirir. Diğer bir deyişle, bunun gibi bir tür diğer adı olacaktır `std::ios_base::fmtflags` :

```cpp
// C++11
using fmtfl = std::ios_base::fmtflags;

// C++03 equivalent:
// typedef std::ios_base::fmtflags fmtfl;

fmtfl fl_orig = std::cout.flags();
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;
// ...
std::cout.flags(fl_hex);
```

Diğer adlar işlev işaretçileriyle de çalışır, ancak eşdeğer typedef öğesinden çok daha okunabilir:

```cpp
// C++11
using func = void(*)(int);

// C++03 equivalent:
// typedef void (*func)(int);

// func can be assigned to a function pointer value
void actual_function(int arg) { /* some code */ }
func fptr = &actual_function;
```

Mekanizmanın sınırlaması, **`typedef`** şablonlarla çalışmamasıdır. Ancak, C++ 11 ' de tür diğer adı sözdizimi diğer ad şablonlarının oluşturulmasını mümkün değildir:

```cpp
template<typename T> using ptr = T*;

// the name 'ptr<T>' is now an alias for pointer to T
ptr<int> ptr_int;
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir diğer ad şablonunun özel bir ayırıcıyla nasıl kullanıldığını gösterir — Bu örnekte, bir tamsayı vektör türüdür. Her türlü türü, **`int`** ana işlevsel kodunuzda karmaşık parametre listelerini gizlemek için uygun bir diğer ad oluşturmak üzere kullanabilirsiniz. Kodunuzun tamamında özel ayırıcıyı kullanarak okunabilirliği iyileştirebilir ve yazım hataları nedeniyle oluşan hataları tanıtma riskini azaltabilirsiniz.

```cpp
#include <stdlib.h>
#include <new>

template <typename T> struct MyAlloc {
    typedef T value_type;

    MyAlloc() { }
    template <typename U> MyAlloc(const MyAlloc<U>&) { }

    bool operator==(const MyAlloc&) const { return true; }
    bool operator!=(const MyAlloc&) const { return false; }

    T * allocate(const size_t n) const {
        if (n == 0) {
            return nullptr;
        }

        if (n > static_cast<size_t>(-1) / sizeof(T)) {
            throw std::bad_array_new_length();
        }

        void * const pv = malloc(n * sizeof(T));

        if (!pv) {
            throw std::bad_alloc();
        }

        return static_cast<T *>(pv);
    }

    void deallocate(T * const p, size_t) const {
        free(p);
    }
};

#include <vector>
using MyIntVector = std::vector<int, MyAlloc<int>>;

#include <iostream>

int main ()
{
    MyIntVector foov = { 1701, 1764, 1664 };

    for (auto a: foov) std::cout << a << " ";
    std::cout << "\n";

    return 0;
}
```

```Output
1701 1764 1664
```

## <a name="typedefs"></a>Tür tanımları

Bir **`typedef`** bildirim, kapsamı içinde, bildirimin *tür bildirimi* bölümü tarafından verilen tür için bir eş anlamlı haline gelir.

Zaten dil veya bildirdiğiniz türler için tanımlanmış olan türler için daha kısa veya daha anlamlı adlar oluşturmak üzere typedef bildirimlerini kullanabilirsiniz. Typedef adları, değişebilir uygulama ayrıntılarını kapsüllemek için izin verir.

,,, **`class`** **`struct`** **`union`** Ve **`enum`** bildirimlerinin aksine, **`typedef`** Bildirimler yeni türler sunmaz; mevcut türler için yeni adlar sağlar.

Kullanılarak belirtilen adlar **`typedef`** , diğer tanımlayıcılarla aynı ad alanını kaplar (ifade etiketleri hariç). Bu nedenle, sınıf türü bildirim dışında daha önce bildirilen bir adla aynı tanımlayıcıyı kullanamazlar. Aşağıdaki örneği inceleyin:

```cpp
// typedef_names1.cpp
// C2377 expected
typedef unsigned long UL;   // Declare a typedef name, UL.
int UL;                     // C2377: redefined.
```

Diğer Tanımlayıcılarla ilgili ad gizleme kuralları kullanılarak belirtilen adların görünürlüğünü de yönetir **`typedef`** . Bu nedenle, aşağıdaki örnek C++'da geçerlidir:

```cpp
// typedef_names2.cpp
typedef unsigned long UL;   // Declare a typedef name, UL
int main()
{
   unsigned int UL;   // Redeclaration hides typedef name
}

// typedef UL back in scope
```

```cpp
// typedef_specifier1.cpp
typedef char FlagType;

int main()
{
}

void myproc( int )
{
    int FlagType;
}
```

Bir typedef ile aynı ad ile bir yerel kapsam tanımlayıcısı bildirirken veya aynı kapsamda veya bir iç kapsamda bir yapının veya birleşimin üyesini bildirirken tür belirleyicisi belirtilmelidir. Örnek:

```cpp
typedef char FlagType;
const FlagType x;
```

`FlagType`Bir tanımlayıcı, yapı üyesi veya birleşim üyesi için adı yeniden kullanmak için, tür sağlanmalıdır:

```cpp
const int FlagType;  // Type specifier required
```

Söylemek yeterli değildir

```cpp
const FlagType;      // Incomplete specification
```

Çünkü, `FlagType` yeniden bildirilebilecek bir tanımlayıcı değil türün bir parçası olmak için alınır. Bu bildirim, şunun gibi geçersiz bir bildirim olacak şekilde alınır

```cpp
int;  // Illegal declaration
```

İşaretçi, işlev ve dizi türleri dahil olmak üzere typedef ile herhangi bir tür bildirebilirsiniz. Tanımın bildirimle aynı görünürlüğe sahip olduğu sürece yapıyı veya birleşim türünü tanımladıktan önce bir yapı veya birleşim türü işaretçisi için bir typedef adı bildirebilirsiniz.

### <a name="examples"></a>Örnekler

Bildirimlerin bir kullanımı **`typedef`** , bildirimlerin daha Tekdüzen ve kompakt olmasını sağlar. Örnek:

```cpp
typedef char CHAR;          // Character type.
typedef CHAR * PSTR;        // Pointer to a string (char *).
PSTR strchr( PSTR source, CHAR target );
typedef unsigned long ulong;
ulong ul;     // Equivalent to "unsigned long ul;"
```

**`typedef`** Aynı bildirimde temel ve türetilmiş türleri belirtmek için kullanmak üzere, bildirimcilerin virgülle ayırabilirsiniz. Örnek:

```cpp
typedef char CHAR, *PSTR;
```

Aşağıdaki örnek, `DRAWF` değer döndürülmeden ve iki int bağımsız değişken alan bir işlev için tür sağlar:

```cpp
typedef void DRAWF( int, int );
```

Yukarıdaki **`typedef`** deyimden sonra bildirim

```cpp
DRAWF box;
```

Bildirime eşdeğerdir

```cpp
void box( int, int );
```

**`typedef`**, **`struct`** Kullanıcı tanımlı türleri bildirmek ve adlandırmak için genellikle ile birleştirilir:

```cpp
// typedef_specifier2.cpp
#include <stdio.h>

typedef struct mystructtag
{
    int   i;
    double f;
} mystruct;

int main()
{
    mystruct ms;
    ms.i = 10;
    ms.f = 0.99;
    printf_s("%d   %f\n", ms.i, ms.f);
}
```

```Output
10   0.990000
```

### <a name="re-declaration-of-typedefs"></a>Tür tanımları öğesinin yeniden bildirimi

Bildirim, aynı **`typedef`** türe başvurmak için aynı adı yeniden bildirmek üzere kullanılabilir. Örnek:

```cpp
// FILE1.H
typedef char CHAR;

// FILE2.H
typedef char CHAR;

// PROG.CPP
#include "file1.h"
#include "file2.h"   // OK
```

Program program programı *. CPP* , her ikisi de ad için bildirimler içeren iki üst bilgi dosyası içerir **`typedef`** `CHAR` . Her iki bildirim de aynı türe başvurduğu sürece, böyle bir yeniden bildirim kabul edilebilir.

**`typedef`**, Daha önce farklı bir tür olarak belirtilen adı yeniden tanımlanamaz. Bu nedenle, *dosya2. H* şunu içerir

```cpp
// FILE2.H
typedef int CHAR;     // Error
```

içeriyorsa, farklı bir türe başvurmak için `CHAR` adını yeniden bildirme girişimi nedeniyle bir hata verir. Bu, aşağıdakiler gibi yapılarla genişletilir:

```cpp
typedef char CHAR;
typedef CHAR CHAR;      // OK: redeclared as same type

typedef union REGS      // OK: name REGS redeclared
{                       //  by typedef name with the
    struct wordregs x;  //  same meaning.
    struct byteregs h;
} REGS;
```

### <a name="typedefs-in-c-vs-c"></a>C++ ve C 'de tür tanımları

, **`typedef`** Bildirimlerde adlandırılmamış yapıları BILDIRIRKEN ANSI C uygulaması nedeniyle, sınıf türleri ile belirleyici kullanılması büyük ölçüde desteklenir **`typedef`** . Örneğin, birçok C programcısı şunları kullanır:

```cpp
// typedef_with_class_types1.cpp
// compile with: /c
typedef struct {   // Declare an unnamed structure and give it the
                   // typedef name POINT.
   unsigned x;
   unsigned y;
} POINT;
```

Böyle bir bildirimin avantajı, şunun gibi bildirimlerin kullanılmasına izin verebilir:

```cpp
POINT ptOrigin;
```

Onun yerine:

```cpp
struct point_t ptOrigin;
```

C++ ' da, **`typedef`** adlar ve gerçek türler ( **`class`** ,, **`struct`** **`union`** ve anahtar sözcüklerle belirtilen) arasındaki fark **`enum`** daha farklıdır. Bir deyimde bir adsız yapısını bildirmenin c uygulaması **`typedef`** hala işe yaramazsa, c içinde olduğu gibi notational avantajlarına sahip değildir.

```cpp
// typedef_with_class_types2.cpp
// compile with: /c /W1
typedef struct {
   int POINT();
   unsigned x;
   unsigned y;
} POINT;
```

Önceki örnek `POINT` adlandırılmamış sınıf söz dizimi kullanılarak adlı bir sınıf bildirir **`typedef`** . `POINT`sınıf adı olarak değerlendirilir; Ancak, aşağıdaki kısıtlamalar bu şekilde tanıtılan adlara uygulanır:

- Ad (eş anlamlı) bir **`class`** , veya öneki öğesinden sonra bulunamaz **`struct`** **`union`** .

- Ad, sınıf bildiriminde Oluşturucu veya yıkıcı adları olarak kullanılamaz.

Özet olarak, bu sözdizimi devralma, oluşturma veya yok etme için herhangi bir mekanizma sağlamaz.
