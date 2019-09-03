---
title: '##if, #elif, #else ve #endif yönergeleri (C/C++)'
ms.date: 08/29/2019
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
ms.openlocfilehash: 2b7ed4733dcafda793b9a945c3f40739b52e040a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220346"
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if, #elif, #else ve #endif yönergeleri (C/C++)

**#İf** yönergesi, **#elif**, **#else**ve **#endif** yönergeleriyle bir kaynak dosyanın bölümlerinin derlemesini denetler. Yazdığınız ifadenin ( **#if**sonrasında) sıfır dışında bir değeri varsa, **#if** yönergesini izleyen satır grubu, çeviri biriminde tutulur.

## <a name="grammar"></a>Dilbilgisi

*koşullu* : \
&nbsp;&nbsp;&nbsp;&nbsp;*IF-Part Elif-Parts* <sub>opt</sub> *Else-bölüm* <sub>opt</sub> *endif-çizgi*

*IF-Part* : \
&nbsp;&nbsp;&nbsp;&nbsp;*If-Line metni*

*IF-Line* : \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *sabit ifadesi*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *tanımlayıcı*

*Elif-parçalar* : \
&nbsp;&nbsp;&nbsp;&nbsp;*elif-Line metni*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif-parçaların Elif-Line metni*

*Elif-satır* : \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *sabit ifadesi*

*Else-bölüm* : \
&nbsp;&nbsp;&nbsp;&nbsp;*Else-Line metni*

*Else-Line* : \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-satır* : \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

## <a name="remarks"></a>Açıklamalar

Kaynak dosyadaki her bir **#if** yönergesi, bir kapanış **#endif** yönergesi ile eşleşmelidir. **#İf** ve **#endif** yönergeleri arasında herhangi bir sayıda **#elif** yönerge görünebilir, ancak en fazla bir **#else** yönergesine izin verilir. Varsa **#else** yönergesi, **#endif**önce son yönerge olmalıdır.

**#İf**, **#elif**, **#else**ve **#endif** yönergeleri, diğer **#if** yönergelerinin *metin* bölümlerine iç içe olabilir. Her iç içe **#else**, **#elif**veya **#endif** yönergesi, en yakın önceki **#if** yönergesine aittir.

**#İf** ve **#ifdef**gibi tüm koşullu derleme yönergelerinin, dosyanın sonundan önce bir kapanış **#endif** yönergesiyle eşleşmesi gerekir. Aksi takdirde, bir hata iletisi oluşturulur. Koşullu derleme yönergeleri içerme dosyalarında yer aldığı zaman, aynı koşullara uymalıdır: İçerme dosyasının sonunda eşleşmeyen koşullu derleme yönergeleri olmamalıdır.

Makro değiştirme bir **#elif** komutu izleyen satırın parçası içinde yapılır, bu nedenle bir makro çağrısı *sabit ifadesinde*kullanılabilir.

Önişlemci, daha fazla işleme için verilen *metin* oluşumlarından birini seçer. *Metinde* belirtilen bir blok herhangi bir metin dizisi olabilir. Birden fazla satır kaplayabilirler. Genellikle *metin* , derleyici veya Önişlemci anlamı olan program metinidir.

Önişlemci seçili *metni* işler ve derleyiciye geçirir. *Metin* Önişlemci yönergeleri içeriyorsa, Önişlemci bu yönergeleri yürütür. Yalnızca Önişlemci tarafından seçilen metin blokları derlenir.

Önişlemci, her **#if** veya **#elif** yönergesinden sonra sabit ifadeyi değerlendirerek, doğru (sıfır olmayan) bir sabit ifade bulana kadar tek bir *metin* öğesi seçer. İlişkili **#elif**, **#else**veya **#endif**kadar tüm metinleri (ile **#** başlayan diğer Önişlemci yönergeleri dahil) seçer.

*Sabit ifadenin* tüm oluşumları false ise veya **#elif** yönergesi görünmüyorsa, Önişlemci, **#else** yan tümcesinden sonra metin bloğunu seçer. **#Else** yan tümcesi yoksa ve **#if** bloğundaki *sabit ifadenin* tüm örnekleri false olduğunda, hiçbir metin bloğu seçili değildir.

*Sabit ifade* , bu ek kısıtlamalara sahip bir tamsayı sabiti ifadesidir:

- İfadeler integral türünde olmalıdır ve yalnızca tamsayı sabitlerini, karakter sabitlerini ve **tanımlanmış** işleci içerebilir.

