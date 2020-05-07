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
ms.openlocfilehash: 941994f668fa035b569f9ccae2c301ebf42bcda6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157961"
---
# <a name="storage-class-specifiers-for-external-level-declarations"></a>Dış Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları

Dış değişkenler dosya kapsamındaki değişkenlerdir. Bunlar herhangi bir işlev dışında tanımlanır ve büyük olasılıkla birçok işlev için kullanılabilir. İşlevler yalnızca dış düzeyde tanımlanabilir ve bu nedenle iç içe geçirilemez. Varsayılan olarak, dış değişkenlere ve aynı ada sahip işlevlere yapılan tüm başvurular aynı nesneye başvurudur ve bu, "dış bağlantı" anlamına gelir. (Bunu geçersiz kılmak için **static** anahtar sözcüğünü kullanabilirsiniz. **Statik**hakkında daha fazla bilgi için bu bölümün ilerleyen kısımlarında yer alan bilgilere bakın.)

Dış düzeydeki değişken bildirimleri değişkenlerin tanımlardır ("bildirimleri tanımlama") ya da başka bir yerde tanımlanan değişkenlere ("başvuru bildirimleri") başvurur.

Değişkeni de Başlatan bir dış değişken bildirimi (örtük veya açık), değişkenin tanımlama bildirimidir. Dış düzeydeki bir tanım, birkaç form alabilir:

- **Statik** depolama sınıfı Belirleyicisi ile bildirdiğiniz bir değişken. [Başlatma](../c-language/initialization.md)bölümünde anlatıldığı gibi **statik** değişkeni sabit bir ifadeyle açıkça başlatabilirsiniz. Başlatıcıyı atlarsanız, değişken varsayılan olarak 0 olarak başlatılır. Örneğin, bu iki deyimin her ikisi de değişkenin `k`tanımları olarak kabul edilir.

    ```
    static int k = 16;
    static int k;
    ```

- Dış düzeyde açıkça başlattığınız bir değişken. Örneğin, `int j = 3;` değişkeninin `j`bir tanımıdır.

Dış düzeydeki (diğer bir deyişle, tüm işlevlerin dışında) değişken bildirimlerinde, **statik** veya `extern` depolama sınıfı belirticisini kullanabilir ya da depolama sınıfı belirticisini tamamen atlayabilirsiniz. **Auto** ve **register** *Storage-Class-belirleyicisi* terminallerini dış düzeyde kullanamazsınız.

Dış düzeyde bir değişken tanımlandıktan sonra, çeviri biriminin geri kalanı boyunca görünür olur. Değişken, aynı kaynak dosyasındaki bildiriminden önce görünür değil. Ayrıca, başvuruda bulunan bir bildirim, aşağıda açıklandığı gibi görünür hale belirtilmedikçe, programın diğer kaynak dosyalarında görünmez.

**Statik** ile ilgili kurallar şunlardır:

- **Static** anahtar sözcüğü olmadan tüm blokların dışında belirtilen değişkenler, her zaman değerlerini program boyunca tutar. Belirli bir çeviri birimine erişimleri kısıtlamak için **static** anahtar sözcüğünü kullanmanız gerekir. Bu, "iç bağlantı" sağlar. Bir programın tamamına Global hale getirmek için açık depolama sınıfını atlayın veya anahtar sözcüğünü `extern` kullanın (sonraki listede bulunan kurallara bakın). Bu, "dış bağlantı" sağlar. İç ve dış bağlantı Ayrıca [bağlantı](../c-language/linkage.md)bölümünde ele alınmıştır.

- Dış düzeyde bir değişkeni bir program içinde yalnızca bir kez tanımlayabilirsiniz. Farklı bir çeviri biriminde aynı ada ve **statik** depolama sınıfı belirticisine sahip başka bir değişken tanımlayabilirsiniz. Her **statik** tanım yalnızca kendi çeviri birimi içinde görünür olduğundan, çakışma oluşmaz. Bu, tek bir çeviri biriminin işlevleri arasında paylaşılması gereken ancak diğer çeviri birimlerine görünmeyen tanımlayıcı adlarını gizlemek için kullanışlı bir yol sağlar.

- **Statik** depolama sınıfı belirticisi işlevlerine de uygulanabilir. **Statik**bir işlev bildirirseniz, adının bildirildiği dosyanın dışında görünmez olur.

Kullanım `extern` kuralları şunlardır:

- Depolama `extern` sınıfı Belirleyicisi, başka bir yerde tanımlı bir değişkene başvuru bildirir. Bir `extern` bildirimi başka bir kaynak dosyasında görünür hale getirmek veya bir değişkeni aynı kaynak dosyasında tanımından önce görünür hale getirmek için kullanabilirsiniz. Dış düzeyde değişkene bir başvuru bildirdikten sonra değişken, belirtilen başvurunun gerçekleştiği çeviri biriminin geri kalanı boyunca görünür olur.

- `extern` Başvurunun geçerli olması için, başvurduğu değişkenin bir kez ve yalnızca bir kez tanımlanması gerekir ve dış düzeyde. Bu tanım ( `extern` depolama sınıfı olmadan) programı oluşturan herhangi bir çeviri biriminde olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte dış bildirimler gösterilmektedir:

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

Bu örnekteki iki kaynak dosyasında toplam üç dış bildirim bulunur `i`. Yalnızca bir bildirim "tanımlama bildirimi" dir. Bu bildirim,

```
int i = 3;
```

genel değişkeni `i` tanımlar ve ilk değeri 3 ile başlatır. Kullanılarak `extern` ilk kaynak dosyanın en üstünde `i` "başvuru" bildirimi, genel değişkeni dosyadaki tanımlama bildiriminden önce görünür hale getirir. İkinci kaynak dosyada başvuru `i` bildirimi aynı zamanda değişkeni bu kaynak dosyasında görünür hale getirir. Çeviri biriminde bir değişken için tanımlama örneği sağlanmazsa, derleyici bir

```
extern int x;
```

Bildirime başvurma ve başvuru tanımlama

```
int x = 0;
```

programın başka bir çeviri biriminde görünür.

, `main`, Ve `next` `other`olmak üzere üç işlevi de aynı görevi gerçekleştirir: bunları artırıp `i` yazdırırlar. 4, 5 ve 6 değerleri yazdırılır.

Değişken `i` başlatılmamış ise, otomatik olarak 0 olarak ayarlanmıştır. Bu durumda, 1, 2 ve 3 değerleri yazdırılmıştır. Değişken başlatma hakkında bilgi için bkz. [başlatma](../c-language/initialization.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama Sınıfları](../c-language/c-storage-classes.md)
