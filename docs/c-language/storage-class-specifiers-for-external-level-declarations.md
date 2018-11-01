---
title: Dış Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- external definitions
- linkage [C++], external
- external linkage, variable declarations
- declaring variables, external variables
- declarations [C++], external
- declarations [C++], specifiers
- external declarations
- static variables, external declarations
- variables, visibility
- external linkage, storage-class specifiers
- referencing declarations
- visibility, variables
- static storage class specifiers
ms.assetid: b76b623a-80ec-4d5d-859b-6cef422657ee
ms.openlocfilehash: 35b8b3082841c14f1cb82778978a84c89a17618d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587882"
---
# <a name="storage-class-specifiers-for-external-level-declarations"></a>Dış Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları

Dış değişkenleri dosya kapsamında değişkenlerdir. Herhangi bir işlevin dışında tanımlanmış ve birçok işlev için potansiyel olarak kullanılabilir. İşlevler yalnızca dış düzeyinde tanımlanabilir ve bu nedenle, iç içe olamaz. Varsayılan olarak, dış değişkenlerin ve işlevlerin aynı ada sahip oldukları "dış bağlantısı." anlamına gelir aynı nesneye başvuru kastetmektedir (Kullanabilirsiniz **statik** bunu geçersiz kılmak için anahtar sözcüğü. Daha fazla ayrıntı için bu bölümün sonraki kısımlarında bilgilere bakın **statik**.)

Değişken bildirimlerini dış düzeyde ("bildirimleri tanımlama") değişkenlerin ya da tanımlardır veya başka bir yerde ("bildirimlere başvurma") tanımlanan değişkenleri başvuruları.

Ayrıca bir değişken (örtük veya açık) başlatan bir dış değişken bildirimi bir tanımlama bildirimi değişkeninin ' dir. Dış düzeyde bir tanımı çeşitli biçimlerde olabilir:

- İle bildirdiğiniz bir değişken **statik** depolama sınıfı tanımlayıcısı. Açıkça başlatabilirsiniz **statik** açıklandığı değişken bir sabit ifadeyle [başlatma](../c-language/initialization.md). Başlatıcı atlarsanız, değişken varsayılan olarak 0 olarak başlatılır. Örneğin, bu iki deyimden hem dikkate alınan değişkenin tanımlardır `k`.

    ```
    static int k = 16;
    static int k;
    ```

- Dış düzeyde açıkça başlatmak bir değişken. Örneğin, `int j = 3;` bir değişken tanımı `j`.

Değişken bildirimlerinde dış düzeyde (diğer bir deyişle, tüm işlevler dışında), kullanabileceğiniz **statik** veya `extern` depolama sınıfı tanımlayıcısı veya depolama sınıfı tanımlayıcısı tamamen çıkarın. Kullanamazsınız **otomatik** ve **kaydetme** *depolama sınıfı tanımlayıcısı* terminaller dış düzeyde.

Bir değişken dış düzeydeki tanımlandığında, çeviri biriminin geri kalan aşamalarında görünür. Değişken aynı kaynak dosyada, bildiriminden önce görünür değil. Başvuruda bulunan bir bildirimi görünür, aşağıda açıklandığı gibi kolaylaştırır sürece Ayrıca, bu program başka kaynak dosyalarında görünür değildir.

İlgili kuralları **statik** içerir:

- Değişkenler tüm blokların dışında **statik** anahtar sözcüğü her zaman değerlerine program boyunca Beklet. Belirli bir çeviri, erişimi kısıtlamak için kullanmalısınız **statik** anahtar sözcüğü. Bu "İç bağlantısı." verir Bir programın tamamındaki genel hale getirmek için açık depolama sınıfı atlayın veya anahtar sözcüğünü kullanın `extern` (sonraki listesinde yer alan kurallara bakın). Bu "dış bağlantısı." verir İç ve dış bağlantı açıklanır ayrıca [bağlantı](../c-language/linkage.md).

