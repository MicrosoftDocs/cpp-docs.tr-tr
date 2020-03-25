---
title: Diğer adlar ve tür tanımları (C++)
ms.date: 11/04/2016
f1_keywords:
- typedef_cpp
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
ms.openlocfilehash: 7a45c4570341aca056b9d4c30ea496317a1ac96f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181570"
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

*type*<br/>
İçin bir diğer ad oluşturduğunuz tür tanımlayıcısı.

Diğer ad yeni bir tür sunmaz ve var olan bir tür adının anlamını değiştiremezler.

Diğer adın en basit biçimi, C++ 03 ' den **typedef** mekanizmasına eşdeğerdir:

```cpp
// C++11
using counter = long;

// C++03 equivalent:
// typedef long counter;
```

Her ikisi de "Counter" türünde değişkenlerin oluşturulmasını etkinleştirir. Daha kullanışlı bir şey, `std::ios_base::fmtflags`için bunun gibi bir tür diğer adı olacaktır:

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

**Typedef** mekanizmasıyla ilgili bir sınırlama, şablonlarla çalışmamasıdır. Ancak, C++ 11 ' de tür diğer adı sözdizimi diğer ad şablonlarının oluşturulmasını mümkün değildir:

```cpp
template<typename T> using ptr = T*;

// the name 'ptr<T>' is now an alias for pointer to T
ptr<int> ptr_int;
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir diğer ad şablonunun özel bir ayırıcıyla nasıl kullanıldığını gösterir — Bu örnekte, bir tamsayı vektör türüdür. Ana işlevsel kodunuzda karmaşık parametre listelerini gizlemek için uygun bir diğer ad oluşturmak üzere **int** için herhangi bir türü kullanabilirsiniz. Kodunuzun tamamında özel ayırıcıyı kullanarak okunabilirliği iyileştirebilir ve yazım hataları nedeniyle oluşan hataları tanıtma riskini azaltabilirsiniz.

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

Bir **typedef** bildirimi, kapsamında, bildirimin *tür bildirimi* bölümü tarafından verilen tür için bir eş anlamlı haline gelir.

Zaten dil veya bildirdiğiniz türler için tanımlanmış olan türler için daha kısa veya daha anlamlı adlar oluşturmak üzere typedef bildirimlerini kullanabilirsiniz. Typedef adları, değişebilir uygulama ayrıntılarını kapsüllemek için izin verir.

**Sınıf**, **Yapı**, **birleşim**ve **numaralandırma** bildirimlerinin aksine, **typedef** bildirimleri yeni türler sunmaz; var olan türler için yeni adlar getirir.

**Typedef** kullanılarak belirtilen adlar, diğer tanımlayıcılarla aynı ad alanını kaplar (ifade etiketleri hariç). Bu nedenle, sınıf türü bildirim dışında daha önce bildirilen bir adla aynı tanımlayıcıyı kullanamazlar. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// typedef_names1.cpp
// C2377 expected
typedef unsigned long UL;   // Declare a typedef name, UL.
int UL;                     // C2377: redefined.
```

Diğer Tanımlayıcılarla ilgili ad gizleme kuralları, **typedef**kullanılarak belirtilen adların görünürlüğünü de yönetir. Bu nedenle, aşağıdaki örnek C++'da geçerlidir:

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

Bir typedef ile aynı ad ile bir yerel kapsam tanımlayıcısı bildirirken veya aynı kapsamda veya bir iç kapsamda bir yapının veya birleşimin üyesini bildirirken tür belirleyicisi belirtilmelidir. Örneğin:

```cpp
typedef char FlagType;
const FlagType x;
```

Tanımlayıcı, yapı üyesi veya birleşim üyesi için `FlagType` adını yeniden kullanmak için, tür sağlanmalıdır:

```cpp
const int FlagType;  // Type specifier required
```

Söylemek yeterli değildir

```cpp
const FlagType;      // Incomplete specification
```

`FlagType`, yeniden bildirilebilecek bir tanımlayıcı değil türün parçası olacak şekilde alındığından. Bu bildirim, şunun gibi geçersiz bir bildirim olacak şekilde alınır

