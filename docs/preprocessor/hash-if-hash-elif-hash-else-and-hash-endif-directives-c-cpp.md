---
title: '#if, #elif, #else ve #endif yönergeleri (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
ms.openlocfilehash: 90fbab45c6408c30198c2a52a42545718002cc11
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028097"
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if, #elif, #else ve #endif Yönergeleri (C/C++)

**#İf** yönergesi ile **#elif**, **#else**, ve **#endif** yönergesi, kaynak dosyanın bölümlerinin derlenmesini denetler. Yazdığınız ifade (sonra **#if**) hemen ardından gelen satır grubu sıfır dışında bir değere sahip **#if** yönergesi, çeviri biriminde korunur.

## <a name="grammar"></a>Dilbilgisi

*Koşullu* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eğer bölümü elif-parts*<sub>iyileştirilmiş</sub> *else bölümünü*<sub>iyileştirilmiş</sub> *endif satır*

*Eğer bölümü* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if-line metni*

*Eğer satır içi* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if***sabit-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef***tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef***tanımlayıcısı*

*elif-parts* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-line metni*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-parts elif-line metni*

*elif-satırı* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif**  *constant-expression*

*else bölümünü* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*else-line metni*

*başka satır* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*Satır içi endif* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

Her **#if** yönergesi kaynak dosyada bir kapanış eşleştirilmelidir **#endif** yönergesi. Herhangi bir sayıda **#elif** yönergeleri arasında görünebilir **#if** ve **#endif** yönergeleri, ancak en fazla bir **#else** yönergesine izin verilir. **#Else** yönergesi, varsa, olmalıdır öncesindeki son yönerge **#endif**.

**#İf**, **#elif**, **#else**, ve **#endif** yönergelerinin metin bölümlerinde diğer iç içe **#if**yönergeleri. Her iç içe **#else**, **#elif**, veya **#endif** yönergesi ait olduğu en yakın önceki **#if** yönergesi.

Tüm koşullu derleme yönergeleri gibi **#if** ve **#ifdef**, kapanış ile eşleştirilmesi gerekir **#endif** yönergeleri önce dosya sonu; Aksi takdirde bir hata ileti oluşturulur. Koşullu derleme yönergeleri içerdiği dosyaları içerir, aynı koşulları karşılaması gerekir: Hiçbir eşleşmeyen koşullu derleme yönergeleri dahil etme dosyasının sonunda olması gerekir.

Makro değiştirme, izleyen komut satırı bölümünde gerçekleştirilir bir **#elif** makro çağrısı kullanılabilir böylece komut *sabit-ifade*.

Önişlemci belirtilen oluşumlarını birini seçer *metin* daha fazla işleme için. Belirtilen bir blok *metin* metin dizisi olabilir. Bu, birden fazla satırı kaplayabilir. Genellikle *metin* derleyici veya önişlemci için anlamlı olan program metnidir.

Önişlemci seçilen işler *metin* ve derleyiciye gönderir. Varsa *metin* önişlemci yönergeleri, önişlemci yönergeleri Bu tıklatıldığındaki içerir. Yalnızca önişlemci tarafından seçilen metin blokları derlenir.

Tek bir önişlemci seçer *metin* her izleyen sabit ifadeyi değerlendirerek by öğesi **#if** veya **#elif** true (sıfırdan farklı) sabit bulana kadar yönergesi ifade. Tüm metni seçer (ile başlayan diğer önişlemci yönergeleri dahil olmak üzere **#**) kadar ilişkili **#elif**, **#else**, veya **#endif** .

Tüm oluşumlarını *sabit-ifade* yanlış olan veya hiçbir **#elif** yönergesi görünmüyorsa, önişlemci sonra metin bloğunu seçer **#else** yan tümcesi. Varsa **#else** yan tümcesi atlanırsa ve tüm örneklerini *sabit-ifade* içinde **#if** false ise, hiçbir metin bloğu seçilmez.

*Sabit-ifade* bir tamsayı sabit ifadesi şu ilave kısıtlatmalara:

- İfadeler Tamsayı türünde olmalıdır ve yalnızca tamsayı sabitlerini, karakter sabitlerini, içerebilir ve **tanımlanan** işleci.

- İfade kullanamazsınız `sizeof` ya da bir tür atama işleci.

- Hedef ortamın tamsayıların tüm aralıklarını temsil etmesi mümkün olmayabilir.

- Çeviri türünü temsil eden **int** türle aynı **uzun**, ve **işaretsiz int** aynı **işaretsiz uzun**.

