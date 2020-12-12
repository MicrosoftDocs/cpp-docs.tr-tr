---
description: 'Daha fazla bilgi edinin: belirteçler ve karakter kümeleri'
title: Belirteçler ve karakter kümeleri
ms.date: 12/10/2019
helpviewer_keywords:
- Tokens (C++)
- Character sets
- basic source character set (C++)
- universal character names
- basic execution character set (C++)
ms.assetid: 379a2af6-6422-425f-8352-ef0bca6c0d74
ms.openlocfilehash: b5a6868f5e4c01772758acaa0e44459e72b16a84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308477"
---
# <a name="tokens-and-character-sets"></a>Belirteçler ve karakter kümeleri

Bir C++ programının metni belirteçlerden ve *boşluklardan* oluşur. Bir belirteç C++ programının derleyicisi için anlamlı olan en küçük öğesidir. C++ ayrıştırıcısı şu tür belirteçleri tanır:

- [Anahtar sözcükler](../cpp/keywords-cpp.md)
- [Tanımlayıcılar](../cpp/identifiers-cpp.md)
- [Sayısal, Boole ve Işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md)
- [Dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md)
- [Kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md)
- [İşleçler](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
- [Noktalama İşaretleri](../cpp/punctuators-cpp.md)

Belirteçler genellikle *boşluk* ile ayrılır ve bu bir veya daha fazla olabilir:

- Boşluklar
- Yatay veya dikey sekmeler
- Yeni satırlar
- Form akışları
- Yorumlar

## <a name="basic-source-character-set"></a>Temel kaynak karakter kümesi

C++ standardı, kaynak dosyalarında kullanılabilecek *temel bir kaynak karakter kümesini* belirtir. Bu küme dışındaki karakterleri göstermek için, bir *evrensel karakter adı* kullanılarak ek karakterler belirtilebilir. MSVC uygulama ek karakterlere izin verir. *Temel kaynak karakter kümesi* , kaynak dosyalarında kullanılabilecek 96 karakterden oluşur. Bu küme boşluk karakterini, yatay sekmeyi, dikey sekmeyi, form akışını ve yeni satır denetim karakterlerini ve bu grafik karakter kümesini içerir:

`a b c d e f g h i j k l m n o p q r s t u v w x y z`

`A B C D E F G H I J K L M N O P Q R S T U V W X Y Z`

`0 1 2 3 4 5 6 7 8 9`

`_ { } [ ] # ( ) < > % : ; . ? * + - / ^ & | ~ ! = , \ " '`

**Microsoft'a Özgü**

MSVC, `$` karakteri temel kaynak karakter kümesinin bir üyesi olarak içerir. MSVC, dosya kodlamaya bağlı olarak kaynak dosyalarında ek bir karakter kümesinin kullanılmasına da izin verir. Varsayılan olarak, Visual Studio varsayılan kod sayfasını kullanarak kaynak dosyalarını depolar. Kaynak dosyaları yerel ayara özgü bir kod sayfası veya bir Unicode kod sayfası kullanılarak kaydedildiğinde, MSVC, temel kaynak karakter kümesinde açıkça izin verilmeyen denetim kodları hariç, kaynak kodunuzda bu kod sayfasının herhangi bir karakterini kullanmanıza izin verir. Örneğin, bir Japonca kod sayfası kullanarak dosyayı kaydederseniz, Japonca karakterleri açıklamalara, tanımlayıcılara veya dize sabit değerlerine yerleştirebilirsiniz. MSVC, geçerli çok baytlı karakterlere veya Unicode kod noktalarına çevrilemeyen karakter dizileri için izin vermez. Derleyici seçeneklerine bağlı olarak, izin verilen tüm karakterler tanımlayıcıda görünmeyebilir. Daha fazla bilgi edinmek için bkz. [Tanımlayıcılar](../cpp/identifiers-cpp.md).

**SON Microsoft 'a özgü**

### <a name="universal-character-names"></a>Evrensel karakter adları

C++ programları temel kaynak karakter kümesinde belirtilenlerden çok daha fazla karakter kullanabileceğinden, *evrensel karakter adlarını* kullanarak bu karakterleri taşınabilir bir şekilde belirtebilirsiniz. Evrensel karakter adı, Unicode kod noktasını temsil eden bir karakter dizisinden oluşur.  Bunlar iki formu alır. `\UNNNNNNNN`U + NNNNNNNN biçimindeki bir Unicode kod noktasını temsil etmek için kullanın; burada, nnnnnnnn sekiz basamaklı onaltılık kod noktası sayısıdır. `\uNNNN`U + 0000NNNN biçimindeki bir Unicode kod noktasını göstermek için dört basamaklı kullanın.

Evrensel karakter adları, tanımlayıcılarında ve dize ve karakter değişmez değerlerinde kullanılabilir. Bir evrensel karakter adı, 0xD800-0xDFFF aralığındaki bir yedek kod noktasını temsil etmek için kullanılamaz. Bunun yerine, istenen kod noktasını kullanın; Derleyici, gerekli tüm yedekleri otomatik olarak oluşturur. Ek kısıtlamalar, tanımlayıcılarda kullanılabilecek evrensel karakter adları için geçerlidir. Daha fazla bilgi için bkz. [tanımlayıcılar](../cpp/identifiers-cpp.md) ve [dize ve karakter sabit değerleri](../cpp/string-and-character-literals-cpp.md).

**Microsoft'a Özgü**

Microsoft C++ derleyicisi, evrensel karakter adı biçimindeki bir karakteri ve değişmez değer formunu birbirinin yerine değerlendirir. Örneğin, evrensel karakter adı formunu kullanarak bir tanımlayıcı bildirebilir ve bunu değişmez bir biçimde kullanabilirsiniz:

```cpp
auto \u30AD = 42; // \u30AD is 'キ'
if (キ == 42) return true; // \u30AD and キ are the same to the compiler
```

Windows panodaki genişletilmiş karakterlerin biçimi, uygulama yerel ayarlarına özgüdür. Bu karakterleri başka bir uygulamadan kodunuza kesip yapıştırmak beklenmeyen karakter kodlamaları ortaya çıkarabilir. Bu, kodunuzda görünür bir neden olmadan hataları ayrıştırmaya neden olabilir. Genişletilmiş karakterleri yapıştırmadan önce kaynak dosya kodlanmasını bir Unicode kod sayfasına ayarlamanızı öneririz. Ayrıca, genişletilmiş karakterler oluşturmak için bir IME veya karakter eşleme uygulaması kullanmanızı öneririz.

**SON Microsoft 'a özgü**

### <a name="execution-character-sets"></a>Yürütme karakter kümeleri

*Yürütme karakter kümeleri* , derlenmiş bir programda görünebilen karakterleri ve dizeleri temsil eder. Bu karakter kümeleri, kaynak dosyada izin verilen tüm karakterlerden ve ayrıca uyarı, geri al, satır başı ve null karakteri temsil eden denetim karakterlerinden oluşur. Yürütme karakter kümesinin yerel ayara özgü bir temsili vardır.
