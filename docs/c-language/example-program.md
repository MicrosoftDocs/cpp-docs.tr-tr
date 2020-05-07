---
title: Örnek Program
ms.date: 11/04/2016
ms.assetid: fc22ef82-9caa-425f-b201-2891bc123d1f
ms.openlocfilehash: fc00ee391fd845039791b8cec727623074a7aeff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233948"
---
# <a name="example-program"></a>Örnek Program

Aşağıdaki C kaynak programı iki kaynak dosyadan oluşur. C programında olası çeşitli bildirimlerin ve tanımlardan bazılarına genel bakış sunar. Bu kitapta daha sonraki bölümlerde, bu bildirimlerin, tanımların ve başlatmanın nasıl yazılacağı ve **statik** ve `extern`gibi C anahtar sözcüklerinin nasıl kullanılacağı açıklanır. `printf` IşLEVI, stdio C üstbilgi dosyası içinde bildirilmiştir. Olsun.

Ve işlevlerinin ayrı dosyalarda olduğu varsayılır ve programın yürütülmesi `main` işlevle başlar. `max` `main` Daha önce `main`hiçbir açık Kullanıcı işlevi yürütülmez.

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

FILE1. C, `max` işlev için prototipi içerir. İşlev kullanılmadan önce bildirildiği için, bu tür bir bildirime bazen "ileri bildirim" denir. `main` İşlevin tanımı öğesine `max`çağrıları içerir.

İle `#define` başlayan satırlar Önişlemci yönergelerinden. Bu `ONE`yönergeler, ön işlemcinin tanımlayıcıları `TWO` `THREE` `1` `2`,, ve sırasıyla, FILE1 tamamında, ve `3`değerleriyle değiştirmesini söyler. ,. Ancak, yönergeler DOSYA2 için de geçerlidir. C, ayrı olarak derlenen ve sonra FıLE1 ile bağlantılandırılır. ,. İle `#include` başlayan satır, derleyiciye stdio dosyasını dahil etmek üzere bildirir. `printf` İşlev için prototipi içeren H. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) , *Önişlemci başvurusunda*açıklanmıştır.

FILE1. C, genel değişkenleri `a` ve `b`öğesini başlatmak için bildirimleri tanımlamayı kullanır. Yerel değişkenler `c` ve `d` bildirilmemiş ancak başlatılmamış. Depolama alanı tüm bu değişkenler için ayrılır. Statik ve dış değişkenler, `u` ve `v`otomatik olarak 0 olarak başlatılır. Bu nedenle `a`, `b`yalnızca `u`,, `v` ve, açıkça veya örtük olarak başlatıldıklarından, her ne kadar anlamlı değerler içerir. Dosya2. C, için `max`işlev tanımı içerir. Bu tanım, FıLE1 içinde öğesine `max` yapılan çağrıları karşılar. ,.

Tanımlayıcıların yaşam süresi ve görünürlüğü, [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)bölümünde ele alınmıştır. İşlevler hakkında daha fazla bilgi için bkz. [işlevler](../c-language/functions-c.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)
