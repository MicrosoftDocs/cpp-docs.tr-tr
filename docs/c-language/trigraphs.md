---
title: Trigraflar
ms.date: 11/04/2016
helpviewer_keywords:
- ??) trigraph
- ??- trigraph
- question mark, in trigraphs
- ??= trigraph
- ?? trigraph
- ??< trigraph
- ??/ trigraph
- trigraphs
- '? symbol, trigraph'
- ??> trigraph
- ??! trigraph
- ??' trigraph
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
ms.openlocfilehash: 001eb90b5cb4dda933571fd053598995d3ef613e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345322"
---
# <a name="trigraphs"></a>Trigraflar

C kaynak programlarının kaynak karakter kümesi 7 bit ASCII karakter kümesi içinde yer alır, ancak ISO 646-1983 Sabit Kod Kümesi'nin bir üst kümesidir. Trigraf dizileri, C programlarının yalnızca ISO (Uluslararası Standartlar Enstitüsü) Sabit Kod Kümesi kullanarak yazılmasına izin verir. Trigraflar, derleyicinin karşılık gelen noktalama karakterleriyle değiştirdiği üç karakterli dizilerdir (birbirini izleyen iki soru işareti ile yazılır). Trigrafları, C kaynak dosyalarında bazı noktalama karakterleri için uygun grafik sunumlar içermeyen bir karakter kümesiyle kullanabilirsiniz.

C++ 17, dilin üç aylık grafiğini kaldırır. Uygulamalar, fiziksel kaynak dosyasından *temel kaynak karakter kümesine*uygulama tanımlı eşlemenin bir parçası olarak üç aylık grafikleri desteklemeye devam edebilir, ancak standart uygulamaları bunu yapamıyor gibi teşvik eder. C++ 14 aracılığıyla trigraf C 'de olduğu gibi desteklenir.

Visual C++ Üçlü grafik değişimini desteklemeye devam eder, ancak varsayılan olarak devre dışıdır. Üçlü grafik değişimini etkinleştirme hakkında daha fazla bilgi için bkz. [/Zc: trigraf (Trigraf değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md).

Aşağıdaki tablo, dokuz trigraf dizisini göstermektedir. Noktalama karakterlerinin kaynak dosyasında ilk sütunda görünen tüm örneklerinin yerine karşılık gelen karakterler ikinci sütuna konur.

### <a name="trigraph-sequences"></a>Trigraf Dizileri

| Trigraf | Noktalama Karakteri |
|----------|-----------------------|
| ??= | # |
| ??( | \[ |
| ??/ | \\ |
| ??) | ] |
| ??' | ^ |
| ??\< | { |
| ??! | &#124; |
| ?? > | } |
| ??- | ~ |

Bir trigraf her zaman tek kaynaklı karakter olarak işlem görür. Trigraf çevirisi ilk [çeviri aşamasında](../preprocessor/phases-of-translation.md), dize sabit değerlerinde ve karakter sabitlerinde kaçış karakterlerinin tanınmadan önce gerçekleşir. Yalnızca yukarıdaki tabloda gösterilen dokuz trigraf tanınır. Diğer tüm karakter dizileri çevrilmeden bırakılır.

Karakter kaçış sırası, ** \\?**, trigraf benzeri karakter sıralarının yanlış yorumlamasını önler. (Kaçış dizileri hakkında daha fazla bilgi için bkz. [kaçış dizileri](../c-language/escape-sequences.md).) Örneğin, dizeyi `What??!` this `printf` ifadesiyle yazdırmaya çalışırsanız

```C
printf( "What??!\n" );
```

yazdırılan `What|` `??!` dize, `|` karakteri ile değiştirilmiş bir trigraf sırasıdır. Diziyi düzgün şekilde yazdırmak için ifadeyi aşağıdaki gibi yazın:

```C
printf( "What?\?!\n" );
```

Bu `printf` deyiminde, ikinci soru işaretinin önündeki bir ters eğik çizgi kaçış karakteri, `??!` öğesinin bir trigraf olarak yanlış yorumlanmasını önler.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc:trigraphs (Trigrafları Değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md)<br/>
[C Tanımlayıcıları](../c-language/c-identifiers.md)
