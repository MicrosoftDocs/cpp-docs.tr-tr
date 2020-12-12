---
description: 'Daha fazla bilgi edinin: örnek program'
title: Örnek Program
ms.date: 11/04/2016
ms.assetid: fc22ef82-9caa-425f-b201-2891bc123d1f
ms.openlocfilehash: 85cba2263e2e9f8f94bf8fda8ca1359cecc9a5d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196522"
---
# <a name="example-program"></a>Örnek Program

Aşağıdaki C kaynak programı iki kaynak dosyadan oluşur. C programında olası çeşitli bildirimlerin ve tanımlardan bazılarına genel bakış sunar. Bu kitapta daha sonraki bölümlerde, bu bildirimlerin, tanımların ve başlatmanın nasıl yazılacağı ve ve gibi C anahtar sözcüklerinin nasıl kullanılacağı açıklanır **`static`** **`extern`** . `printf`İşlevi, STDIO. H C üstbilgi dosyasında bildirilmiştir.

`main`Ve `max` işlevlerinin ayrı dosyalarda olduğu varsayılır ve programın yürütülmesi `main` işlevle başlar. Daha önce hiçbir açık Kullanıcı işlevi yürütülmez `main` .

```
/*****************************************************************
                    FILE1.C - main function
*****************************************************************/

#define ONE     1
#define TWO     2
#define THREE   3
#include <stdio.h>

int a = 1;                       // Defining declarations
int b = 2;                       //  of external variables

extern int max( int a, int b );  // Function prototype

int main()                       // Function definition
{                                //  for main function
    int c;                       // Definitions for
    int d;                       //  two uninitialized
                                 //  local variables

    extern int u;                // Referencing declaration
                                 //  of external variable
                                 //  defined elsewhere
    static int v;                // Definition of variable
                                 //  with continuous lifetime

    int w = ONE, x = TWO, y = THREE;
    int z = 0;

    z = max( x, y );             // Executable statements
    w = max( z, w );
    printf_s( "%d %d\n", z, w );
    return 0;
}

/****************************************************************
            FILE2.C - definition of max function
****************************************************************/

int max( int a, int b )          // Note formal parameters are
                                 //  included in function header
{
    if( a > b )
        return( a );
    else
        return( b );
}
```

FILE1. C, işlev için prototipi içerir `max` . İşlev kullanılmadan önce bildirildiği için, bu tür bir bildirime bazen "ileri bildirim" denir. `main`İşlevin tanımı öğesine çağrıları içerir `max` .

İle başlayan satırlar `#define` Önişlemci yönergelerinden. Bu yönergeler, önişlemcinin tanımlayıcıları, `ONE` `TWO` , ve `THREE` `1` sırasıyla, `2` `3` FILE1. C boyunca, ve değerleriyle değiştirmesini söyler. Ancak, yönergeler DOSYA2 için de geçerlidir. C, ayrı olarak derlenen ve ardından FıLE1. C ile bağlantılandırılır. İle başlayan satır, `#include` derleyiciye STDIO dosyasını dahil etmek üzere bildirir. İşlev için prototipi içeren H `printf` . [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) , *Önişlemci başvurusunda* açıklanmıştır.

FILE1. C, genel değişkenleri ve öğesini başlatmak için bildirimleri tanımlamayı kullanır `a` `b` . Yerel değişkenler `c` ve `d` bildirilmemiş ancak başlatılmamış. Depolama alanı tüm bu değişkenler için ayrılır. Statik ve dış değişkenler, `u` ve `v` otomatik olarak 0 olarak başlatılır. Bu nedenle, yalnızca,, `a` `b` ve, `u` `v` açıkça veya örtük olarak başlatıldıklarından, her ne kadar anlamlı değerler içerir. Dosya2. C, için işlev tanımı içerir `max` . Bu tanım, `max` FILE1. C ' de yapılan çağrıları karşılar.

Tanımlayıcıların yaşam süresi ve görünürlüğü, [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)bölümünde ele alınmıştır. İşlevler hakkında daha fazla bilgi için bkz. [işlevler](../c-language/functions-c.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)