- Çevirici karakter sabitlerini hedef ortam kümesinden farklı bir kod değerleri kümesine çevirebilir. Hedef ortamın özelliklerini belirlemek için SINIRLARI makrolarından değerlerini kontrol edin. Hedef ortam için oluşturulmuş bir uygulamada H.

- İfade herhangi bir ortam sorguları gerçekleştirmemelisiniz ve hedef bilgisayardaki uygulama ayrıntılarını karşı yalıtılmış kalmalıdır.

## <a name="defined"></a>tanımlanmış

Önişlemci işleci **tanımlanan** aşağıdaki sözdiziminde gösterildiği gibi özel sabit ifadelerde kullanılabilir:

tanımlanan ( `identifier` )

Tanımlanan `identifier`

Bu sabit ifade true (sıfırdan farklı) ise değerlendirilir *tanımlayıcı* şu anda tanımlanır; Aksi halde koşul false (0). Boş metin olarak kabul edilir olarak tanımlanan bir tanımlayıcı, tanımlanmış. **Tanımlanan** yönergesi olarak kullanılabilir bir **#if** ve **#elif** yönergesi, ancak başka bir yerde kullanılamaz.

Aşağıdaki örnekte, **#if** ve **#endif** yönergeleri üç işlev çağrısından birinin derlemesini denetler:

```C
#if defined(CREDIT)
    credit();
#elif defined(DEBIT)
    debit();
#else
    printerror();
#endif
```

İşlev çağrısı `credit` derlenir tanımlayıcı `CREDIT` tanımlanır. Tanımlayıcı `DEBIT` tanımlanır, işlev çağrısı `debit` derlenir. Hiçbir tanımlayıcı tanımlanmadıysa çağrısı `printerror` derlenir. Unutmayın `CREDIT` ve `credit` kullanımları farklı olduğundan, C ve C++ içindeki farklı tanımlayıcılar olduğunu.

Koşullu derleme deyimleri aşağıdaki örnekte adlı önceden tanımlanmış bir sembolik sabiti varsayarlar `DLEVEL`.

```C
#if DLEVEL > 5
    #define SIGNAL  1
    #if STACKUSE == 1
        #define STACK   200
    #else
        #define STACK   100
    #endif
#else
    #define SIGNAL  0
    #if STACKUSE == 1
        #define STACK   100
    #else
        #define STACK   50
    #endif
#endif
#if DLEVEL == 0
    #define STACK 0
#elif DLEVEL == 1
    #define STACK 100
#elif DLEVEL > 5
    display( debugptr );
#else
    #define STACK 200
#endif
```

İlk **#if** blok iki kümesini gösterir iç içe geçmiş **#if**, **#else**, ve **#endif** yönergeleri. İlk yönergeler kümesi yalnızca işlenen `DLEVEL > 5` geçerlidir. Aksi takdirde, ardından gelen ifadeler **#else** işlenir.

**#Elif** ve **#else** değerini temel alarak dört seçimden birini yapmak için yönergeleri ikinci örnekte kullanılan `DLEVEL`. Sabit `STACK` 0, 100 veya 200, tanımını bağlı olarak ayarlanmış `DLEVEL`. Varsa `DLEVEL` 5 sonra deyimi büyük

```C
#elif DLEVEL > 5
display(debugptr);
```

derlenir ve `STACK` tanımlı değil.

Koşullu derleme için yaygın bir kullanımı, aynı üstbilgi dosyasına birden çok ekleme yapılmasının engellemektir. Burada sınıflar genellikle üstbilgi dosyalarında tanımlanır, C++'da, aşağıdaki gibi yapıları birden çok tanımı önlemek için kullanılabilir:

```cpp
/*  EXAMPLE.H - Example header file  */
#if !defined( EXAMPLE_H )
#define EXAMPLE_H

class Example
{
...
};

#endif // !defined( EXAMPLE_H )
```

Yukarıdaki kod olup olmadığını denetler. sembolik sabitin `EXAMPLE_H` tanımlanır. Bu durumda, dosya zaten eklenmiştir ve işlenmez. Değilse, sabiti `EXAMPLE_H` örnek işaretlemek üzere tanımlanır. H işlendi olarak.

## <a name="hasinclude"></a>__has_include

**Visual Studio 2017 sürüm 15.3 ve üzeri**:  Bir kitaplığı üstbilgi ekleme için kullanılabilir olup olmadığını belirler:

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)