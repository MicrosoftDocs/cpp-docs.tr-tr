---
title: Karakter Kümeleri
ms.date: 04/12/2018
helpviewer_keywords:
- Character sets
- basic source character set (C++)
- universal character names
- basic execution character set (C++)
ms.assetid: 379a2af6-6422-425f-8352-ef0bca6c0d74
ms.openlocfilehash: 5282d5b227e71c0ba6f822a9534a8a31cbd86db9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331239"
---
# <a name="character-sets"></a>Karakter Kümeleri

Bir C++ programının metnin belirli karakter kodlaması kullanan kaynak dosyalarında depolanır. C++ standartı, kaynak dosyaları için bir temel kaynak karakter kümesi ve derlenmiş dosyalar için bir temel yürütme karakter kümesini belirtir. Visual C++, ek kaynak dosyalarında kullanılacak yerel ayara özgü karakter kümesi sağlar ve derlenmiş dosyalar.

## <a name="character-sets"></a>Karakter kümesi

C++ standardı belirtir bir *temel kaynak karakter kümesi* kaynak dosyalarında kullanılabilir. Bu küme dışındaki karakterleri temsil etmek için ek karakterler kullanarak belirtilebilir bir *evrensel karakter adı*. Derlendiğinde *temel yürütme karakter kümesi* ve *temel yürütme joker karakter kümesi* karakter ve bir programda görünebilir dizeleri temsil eder. Visual C++ uygulama kaynak kodu ve derlenmiş kod içinde ek karaktere izin verilir.

### <a name="basic-source-character-set"></a>Temel kaynak karakter kümesi

*Temel kaynak karakter kümesi* kaynak dosyalarında kullanılan 96 karakterden oluşur. Bu grafik karakter kümesini ve bu boşluk karakterini, yatay sekme, dikey sekme, form besleme ve yeni satır denetim karakterleri içerir:

`a b c d e f g h i j k l m n o p q r s t u v w x y z`

`A B C D E F G H I J K L M N O P Q R S T U V W X Y Z`

`0 1 2 3 4 5 6 7 8 9`

`_ { } [ ] # ( ) < > % : ; . ? * + - / ^ & | ~ ! = , \ " '`

**Microsoft'a özgü**

Visual C++ içerir `$` temel kaynak karakter kümesi üyesi olarak karakter. Visual C++, ek bir dosya kodlamasına göre kaynak dosyalarında kullanılacak karakter kümesi de sağlar. Varsayılan olarak, Visual Studio varsayılan kod sayfasını kullanarak kaynak dosyalarını depolar. Kaynak dosyaları, yerel ayara özgü bir kod ya da bir Unicode kod kullanarak kaydedildiğinde Visual C++ kod sayfasını karakterlerden herhangi birini kaynak kodunuzu kullanmanıza olanak tanır temel kaynak karakter açıkça izin verilen denetim kodları dışında ayarlayın. Örneğin, Japonca bir kod kullanarak dosyayı kaydederseniz, yorumlar, tanımlayıcı veya dize değişmez değerleri Japonca karakterler koyabilirsiniz. Visual C++ geçerli çok baytlı karakter veya Unicode kod noktaları çevrilemez karakter sıraları izin vermez. Derleyici seçeneklerine bağlı olarak, tüm izin verilmeyen karakterler tanımlayıcıları görünebilir. Daha fazla bilgi için [tanımlayıcıları](../cpp/identifiers-cpp.md).

**END Microsoft özgü**

### <a name="universal-character-names"></a>Evrensel karakter adları

C++ programları temel kaynak karakter kümesinde belirtilenlerden daha çok daha fazla karakter kullandığından, bu karakterler taşınabilir bir biçimde kullanarak belirtebilirsiniz *evrensel karakter adları*. Evrensel karakter adı bir Unicode kod noktasını temsil eden bir karakter dizisi oluşur.  Bu iki biçimlerde. Kullanım `\UNNNNNNNN` NNNNNNNN sekiz basamaklı onaltılık kod noktası numarası olduğu form U + NNNNNNNN, bir Unicode kod noktasını temsil etmek için. Kullanım dört basamaklı `\uNNNN` bir Unicode kod noktası U + 0000NNNN formun temsil etmek için.

Evrensel karakter adları, dize ve karakter değişmez değerleri ve tanımlayıcıları de kullanılabilir. Evrensel karakter adı, bir yedek kod noktası aralığı 0xD800 0xDFFF içinde temsil etmek için kullanılamaz. Bunun yerine, istenen kod noktası kullanın. Derleyici, tüm gerekli yedekleri otomatik olarak oluşturur. Tanımlayıcılar kullanılabilir evrensel karakter adları ek kısıtlamalar uygulanır. Daha fazla bilgi için [tanımlayıcıları](../cpp/identifiers-cpp.md) ve [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md).

**Microsoft'a özgü**

Visual C++ derleyicisi evrensel karakter adı ve değişmez değer formunda bir karakteri terimleri değerlendirir. Örneğin, evrensel karakter adı biçimi kullanarak bir tanımlayıcı bildirmek ve değişmez değer biçiminde kullanın:

```cpp
auto \u30AD = 42; // \u30AD is 'キ'
if (キ == 42) return true; // \u30AD and キ are the same to the compiler
```

Uygulama yerel ayarlarını belirli Windows panosuna Genişletilmiş karakter biçimidir. Kesme ve şu karakterleri kodunuzla başka bir uygulamadan yapıştırma beklenmeyen karakter kodlamaları neden olabilir. Bu, kodunuzun içinde görünür bir neden olan hataları Ayrıştırmada neden olabilir. Kaynak dosyası bir Unicode kod için Genişletilmiş karakter yapıştırmadan önce kodlamanızın ayarlamanızı öneririz. Genişletilmiş karakterler oluşturulacak IME veya karakter harita uygulaması kullanmanızı öneririz.

**END Microsoft özgü**

### <a name="basic-execution-character-set"></a>Temel yürütme karakter kümesi

*Temel yürütme karakter kümesi* ve *temel yürütme joker karakter kümesi* temel kaynak karakter kümesindeki tüm karakterleri ve uyarı temsil eden denetim karakterleri oluşur Geri Al, satır başı ve null karakteri. *Yürütme karakter kümesi* ve *yürütme geniş karakter kümesi* olan temel ayarlar üst kümeleridir. Uygulama tanımlı kaynak karakter temel kaynak karakter kümesi dışında içerirler. Yürütme karakter kümesi, bir yerel ayara özgü gösterimi yok.