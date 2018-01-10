---
title: Karakter Sets2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- Character sets
- basic source character set (C++)
- universal character names
- basic execution character set (C++)
ms.assetid: 379a2af6-6422-425f-8352-ef0bca6c0d74
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db505809c1fbc2c49e116b9c2f850f6e14dfbdf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="character-sets"></a>Karakter Kümeleri
C++ programı metnin belirli karakter kodlamasını kullanacak kaynak dosyalarında depolanır. C++ standart, kaynak dosyaları için bir temel kaynak karakter kümesi ve derlenmiş dosyalar için bir temel yürütme karakter kümesi belirtir. Visual C++ derlenmiş dosyalar ve ek bir kaynak dosyalarında kullanılacak yerel ayarlara özgü karakter kümesi sağlar.  
  
## <a name="character-sets"></a>Karakter kümeleri  
 C++ Standart belirten bir *temel kaynak karakter kümesi* kaynak dosyalarında kullanılabilir. Bu küme dışındaki karakterleri temsil etmek için ek karakterler kullanarak belirtilebilir bir *evrensel karakter adı*. Derlendiğinde *temel yürütme karakter kümesi* ve *temel yürütme joker karakter kümesi* karakter ve bir programda görünebilir dizeleri temsil eder. Visual C++ uygulaması kaynak kodu ve derlenmiş kod içinde ek karaktere izin verilir.  
  
### <a name="basic-source-character-set"></a>Temel kaynak karakter kümesi  
 *Temel kaynak karakter kümesi* kaynak dosyalarında kullanılan 96 karakterden oluşur. Bu grafik karakter kümesini ve bu küme boşluk karakteri, yatay sekme, dikey sekme, form besleme ve yeni satır denetim karakterleri içerir:  
  
 `a b c d e f g h i j k l m n o p q r s t u v w x y z`  
  
 `A B C D E F G H I J K L M N O P Q R S T U V W X Y Z`  
  
 `0 1 2 3 4 5 6 7 8 9`  
  
 `_ { } [ ] # ( ) < > % : ; . ? * + - / ^ & | ~ ! = , \ " '`  
  
 **Microsoft özel**  
  
 Visual C++ içeren `$` temel kaynak karakter kümesinin bir üyesi olarak karakter. Visual C++ ek ait dosya kodlamasını göre kaynak dosyalarında kullanılacak karakter kümesi de sağlar. Varsayılan olarak, varsayılan kod sayfasını kullanarak Visual Studio kaynak dosyalarını depolar. Kaynak dosyaları, yerel ayarlara özgü kod sayfası veya bir Unicode kod sayfası kullanarak kaydedildiğinde Visual C++ kod sayfasını karakterlerden herhangi birini kaynak kodunuz kullanmanıza olanak sağlayan temel kaynak karakteri açıkça izin denetim kodları dışında ayarlayın. Örneğin, Japonca codepage kullanarak dosyasını kaydederseniz, yorumlar, tanımlayıcılar veya dize değişmez değerleri Japonca karakterler koyabilirsiniz. Visual C++ geçerli birden çok baytlı karakterler veya Unicode kod noktası çevrilemiyor karakter sıralarının izin vermiyor. Derleyici Seçenekleri bağlı olarak, tüm izin verilmeyen karakterler tanımlayıcılarının görünebilir. Daha fazla bilgi için bkz: [tanımlayıcıları](../cpp/identifiers-cpp.md).  
  
 **SON Microsoft özel**  
  
### <a name="universal-character-names"></a>Evrensel karakter adları  
 C++ programları temel kaynak karakter kümesinde belirtilenler daha çok daha fazla karakter kullandığından, bu karakterler taşınabilir bir biçimde kullanarak belirtebilirsiniz *evrensel karakter adları*. Evrensel karakter adları bir Unicode kod noktası temsil eden bir karakter dizisi oluşur.  Bu iki biçimlerde. Kullanım `\UNNNNNNNN` formun nerede NNNNNNNN numarasıdır sekiz basamaklı onaltılık kod noktası U + NNNNNNNN, bir Unicode kod noktası temsil etmek için. Kullanım dört basamaklı `\uNNNN` bir Unicode kod noktası U + 0000NNNN formun temsil etmek için.  
  
 Evrensel karakter adları tanımlayıcıları ve dize ve karakter değişmez değerleri kullanılabilir. Evrensel karakter adları, bir yedek kod noktası 0xD800 0xDFFF aralıktaki temsil etmek için kullanılamaz. Bunun yerine, istenen kod noktası kullanın; Derleyici, tüm gerekli yedekleri otomatik olarak oluşturur. Ek sınırlamalar tanımlayıcılarının kullanılabilir evrensel karakter adları geçerlidir. Daha fazla bilgi için bkz: [tanımlayıcıları](../cpp/identifiers-cpp.md) ve [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md).  
  
 **Microsoft özel**  
  
 Visual C++ derleyicisi evrensel karakter adı ve değişmez değer formunda bir karakter birbirinin yerine değerlendirir. Örneğin, evrensel karakter adı formunu kullanarak tanımlayıcı bildirme ve değişmez değer formunda kullanın:  
  
```cpp  
auto \u30AD = 42; // \u30AD is 'キ'  
if (キ == 42) return true; // \u30AD and キ are the same to the compiler  
  
```  
  
 Genişletilmiş karakterler Windows panosuna biçimi, uygulama yerel ayarları için özeldir. Kesme ve şu karakterleri başka bir uygulama kodunuzdan içine yapıştırma beklenmeyen karakter kodlamaları çıkarabilir. Bu, hiçbir görünür neden kodunuzdaki hataları ayrıştırma neden olabilir. Kaynak dosya bir Unicode kod için genişletilmiş karakterler yapıştırmadan önce kodlama ayarlamanızı öneririz. Genişletilmiş karakterler oluşturmak için IME veya Karakter Eşlem uygulamasını kullanmanızı öneririz.  
  
 **SON Microsoft özel**  
  
### <a name="basic-execution-character-set"></a>Temel yürütme karakter kümesi  
 *Temel yürütme karakter kümesi* ve *temel yürütme joker karakter kümesi* temel kaynak karakter kümesi içindeki tüm karakterleri ve uyarı temsil eden bir denetim karakteri oluşur geri alma, satır başı ve null karakteri.   *Yürütme karakter kümesi* ve *yürütme joker karakter kümesi* temel kümelerinin üst şunlardır. Temel kaynak karakter kümesi dışında uygulama tanımlı kaynak karakterler içerirler. Yürütme karakter kümesi yerel ayarlara özgü gösterimi yok.