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
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152306"
---
# <a name="trigraphs"></a>Trigraflar

C kaynak programlarının kaynak karakter kümesi 7 bit ASCII karakter kümesi içinde yer alır, ancak ISO 646-1983 Sabit Kod Kümesi'nin bir üst kümesidir. Trigraf dizileri, C programlarının yalnızca ISO (Uluslararası Standartlar Enstitüsü) Sabit Kod Kümesi kullanarak yazılmasına izin verir. Trigraflar, derleyicinin karşılık gelen noktalama karakterleriyle değiştirdiği üç karakterli dizilerdir (birbirini izleyen iki soru işareti ile yazılır). Trigrafları, C kaynak dosyalarında bazı noktalama karakterleri için uygun grafik sunumlar içermeyen bir karakter kümesiyle kullanabilirsiniz.

Trigrafları, c ++ 17 dilinden kaldırır. Uygulamaları uygulama tanımlı eşlemeden fiziksel kaynak dosyaya bir parçası olarak trigrafları desteklemeye devam edebilir *temel kaynak karakter kümesi*, ancak bunu yapmak için uygulamaları standart teşvik eder. C ++ 14, olduğu gibi c trigrafları desteklenir

Visual C++ trigraf değiştirme desteklemeye devam eder, ancak varsayılan olarak devre dışıdır. Trigraf değiştirme etkinleştirme hakkında daha fazla bilgi için bkz: [/ZC: trigraphs (Trigrafları değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md).

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
| ??> | } |
| ??- | ~ |

Bir trigraf her zaman tek kaynaklı karakter olarak işlem görür. İlk çevirisi yapılmaz [çeviri aşaması](../preprocessor/phases-of-translation.md)tanıma çıkış karakterlerinin tanınmasından önce dize değişmez değerleri ve karakter sabitlerinde. Yalnızca yukarıdaki tabloda gösterilen dokuz trigraf tanınır. Diğer tüm karakter dizileri çevrilmeden bırakılır.

Karakter kaçış dizisi  **\\?**, trigraf benzeri karakter dizilerinin yanlış yorumlanmasını önler. (Kaçış dizileri hakkında daha fazla bilgi için bkz: [kaçış dizileri](../c-language/escape-sequences.md).) Örneğin, `What??!` dizesini bu `printf` ifadesiyle yazdırmaya çalışırsanız

```C
printf( "What??!\n" );
```

Yazdırılan dize `What|` çünkü `??!` ile değiştirilir bir trigraf sırası `|` karakter. Diziyi düzgün şekilde yazdırmak için ifadeyi aşağıdaki gibi yazın:

```C
printf( "What?\?!\n" );
```

Bu `printf` deyiminde, ikinci soru işaretinin önündeki bir ters eğik çizgi kaçış karakteri, `??!` öğesinin bir trigraf olarak yanlış yorumlanmasını önler.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc:trigraphs (Trigrafları Değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md)<br/>
[C Tanımlayıcıları](../c-language/c-identifiers.md)