- İfade veya tür atama `sizeof` işleci kullanamaz.

- Hedef ortam, tüm tamsayılar aralıklarını temsil edemiyor olabilir.

- Çeviri tür **int** 'i **Long**ile aynı şekilde ve işaretsiz **int** ile **işaretsiz Long**ile aynı şekilde temsil eder.

- Çevirmen, karakter sabitlerini hedef ortam kümesinden farklı bir kod değerleri kümesine çevirebilir. Hedef ortamın özelliklerini öğrenmek için, limitlerin değerlerini denetlemek üzere bu ortam için oluşturulmuş bir uygulama kullanın *. H* makroları.

- İfade, ortamı sorgulayamaz ve hedef bilgisayardaki uygulama ayrıntılarının yalıtılmış olarak kalması gerekir.

## <a name="preprocessor-operators"></a>Ön işlemci işleçleri

### <a name="defined"></a>tanımlanmış

**Tanımlanan** Önişlemci işleci, aşağıdaki sözdiziminde gösterildiği gibi özel sabit ifadelerde kullanılabilir:

> **tanımlı (** *tanımlayıcı* **)** \
> **tanımlı** *tanımlayıcı*

*Tanımlayıcı* Şu anda tanımlanmışsa, bu sabit ifade true (sıfır dışında) olarak değerlendirilir. Aksi takdirde, koşul false (0) olur. Boş metin olarak tanımlanan bir tanımlayıcı tanımlanmış olarak değerlendirilir. **Tanımlı** işleç bir **#if** ve **#elif** yönergesinde kullanılabilir, ancak başka bir yönerge.

Aşağıdaki örnekte **#if** ve **#endif** yönergeleri üç işlevden birinin derlemesini denetler:

```C
#if defined(CREDIT)
    credit();
#elif defined(DEBIT)
    debit();
#else
    printerror();
#endif
```

İçin `credit` işlev çağrısı, tanımlayıcı `CREDIT` tanımlanmışsa derlenir. Tanımlayıcı `DEBIT` tanımlanmışsa, öğesine `debit` işlev çağrısı derlenir. Tanımlayıcı tanımlanmadıysa, çağrısı `printerror` derlenir. Ve `CREDIT` ,`credit` her ikisi de C 'de ve C++ durumları farklı olduğundan farklı tanımlayıcılardır.

Aşağıdaki örnekteki koşullu derleme deyimleri, adlı `DLEVEL`önceden tanımlanmış bir sembolik sabiti kabul eder.

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

İlk **#if** bloğu, iç içe **#if**, **#else**ve **#endif** yönergelerinin oluşan iki kümesini gösterir. İlk yönergeler kümesi yalnızca `DLEVEL > 5` true ise işlenir. Aksi takdirde, **#else** sonraki deyimler işlenir.

İkinci örnekteki **#elif** ve **#else** yönergeleri, değerini `DLEVEL`temel alarak dört seçenekten birini yapmak için kullanılır. Bu, tanımına bağlı olarak 0, 100 veya 200 olarak ayarlanır. `DLEVEL` `STACK` `DLEVEL` 5 ' ten büyükse, ifade

```C
#elif DLEVEL > 5
display(debugptr);
```

derlenir ve `STACK` tanımlı değildir.

Koşullu derleme için yaygın olarak kullanılan bir kullanım, aynı üst bilgi dosyasının birden çok eklemeleri önlemektir. ' C++De, sınıfların genellikle başlık dosyalarında tanımlanması halinde, bunun gibi yapılar birden çok tanımı engellemek için kullanılabilir:

```cpp
/*  EXAMPLE.H - Example header file  */
#if !defined( EXAMPLE_H )
#define EXAMPLE_H

class Example
{
    //...
};

#endif // !defined( EXAMPLE_H )
```

Yukarıdaki kod, sembolik sabitinin `EXAMPLE_H` tanımlanıp tanımlanmadığını denetler. Bu durumda, dosya zaten dahil edilmiştir ve yeniden işlenmesine gerek kalmaz. Aksi takdirde, sabit `EXAMPLE_H` örnek işaretlemek için tanımlanır. H zaten işlenmiş olarak.

### <a name="__has_include"></a>__has_include

**Visual Studio 2017 sürüm 15,3 ve üzeri**:  Bir kitaplık üstbilgisinin ekleme için kullanılabilir olup olmadığını belirler:

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

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
