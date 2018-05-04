---
title: Diğer adlar ve tür tanımları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typedef_cpp
dev_langs:
- C++
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c020d9fc4a8bc5275fe77b05eff74fdcec25ec6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="aliases-and-typedefs-c"></a>Diğer adlar ve tür tanımları (C++)
Kullanabileceğiniz bir *diğer bildirimi* için önceden tanımlanmış bir türü eşanlamlısı olarak kullanılacak bir ad bildirmek için. (Bu düzenek basit olarak da adlandırılan bir *türü diğer ad*). Oluşturmak için bu düzenek kullanabilirsiniz bir *diğer şablon*, hangi özel allocators için özellikle yararlı olabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
using identifier = type;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `identifier`  
 Diğer adı.  
  
 `type`  
 İçin bir diğer ad oluşturma türü tanımlayıcısı.  
  
 Bir diğer ad yeni bir tür sunmaz ve var olan bir tür adı anlamını değiştiremezsiniz.  
  
 Bir diğer ad en basit biçimi eşdeğerdir `typedef` C ++ 03 düzeneğinden:  
  
```cpp  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
```  
  
 Bunların her ikisi de "sayacı" türündeki değişkenler oluşturulmasını sağlamak. Daha kullanışlı bir şey için bunun gibi bir türü diğer ad olacak `std::ios_base::fmtflags`:  
  
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
  
 Diğer adlar da işlev işaretçileri ile çalışır, ancak eşdeğer typedef çok daha okunabilir:  
  
```cpp  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 Sınırlandırılmasıdır `typedef` mekanizmasıdır şablonları ile çalışmaz. Ancak, C ++ 11 türü diğer ad sözdiziminde diğer şablonları oluşturulmasını sağlar:  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir diğer ad şablon ile özel bir ayırıcı kullanmak üzere nasıl gösterir; bu durumda, bir tamsayı vektör türü. Herhangi bir türü için alternatif `int` karmaşık parametre gizlemek için kullanışlı bir diğer adı oluşturmak için ana işlevsel kodunuzda listeler. Tüm kodunuzda özel ayırıcısı kullanarak okunabilirliğini artırmak ve yazım hatalarını tarafından neden hatalar Tanıtımı riskini azaltmak.  
  
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
 A `typedef` bildirimi tanıtır kapsamında, bir eş tarafından verilen türünün hale bir ad *türü bildirimi* bildirimi kısmı.  
  
 Typedef bildirimleri daha kısa ya da daha anlamlı adları zaten dili tarafından tanımlanan türlerin veya bildirilen türleri oluşturmak için kullanabilirsiniz. TypeDef adları değişebilir uygulama ayrıntılarını kapsülleyen olanak sağlar.  
  
 Tersine için **sınıfı**, `struct`, **UNION**, ve `enum` bildirimleri, `typedef` bildirimleri yeni türleri tanıtmak değil — varolan türleri için yeni adlar tanıtır.  
  
 Kullanılarak bildirilen adları `typedef` diğer tanımlayıcıları (dışında deyimi etiketleri) aynı ad alanına kaplar. Bu nedenle, sınıf türü bildirim dışında daha önce bildirilen bir adla aynı tanımlayıcıyı kullanamazlar. Aşağıdaki örnek göz önünde bulundurun:  
  
```  
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 Diğer tanımlayıcılarla ilgili ad gizleme kuralları, `typedef` kullanılarak bildirilen adların görünürlüğünü de yönetir. Bu nedenle, aşağıdaki örnek C++'da geçerlidir:  
  
```  
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
 
  
```  
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
  
 Tür belirleyici bir typedef aynı adda bir yerel kapsamı tanımlayıcısı bildirme veya bir yapının veya birleşimin aynı kapsamı veya bir iç kapsamda üyesi bildirme belirtilmesi gerekir. Örneğin:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Yeniden `FlagType` bir tanımlayıcı, yapı üyesi veya bir bileşim üyesi, türü için ad sağlanmalıdır:  
  
```  
const int FlagType;  // Type specifier required  
```  
  
 Söylemek yeterli değil  
  