```cpp
int;  // Illegal declaration
```

İşaretçi, işlev ve dizi türleri dahil olmak üzere typedef ile herhangi bir tür bildirebilirsiniz. Tanımın bildirimle aynı görünürlüğe sahip olduğu sürece yapıyı veya birleşim türünü tanımladıktan önce bir yapı veya birleşim türü işaretçisi için bir typedef adı bildirebilirsiniz.

### <a name="examples"></a>Örnekler

**Typedef** bildirimlerinin bir kullanımı, bildirimlerin daha Tekdüzen ve kompakt olmasını sağlar. Örneğin:

```cpp
typedef char CHAR;          // Character type.
typedef CHAR * PSTR;        // Pointer to a string (char *).
PSTR strchr( PSTR source, CHAR target );
typedef unsigned long ulong;
ulong ul;     // Equivalent to "unsigned long ul;"
```

Aynı bildirimde temel ve türetilmiş türleri belirtmek üzere **typedef** kullanmak için, bildirimcilerin virgülle ayırabilirsiniz. Örneğin:

```cpp
typedef char CHAR, *PSTR;
```

Aşağıdaki örnek, bir değer döndüren ve iki int bağımsız değişken alan bir işlev için tür `DRAWF` sağlar:

```cpp
typedef void DRAWF( int, int );
```

Yukarıdaki **typedef** ifadesinden sonra bildirim

```cpp
DRAWF box;
```

Bildirime eşdeğerdir

```cpp
void box( int, int );
```

**typedef** , Kullanıcı tanımlı türleri bildirmek ve adlandırmak için genellikle **struct** ile birleştirilir:

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

**Typedef** bildirimi aynı türü belirtmek için aynı adı yeniden bildirmek üzere kullanılabilir. Örneğin:

```cpp
// FILE1.H
typedef char CHAR;

// FILE2.H
typedef char CHAR;

// PROG.CPP
#include "file1.h"
#include "file2.h"   // OK
```

Program program programı *. CPP* , her ikisi de `CHAR`ad için **typedef** bildirimleri içeren iki üst bilgi dosyası içerir. Her iki bildirim de aynı türe başvurduğu sürece, böyle bir yeniden bildirim kabul edilebilir.

Bir **typedef** daha önce farklı bir tür olarak belirtilen adı yeniden tanımlanamaz. Bu nedenle, *dosya2. H* şunu içerir

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

### <a name="typedefs-in-c-vs-c"></a>vs. C C++ 'de tür tanımları

**Typedef bildiriminde** adlandırılmamış yapıları bildirmek IÇIN kullanılan ANSI C uygulaması nedeniyle, sınıf türleri ile **typedef** belirleyicisi kullanılması büyük ölçüde desteklenir. Örneğin, birçok C programcısı şunları kullanır:

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

' C++De, **typedef** adları ve gerçek türler arasındaki fark ( **sınıf**, **Yapı**, **birleşim**ve **enum** anahtar sözcükleriyle belirtilen), daha farklıdır. Bir **typedef** ifadesinde isimsiz bir yapı bildirmenin c uygulaması hala işe yaramazsa, c içinde olduğu gibi notational avantajlarına sahip değildir.

```cpp
// typedef_with_class_types2.cpp
// compile with: /c /W1
typedef struct {
   int POINT();
   unsigned x;
   unsigned y;
} POINT;
```

Önceki örnek adlandırılmamış sınıf **typedef** sözdizimini kullanarak `POINT` adlı bir sınıf bildirir. `POINT`, sınıf adı olarak değerlendirilir; Ancak, aşağıdaki kısıtlamalar bu şekilde tanıtılan adlara uygulanır:

- Ad (eş anlamlı) bir **sınıf**, **Yapı**veya **birleşim** öneki öğesinden sonra yer alamaz.

- Ad, sınıf bildiriminde Oluşturucu veya yıkıcı adları olarak kullanılamaz.

Özet olarak, bu sözdizimi devralma, oluşturma veya yok etme için herhangi bir mekanizma sağlamaz.
