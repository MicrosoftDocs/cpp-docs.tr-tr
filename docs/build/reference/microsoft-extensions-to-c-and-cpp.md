---
title: "C ve C++ için Microsoft uzantıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8453209a92b8f7485a9e7f575fb8810196d27fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoft-extensions-to-c-and-c"></a>C ve C++ için Microsoft Uzantıları
Visual C++ ANSI C ve C++ ANSI standartları şu şekilde genişletir.  
  
## <a name="keywords"></a>Anahtar Sözcükler  
 Birkaç anahtar sözcükleri eklenir. Listede [anahtar sözcükleri](../../cpp/keywords-cpp.md), iki başında alt çizgi olan Visual C++ uzantıları anahtar sözcükler.  
  
## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Sınıf tanımı statik const Integral (veya enum) üyeleri dışında  
 Standart altında (**/Za**), aşağıda gösterildiği gibi veri üyeleri için bir sınıf çıkış tanımı yapmalısınız:  
  
```  
  
      class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 Altında **/Ze**, sınıf tanımı statik, const Entegral ve const enum veri üyeleri için isteğe bağlıdır. Yalnızca integraller ve statik ve const numaralandırmaları başlatıcıları bir sınıfta olabilir; const deyimi başlatılırken ifade olmalıdır.  
  
 Bir üstbilgisinde dosya ve üstbilgi dosyası dahil sağlanan birden çok kaynak dosyalarında bir sınıf çıkış tanımı olduğunda hataları önlemek için [selectany](../../cpp/selectany.md). Örneğin:  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## <a name="casts"></a>Atamaları  
 C++ derleyicisi ve C Derleyici ANSI olmayan atamaları bu türlerini destekler:  
  
-   L-değeri oluşturmak üzere olmayan ANSI atamaları. Örneğin:  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  Bu uzantı yalnızca C dilinde kullanılabilir. Farklı bir türe işaretçidir gibi bir işaretçi değiştirmek için C++ kodu aşağıdaki ANSI C Standart formu kullanın.  
  
     ANSI C Standart uyacak şekilde aşağıdaki gibi önceki örnekte yazılması.  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   Bir işlev işaretçisi veri işaretçisi olmayan ANSI atamaları. Örneğin:  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     Aynı dönüştürme gerçekleştirmek ve aynı zamanda ANSI uyumluluğu korumak için işlev işaretçisi çevirebilirsiniz bir `uintptr_t` veri işaretçisi cast önce:  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## <a name="variable-length-argument-lists"></a>Değişken uzunlukta bağımsız değişken listeleri  
 C++ derleyicisi ve C Derleyici bir tür sağlar, bunun yerine bir işlev tanımı tarafından izlenen bağımsız değişken sayıda belirtir işlevi bildirimcisi destekler:  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## <a name="single-line-comments"></a>Tek satırlı yorumlar  
 C derleyicisi iki eğik kullanarak sunulan tek satırlı yorumlar destekler (/ /) karakterleri:  
  
```  
// This is a single-line comment.  
```  
  
## <a name="scope"></a>Kapsam  
 C derleyicisi kapsamı ile ilgili aşağıdaki özellikleri destekler.  
  
-   Extern öğeleri statik olarak yeniden:  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   Aynı kapsamdaki zararsız typedef yeniden kullanın:  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   İşlev bildirimleri dosya kapsamı vardır:  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   Blok kapsamı değişkenlerin nonconstant ifadeler kullanarak tarafından başlatılan kullanın:  
  
    ```  
    int clip( int );  
    int bar( int );  
    int main( void )  
    {  
        int array[2] = { clip( 2 ), bar( 4 ) };  
    }  
    int clip( int x )  
    {  
        return x;  
    }  
    int bar( int x )  
    {  
        return x;  
    }  
    ```  
  
## <a name="data-declarations-and-definitions"></a>Veri bildirimler ve tanımlar  
 C derleyicisi aşağıdaki veri bildirimi ve tanımı özelliklerini destekler.  
  
-   Karma karakter ve dize sabitleri bir başlatıcı içinde:  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   Bit dışında temel türlerine sahip alanlar **imzasız int** veya **imzalı int**.  
  
-   Bir türe sahip olmayan bildiriciler:  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   Yapılar ve birleşimleri en son alanda olarak boyutsuz diziler:  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   Adlandırılmamış (anonim) yapıları:  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   Adlandırılmamış (anonim) birleşimler:  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   Adlandırılmamış Üyeler:  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## <a name="intrinsic-floating-point-functions"></a>İç kayan nokta işlevleri  
 C++ derleyicisi ve C Derleyici satır içi nesil Destek **x86 belirli >** , `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, ve `tan` işlevleri **son x86 belirli** zaman **/Oi** belirtilir. Bu yapı kullanıldığında, ayarlı olduğundan C derleyici için ANSI uyumluluğu kaybolur `errno` değişkeni.  
  
## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Const olmayan işaretçi parametresi, bir işleve geçirme Const işaretçi parametresi için bir başvuru bekliyor  
 Bu C++ uzantısıdır. Bu kod ile derlenir **/Ze**:  
  
```  
typedef   int   T;  
  
const T  acT = 9;      // A constant of type 'T'  
const T* pcT = &acT;   // A pointer to a constant of type 'T'  
  
void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'  
{  
   rpcT = pcT;  
}  
  
T*   pT;               // A pointer to a 'T'  
  
void func ()  
{  
   func2 ( pT );      // Should be an error, but isn't detected  
   *pT   = 7;         // Invalidly overwrites the constant 'acT'  
}  
```  
  
## <a name="iso646h-not-enabled"></a>ISO646. H etkin değil  
 Altında **/Ze**, aşağıdaki işleçleri metin biçimlerinin kullanmak istiyorsanız, iso646.h eklemek zorunda:  
  
-   & & (ve)  
  
-   & = (and_eq)  
  
-   & (bitand)  
  
-   &#124; (bitor)  
  
-   ~ (compl)  
  
-   ! (yok)  
  
-   ! = (not_eq)  
  
-   &#124; &#124; (veya)  
  
-   &#124; (or_eq) =  
  
-   ^ (xor)  
  
-   ^ = (xor_eq)  
  
## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Dize değişmez değer türü sahip const char [], değil const karakter (*) [] adresidir  
 Aşağıdaki örnek, char const olmadığını çıkış (\*) [4] altında **/Za**, ancak char const [4] altında **/Ze**.  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ Za, /Ze (dil uzantılarını devre dışı bırak)](../../build/reference/za-ze-disable-language-extensions.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)