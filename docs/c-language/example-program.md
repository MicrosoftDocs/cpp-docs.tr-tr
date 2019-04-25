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

Aşağıdaki C kaynak programında iki kaynak dosyalardan oluşur. Bu, bazı çeşitli bildirimlerinin ve tanımlarının bir C programında olası bir genel bakış sağlar. Bu kitap sonraki bölümlerde, bu bildirimler, tanımlar ve başlatmalar yazma ve C anahtar sözcükleri gibi kullanmayı açıklar **statik** ve `extern`. `printf` STDIO C üstbilgi dosyasında bildirilen işlev. H

`main` Ve `max` işlevlerini ayrı dosyalarında olmasını olduğu varsayılır ve programın yürütülmesi ile başlayan `main` işlevi. Hiçbir açık kullanıcı işlevleri önce yürütülür `main`.

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

FILE1'DE. C için prototip içeren `max` işlevi. Bu tür bir bildirim bazen kullanılmadan önce işlevin bildirildiği için "İleri dönük bildirimi" adı verilir. Tanımı `main` işlev çağrılarını içerir `max`.

İle başlayan satırlar `#define` önişlemci yönergeleri. Bu yönergeler önişlemciye tanımlayıcıları değiştirin söyleyin `ONE`, `TWO`, ve `THREE` sayılarla `1`, `2`, ve `3`sırasıyla dosya1 boyunca. C. Ancak, yönergeleri dosya2 için geçerli değildir. Ayrı olarak derlenmiş ve ardından ile dosya1'e bağlı C. C. İle satır başına `#include` derleyiciye STDIO dosyasını dahil edin. İçin prototip içeren H `printf` işlevi. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) açıklanmıştır *önişlemci başvurusu*.

FILE1'DE. Genel değişkenler başlatmak için bildirimleri tanımlama C kullandığı `a` ve `b`. Yerel değişkenler `c` ve `d` bildirilir ancak başlatılmadı. Depolama alanı, tüm bu değişkenler için ayrılır. Statik ve dış değişkenler `u` ve `v`, otomatik olarak 0 olarak başlatılır. Bu nedenle yalnızca `a`, `b`, `u`, ve `v` bunlar, açıkça veya örtülü olarak başlatıldığından bildirildiğinde anlamlı değerleri içerir. DOSYA2. C işlev tanımı içeren `max`. Bu tanımı karşılayan çağrıları `max` fıle1'de. C.

Ömür ve görünürlük tanımlayıcıların ele alınmıştır [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md). İşlevler hakkında daha fazla bilgi için bkz. [işlevleri](../c-language/functions-c.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)