```  
const FlagType;      // Incomplete specification  
```  
  
 çünkü `FlagType` değil bildiriliyor bir tanımlayıcı türü parçası olarak alınır. Bu bildirim gibi geçersiz bir bildirim olarak alınır  
  
```  
int;  // Illegal declaration   
```  
  
 Typedef, işaretçi, işlevi ve dizi türleri dahil olmak üzere tüm türüyle bildirebilirsiniz. Yapı veya birleşim türü tanımlamadan önce bildirimiyle aynı görünürlük tanımına sahip olduğu sürece bir işaretçi bir yapı veya birleşim türü için bir typedef ad bildirebilirsiniz.  
  
### <a name="examples"></a>Örnekler  
 Bir kullanımını `typedef` bildirimleri olduğundan daha tekdüzen ve compact bildirimleri yapmak için. Örneğin:  
  
```cpp  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 Kullanılacak `typedef` aynı bildiriminde temel ve türetilen türlerin belirtmek için Bildirimciler virgülle ayırabilirsiniz. Örneğin:  
  
```  
typedef char CHAR, *PSTR;  
```  
  
 Aşağıdaki örnek türü sağlar `DRAWF` iki int bağımsız değişken almama ve herhangi bir değer döndüren bir işlev için:  
  
```  
typedef void DRAWF( int, int );  
```  
  
 Yukarıdaki sonra `typedef` deyimi, bildirimi  
  
```  
DRAWF box;   
```  
  
 bildirimine eşdeğer olacaktır  
  
```  
void box( int, int );  
```  
  
 `typedef` ile birlikte `struct` bildirme ve kullanıcı tanımlı türler adı için:  
  
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
 `typedef` bildirimi, aynı türe başvurmak amacıyla aynı adı yeniden bildirmek için kullanılabilir. Örneğin:  
  
```cpp  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
```  
  
 PROG.CPP programı, her biri `typedef` adının `CHAR` bildirimlerini içeren iki üstbilgi dosyasına sahiptir. Her iki bildirim de aynı türe başvurduğu sürece, böyle bir yeniden bildirim kabul edilebilir.  
  
 `typedef` daha önce farklı bir tür olarak bildirilen bir adı yeniden tanımlayamaz. Bu nedenle, FILE2.H  
  
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
  
### <a name="typedefs-in-c-vs-c"></a>tür tanımları C++ vs'de. C  
 Kullanımı `typedef` belirticisi sınıf türleri ile desteklenen adlandırılmamış yapılarda bildirme büyük ölçüde ANSI C uygulaması nedeniyle `typedef` bildirimleri. Örneğin, birçok C programcıları aşağıdakileri kullanın:  
  
```cpp  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 Bu tür bir bildirime avantajlarından gibi bildirimleri etkinleştirir şöyledir:  
  
```  
POINT ptOrigin;  
```  
  
 Onun yerine:  
  
```  
struct point_t ptOrigin;  
```  
  
 C++, arasındaki farkı `typedef` adları ve gerçek türleri (ile bildirilen **sınıfı**, `struct`, **UNION**, ve `enum` anahtar sözcükler) daha farklıdır. Ancak adsız yapısında bildirme C uygulaması bir `typedef` deyimi çalışmaya devam ettiğinden, c dilinde olduğu gibi hiçbir notational yararları sağlar  
  
```cpp  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 Önceki örnekte adlı bir sınıf bildirir `POINT` adlandırılmamış sınıfını kullanarak `typedef` sözdizimi. `POINT` bir sınıf adı olarak kabul edilir; Ancak, bu şekilde sunulan adları için aşağıdaki kısıtlamalar geçerlidir:  
  
-   Sonra (eş) adı bulunamaz bir **sınıfı**, `struct`, veya **UNION** öneki.  
  
-   Ad, bir sınıf bildirimi içinde Oluşturucusu veya yıkıcı adları olarak kullanılamaz.  
  
 Özet olarak, bu söz dizimini devralma, oluşturma ve yok etme için herhangi bir mekanizma sağlamaz.  