- Dış düzey yalnızca bir kez bir programın, bir değişken tanımlayabilirsiniz. Aynı ada sahip başka bir değişken tanımlayabilirsiniz ve **statik** farklı bir çeviri birimindeki depolama sınıfı tanımlayıcısı. Her **statik** tanımı yalnızca kendi çeviri biriminde görünür yok çakışması ortaya çıkar. Bu, tek bir çeviri biriminin işlevleri arasında paylaşılan, ancak diğer çeviri birimleri için görünür değil olmalıdır bir tanımlayıcı adları gizlemek için kullanışlı bir yol sağlar.

- **Statik** depolama sınıfı tanımlayıcısı, işleve de uygulayabilirsiniz. Bir işlev bildirirseniz **statik**, adı bu bildirilen dosya dışında görünmez durumdadır.

Kullanmakla ilgili kuralları `extern` şunlardır:

- `extern` Depolama sınıfı tanımlayıcısı başka yerde tanımlanmış bir değişkene bir referans bildirir. Kullanabileceğiniz bir `extern` bildirimi bir tanım başka bir kaynak dosyasında görünür hale getirmek ya da aynı kaynak dosyada bir değişken tanımı önce görünür hale getirmek için. Dış düzeyde değişkeni başvuru bildirdikten sonra çeviri biriminin bildirilmiş başvuru oluştuğu geri kalanı görünür bir değişkendir.

- İçin bir `extern` geçerli olması için başvuru, değişkenin başvurduğu bir kez ve yalnızca bir kez dış düzeyde tanımlanmış olması gerekir. Bu tanımı (olmadan `extern` depolama sınıfı) programı olun çeviri birimleri birinde olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, dış bildirimler gösterilmektedir:

```
/******************************************************************
                      SOURCE FILE ONE
*******************************************************************/
#include <stdio.h>

extern int i;                // Reference to i, defined below
void next( void );           // Function prototype

int main()
{
    i++;
    printf_s( "%d\n", i );   // i equals 4
    next();
}

int i = 3;                  // Definition of i

void next( void )
{
    i++;
    printf_s( "%d\n", i );  // i equals 5
    other();
}

/******************************************************************
                      SOURCE FILE TWO
*******************************************************************/
#include <stdio.h>

extern int i;              // Reference to i in
                           // first source file
void other( void )
{
    i++;
    printf_s( "%d\n", i ); // i equals 6
}
```

Bu örnekte iki kaynak dosyalarını içeren üç dış bildirimlerini toplam `i`. Bir bildirimi yalnızca bir "tanımlama bildirimi." Bu bildirimi

```
int i = 3;
```

Genel değişken tanımlar `i` ve başlangıç değeri 3 ile başlatır. "Başvuru" bildirimi `i` dosyası birinci kaynak kullanmanın üst `extern` genel değişkeni dosyasında tanımlama bildiriminden önce görünür hale getirir. Başvuruda bulunan beyanı `i` ikinci kaynak dosyası da değişkeni görünür, kaynak dosyada yapar. Bir değişken tanımlayan bir örneğin bir çeviri birimindeki sağlanmazsa, derleyici, olduğunu varsayar bir

```
extern int x;
```

bildirim ve bir tanımlama başvuru başvurma

```
int x = 0;
```

programın başka bir çeviri biriminde görünür.

Üç işlev `main`, `next`, ve `other`, aynı görevi gerçekleştirmenin: Bunlar artırmak `i` ve yazdırabilirsiniz. 4, 5 ve 6 değerlerini yazdırılır.

Değişken `i` değil olsaydı başlatılır, 0'a otomatik olarak ayarlanacak. Bu durumda, değerler 1, 2 ve 3 yazdırılmış. Bkz: [başlatma](../c-language/initialization.md) değişken başlatma hakkında bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[C Depolama Sınıfları](../c-language/c-storage-classes.md)