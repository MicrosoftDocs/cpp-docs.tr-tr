---
title: Diğer adlar ve tür tanımları (C++)
ms.date: 11/04/2016
f1_keywords:
- typedef_cpp
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
ms.openlocfilehash: 9bb39a668605276a82117c1f0a8fe6dd2db20eea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546256"
---
# <a name="aliases-and-typedefs-c"></a>Diğer adlar ve tür tanımları (C++)

Kullanabileceğiniz bir *diğer ad bildirimi* eşanlamlısı olarak kullanmak için daha önce bildirilen bir tür için bir ad bildirmek için. (Bu mekanizma resmi olmayan adı olarak da adlandırılan bir *tür diğer adı*). Oluşturmak için bu mekanizma kullanabilirsiniz bir *diğer ad şablonu*, hangi özel ayırıcılar için özellikle yararlı olabilir.

## <a name="syntax"></a>Sözdizimi

```
using identifier = type;
```

## <a name="remarks"></a>Açıklamalar

*tanımlayıcı*<br/>
Diğer adı.

*Türü*<br/>
İçin bir diğer ad oluşturmakta olduğunuz tür tanımlayıcısı.

Bir diğer ad, yeni bir tür sunmaz ve var olan bir tür adı anlamını değiştiremezsiniz.

En basit bir diğer ad biçimi eşdeğerdir **typedef** C ++ 03 düzeneğinden:

```cpp
// C++11
using counter = long;

// C++03 equivalent:
// typedef long counter;
```

Bunların her ikisi de "sayaç" türündeki değişkenler oluşturulmasını sağlar. Bir tür diğer adı için bunun gibi bir şey daha kullanışlı olacaktır `std::ios_base::fmtflags`:

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

Diğer adlar da sahip işlev işaretçilerine çalışır, ancak eşdeğer typedef çok daha okunabilir:

```cpp
// C++11
using func = void(*)(int);

// C++03 equivalent:
// typedef void (*func)(int);

// func can be assigned to a function pointer value
void actual_function(int arg) { /* some code */ }
func fptr = &actual_function;

```

Sınırlama **typedef** mekanizmadır şablonları ile çalışmaz. Ancak, türü diğer ad sözdizimi C ++ 11'de, diğer ad şablonları oluşturulmasını sağlar:

```cpp
template<typename T> using ptr = T*;

// the name 'ptr<T>' is now an alias for pointer to T
ptr<int> ptr_int;

```

## <a name="example"></a>Örnek

Aşağıdaki örnek bir özel bellek ayırıcısı ile bir diğer ad şablonu kullanmayı gösterir; bu durumda, bir tamsayı vektör türü. Herhangi bir türü için değiştirebildiği **int** karmaşık parametre gizlemek için kullanışlı bir diğer ad oluşturmak için ana işlev kodunuzda listeler. Özel bellek ayırıcısı, tüm kodunuzda kullanarak okunabilirliği geliştirmek ve hataları tarafından yazım hatası nedeniyle giriş riskini azaltmak.

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

A **typedef** bildirimi tarafından verilen türe ilişkin bir eşanlam kapsamında, duruma bir ad tanıtır *tür-bildirimi* bildirimi kısmı.

Typedef bildirimleri bildirilen türleri veya zaten dili tarafından tanımlanan türler için daha kısa ya da daha anlamlı adlar oluşturmak için kullanabilirsiniz. TypeDef adları değişebilir uygulama ayrıntılarını kapsüllemek olanak sağlar.

Tersine **sınıfı**, **yapı**, **birleşim**, ve **enum** bildirimleri, **typedef** bildirimleri yeni türlerini tanıtır değildir — bunlar varolan türler için yeni adlar sunar.

