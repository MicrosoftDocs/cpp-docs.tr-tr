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
ms.openlocfilehash: 6c30b8a12c0bf26bc35905872fb6fa527b367ef4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229473"
---
# <a name="storage-class-specifiers-for-external-level-declarations"></a>Dış Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları

Dış değişkenler dosya kapsamındaki değişkenlerdir. Bunlar herhangi bir işlev dışında tanımlanır ve büyük olasılıkla birçok işlev için kullanılabilir. İşlevler yalnızca dış düzeyde tanımlanabilir ve bu nedenle iç içe geçirilemez. Varsayılan olarak, dış değişkenlere ve aynı ada sahip işlevlere yapılan tüm başvurular aynı nesneye yapılan başvurulardır ve bu, *dış bağlantıya*sahip oldukları anlamına gelir. ( **`static`** Bu davranışı geçersiz kılmak için anahtar sözcüğünü kullanabilirsiniz.)

Dış düzeydeki değişken bildirimleri, değişkenlerin tanımlarından (*bildirimleri tanımlama*) veya başka bir yerde (*başvuru bildirimleri*) tanımlanmış değişkenlere başvurular olabilir.

Değişkeni de Başlatan bir dış değişken bildirimi (örtük veya açık), değişkenin tanımlama bildirimidir. Dış düzeydeki bir tanım, birkaç form alabilir:

- **`static`** Depolama sınıfı belirticisiyle tanımladığınız bir değişken. **`static`** [Başlatma](../c-language/initialization.md)bölümünde açıklandığı gibi değişkeni sabit bir ifadeyle açıkça başlatabilirsiniz. Başlatıcıyı atlarsanız, değişken varsayılan olarak 0 olarak başlatılır. Örneğin, bu iki deyimin her ikisi de değişkenin tanımları olarak kabul edilir `k` .

    ```C
    static int k = 16;
    static int k;
    ```

- Dış düzeyde açıkça başlattığınız bir değişken. Örneğin, `int j = 3;` değişkeninin bir tanımıdır `j` .

Dış düzeydeki (yani, tüm işlevlerin dışında) değişken bildirimlerinde, **`static`** veya **`extern`** depolama sınıfı belirticisini kullanabilir ya da depolama sınıfı belirticisini tamamen atlayabilirsiniz. **`auto`** Ve **`register`** *`storage-class-specifier`* terminallerini dış düzeyde kullanamazsınız.

Dış düzeyde bir değişken tanımlandıktan sonra, çeviri biriminin geri kalanı boyunca görünür olur. Değişken, aynı kaynak dosyasındaki bildiriminden önce görünür değil. Ayrıca, başvuruda bulunan bir bildirim, aşağıda açıklandığı gibi görünür hale belirtilmedikçe, programın diğer kaynak dosyalarında görünmez.

Şunlar ile ilgili kurallar **`static`** :

- Anahtar sözcük olmadan tüm blokların dışında belirtilen değişkenler, **`static`** her zaman değerlerini program boyunca tutar. Belirli bir çeviri birimine erişimleri kısıtlamak için **`static`** anahtar sözcüğünü kullanmanız gerekir. Bu, *iç bağlantı*sağlar. Bir programın tamamına Global hale getirmek için açık depolama sınıfını atlayın veya anahtar sözcüğünü kullanın **`extern`** (sonraki listede bulunan kurallara bakın). Bu, bunlara *dış bağlantı*sağlar. İç ve dış bağlantı Ayrıca [bağlantı](../c-language/linkage.md)bölümünde ele alınmıştır.

- Dış düzeyde bir değişkeni bir program içinde yalnızca bir kez tanımlayabilirsiniz. Farklı bir çeviri biriminde aynı ada ve **`static`** depolama sınıfı belirticisine sahip başka bir değişken tanımlayabilirsiniz. Her **`static`** tanım yalnızca kendi çeviri birimi içinde görünür olduğundan, çakışma oluşmaz. Tek bir çeviri biriminin işlevleri arasında paylaşılması gereken ancak diğer çeviri birimlerine görünmeyen tanımlayıcı adlarını gizlemek için kullanışlı bir yol sağlar.

- **`static`** Depolama sınıfı Belirleyicisi de işlevlerine uygulanabilir. Bir işlev bildirirseniz **`static`** , adının bildirildiği dosyanın dışında görünmez olur.

Kullanım kuralları **`extern`** şunlardır:

- **`extern`** Depolama sınıfı Belirleyicisi, başka bir yerde tanımlı bir değişkene başvuru bildirir. Bir **`extern`** bildirimi başka bir kaynak dosyasında görünür hale getirmek veya bir değişkeni aynı kaynak dosyasındaki tanımından önce görünür hale getirmek için kullanabilirsiniz. Dış düzeyde değişkene bir başvuru bildirdikten sonra değişken, belirtilen başvurunun gerçekleştiği çeviri biriminin geri kalanı boyunca görünür olur.

- **`extern`** Başvurunun geçerli olması için, başvurduğu değişkenin bir kez ve yalnızca bir kez tanımlanması gerekir ve dış düzeyde. Bu tanım ( **`extern`** depolama sınıfı olmadan) programı oluşturan herhangi bir çeviri biriminde olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte dış bildirimler gösterilmektedir:

```C
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

Bu örnekteki iki kaynak dosyasında toplam üç dış bildirim bulunur `i` . Yalnızca bir bildirim "tanımlama bildirimi" dir. Bu bildirim,

```C
int i = 3;
```

genel değişkeni tanımlar `i` ve ilk değeri 3 ile başlatır. `i`Kullanılarak ilk kaynak dosyanın en üstünde "başvuru" bildirimi, **`extern`** genel değişkeni dosyadaki tanımlama bildiriminden önce görünür hale getirir. `i`İkinci kaynak dosyada başvuru bildirimi aynı zamanda değişkeni bu kaynak dosyasında görünür hale getirir. Çeviri biriminde bir değişken için tanımlama örneği sağlanmazsa, derleyici bir

```C
extern int x;
```

Bildirime başvurma ve başvuru tanımlama

```C
int x = 0;
```

programın başka bir çeviri biriminde görünür.

,, Ve olmak üzere üç işlevi de `main` `next` `other` aynı görevi gerçekleştirir: `i` bunları artırıp yazdırırlar. 4, 5 ve 6 değerleri yazdırılır.

`i`Hadya değişkeni başlatılmamışsa, otomatik olarak 0 olarak ayarlanmıştır. Bu durumda, 1, 2 ve 3 değerleri yazdırılmıştır. Değişken başlatma hakkında bilgi için bkz. [başlatma](../c-language/initialization.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama sınıfları](../c-language/c-storage-classes.md)