Kullanılarak bildirilen adların **typedef** diğer tanımlayıcılarla (deyim etiketleri dışında) aynı ad alanını kaplar. Bu nedenle, sınıf türü bildirim dışında daha önce bildirilen bir adla aynı tanımlayıcıyı kullanamazlar. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// typedef_names1.cpp
// C2377 expected
typedef unsigned long UL;   // Declare a typedef name, UL.
int UL;                     // C2377: redefined.
```

Diğer tanımlayıcılarla ilgili ad gizleme kuralları kullanılarak bildirilen adların görünürlüğünü de yönetir **typedef**. Bu nedenle, aşağıdaki örnek C++'da geçerlidir:

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

Bir yerel kapsamı tanımlayıcısı için bir typedef ile aynı adla bildirirken veya bir yapı veya birleşim iç kapsamda veya aynı kapsamda üyesi bildirdiğinizde, tür tanımlayıcısı belirtilmelidir. Örneğin:

```cpp
typedef char FlagType;
const FlagType x;
```

Yeniden `FlagType` bir tanımlayıcı, bir yapı üyesinin veya birleşim üyesi, tür için ad sağlanmalıdır:

```cpp
const int FlagType;  // Type specifier required
```

Söyleyin için yeterli değil

```cpp
const FlagType;      // Incomplete specification
```

çünkü `FlagType` türü değil bildiriliyor tanımlayıcının bir parçası olarak alınır. Bu bildirim gibi bildirimi geçersiz olacak şekilde alınır

```cpp
int;  // Illegal declaration
```

Typedef, işaretçi, işlevi ve dizi türleri dahil olan her türlü bildirebilirsiniz. Yapı veya birleşim türü tanımlamadan önce bildirimiyle aynı görünürlük tanımını sahip olduğu sürece bir yapı veya birleşim türü işaretçisi için bir typedef adı bildirebilirsiniz.

### <a name="examples"></a>Örnekler

Bir kullanımını **typedef** bildirimleri olan daha tekdüzen ve compact bildirimleri yapma. Örneğin:

```cpp
typedef char CHAR;          // Character type.
typedef CHAR * PSTR;        // Pointer to a string (char *).
PSTR strchr( PSTR source, CHAR target );
typedef unsigned long ulong;
ulong ul;     // Equivalent to "unsigned long ul;"
```

Kullanılacak **typedef** aynı bildirimde temel ve türetilmiş türleri belirtmek için Bildirimciler virgülle ayırabilirsiniz. Örneğin:

```cpp
typedef char CHAR, *PSTR;
```

Aşağıdaki örnek türü sağlar `DRAWF` hiçbir değer döndürerek ve iki tamsayı bağımsız değişken alan bir işlev için:

```cpp
typedef void DRAWF( int, int );
```

Yukarıdaki sonra **typedef** deyimi, bildirimi

```cpp
DRAWF box;
```

bildirime eşdeğer olacaktır

```cpp
void box( int, int );
```

**TypeDef** ile birlikte **yapı** bildirmeyi ve kullanıcı tanımlı türler adlandırın:

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

### <a name="re-declaration-of-typedefs"></a>Tür tanımları yeniden bildirimi

**Typedef** bildirimi, aynı türe başvurmak amacıyla aynı adı yeniden bildirmek için kullanılabilir. Örneğin:

```cpp
// FILE1.H
typedef char CHAR;

// FILE2.H
typedef char CHAR;

// PROG.CPP
#include "file1.h"
#include "file2.h"   // OK
```

Program *PROG. CPP* içeren iki üstbilgi dosyalarını içeren **typedef** adı için bildirimleri `CHAR`. Her iki bildirim de aynı türe başvurduğu sürece, böyle bir yeniden bildirim kabul edilebilir.

A **typedef** daha önceden farklı bir tür olarak bildirilen bir adı yeniden tanımlayamaz. Bu nedenle, *Dosya2. H* içerir

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

### <a name="typedefs-in-c-vs-c"></a>tür tanımları C++ vs. C

Kullanım **typedef** tanımlayıcısı sınıf türleri ile desteklenen adlandırılmamış yapılarda bildirme büyük ölçüde ANSI C uygulaması nedeniyle **typedef** bildirimleri. Örneğin, birçok C Programcı aşağıdakini kullanın:

```cpp
// typedef_with_class_types1.cpp
// compile with: /c
typedef struct {   // Declare an unnamed structure and give it the
                   // typedef name POINT.
   unsigned x;
   unsigned y;
} POINT;
```

Böyle bir bildirim avantajlarından bildirimleri gibi sunmasıdır:

```cpp
POINT ptOrigin;
```

Onun yerine:

```cpp
struct point_t ptOrigin;
```

C++'da arasındaki farkı **typedef** adları ve gerçek türler (ile bildirilen **sınıfı**, **yapı**, **birleşim**ve **enum** anahtar sözcükleri) daha farklıdır. Ancak adsız bir yapıda bildirme C uygulaması bir **typedef** deyimi çalışmaya devam ettiğinden, c dilinde olduğu gibi hiçbir notational avantajlar sağlar.

```cpp
// typedef_with_class_types2.cpp
// compile with: /c /W1
typedef struct {
   int POINT();
   unsigned x;
   unsigned y;
} POINT;
```

Yukarıdaki örnekte adlı bir sınıfı bildirir `POINT` adsız sınıf kullanarak **typedef** söz dizimi. `POINT` sınıf adı olarak kabul edilir; Ancak, bu şekilde bildirilen adlar için aşağıdaki kısıtlamalar uygulanır:

- ' % S'adı (eş anlamlı) sonra yer alamaz bir **sınıfı**, **yapı**, veya **birleşim** önek.

- Ad, sınıf bildirimi içinde oluşturucu veya yıkıcı adları olarak kullanılamaz.

Özet olarak, bu sözdizimi, devralma, oluşturma veya yok etme için herhangi bir mekanizma sağlamaz.