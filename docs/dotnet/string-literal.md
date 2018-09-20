---
title: Dize değişmez değeri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- string literals
- strings [C++], string literals
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 41f1996cd4f4caf24ac08d09b05e636cb09f7eed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415271"
---
# <a name="string-literal"></a>Değişmez Dize Değeri

Dize değişmez değerleri işleme, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

C++ dil tasarımı için Yönetilen Uzantılar'yönetilen bir dize sabit değeri dize sabit değeri ile tarafından gösterilirdi bir `S`. Örneğin:

```
String *ps1 = "hello";
String *ps2 = S"goodbye";
```

Önemsiz olmasını yükü iki başlatmaları arasındaki performans ettik, görülen temsili aşağıdaki CIL'i gösterir **ildasm**:

```
// String *ps1 = "hello";
ldsflda    valuetype $ArrayType$0xd61117dd
     modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier)
     '?A0xbdde7aca.unnamed-global-0'

newobj instance void [mscorlib]System.String::.ctor(int8*)
stloc.0

// String *ps2 = S"goodbye";
ldstr      "goodbye"
stloc.0
```

İle bir konferansta tasarruf bir sabit dize öneki hatırlamak (veya öğrenme) olan bir `S`. Yeni sözdiziminde, dize sabit değerleri işlenmesini kullanım bağlam tarafından belirlenen saydam yapılır. `S` Artık ihtiyaç belirtilmelidir.

Peki, biz açıkça gerektiğinde derleyici bir yorumu veya başka bir doğrudan? Bu durumlarda, biz bir açık tür dönüştürme uygulanır. Örneğin:

```
f( safe_cast<String^>("ABC") );
```

Ayrıca, dize sabit değeri artık eşleşen bir `String` standart bir dönüşüm yerine basit bir dönüştürme. Bunu içeren aşırı yüklenmiş işlev kümeleri çözünürlüğünü değiştirir gibi bu değil Kulağa bir `String` ve `const char*` rakip biçimsel parametre olarak. Bir kez çözümlendi çözümleme bir `const char*` örneği artık bayrak olarak belirsiz. Örneğin:

```
ref struct R {
   void f(const char*);
   void f(String^);
};

int main () {
   R r;
   // old syntax: f( const char* );
   // new syntax: error: ambiguous
   r.f("ABC"); 
}
```

Neden bir fark var mı? Adlı birden fazla örneğinin bu yana `f` var. Bu programda çağrısı uygulanacak işlev aşırı yükleme çözümlemesi algoritması gerektirir. Aşırı yükleme işlevi resmi çözümlemesi üç adımdan oluşur.

1. Aday işlevler koleksiyonu. Aday sözcüksel olarak çağrılan işlev adıyla eşleşmesi olan yöntemlerini kapsam içi işlevlerdir. Örneğin, bu yana `f()` örneği çağrılan `R`, tüm işlevler adlı `f` üyesi olmayan `R` (veya kendi temel sınıf hiyerarşisinin) adayı işlevler değildir. Bu örnekte iki deneme işlevi vardır. Bunlar iki üye işlevlerinin `R` adlı `f`. Aday işlev kümesi boşsa, bu aşamada çağrı başarısız olur.

1. Aday işlevler arasındaki önemli işlevler kümesi. Uygun bir işlev çağrısında bağımsız değişken sayısı ve bunların türlerini verilen belirtilen bağımsız değişkenlerle çağrılır biridir. Bizim örneğimizde, aday her iki işlev de uygulanabilir işlevlerdir. Önemli işlev kümesi boşsa, bu aşamada çağrı başarısız olur.

1. Çağrı en iyi eşleşmeyi temsil eden işlevi seçin. Bu bağımsız değişkenleri uygulanabilir işlevi parametre türüne dönüştürmek için uygulanan dönüştürmeler sıralaması tarafından gerçekleştirilir. Bu, bir tek parametreye işlev ile görece sorunsuz, birden çok parametre olduğunda biraz daha karmaşık hale gelir. En iyi eşleşme yoksa bu aşamada çağrı başarısız olur. Diğer bir deyişle, biçimsel parametresinin türü için fiili bağımsız değişkenin türü dönüştürmek için gerekli dönüştürmeleri eşit derecede iyi ise. Çağrısı belirsiz olarak işaretlenir.

Yönetilen Uzantılar, bu çağrı çağrılan çözünürlüğünü `const char*` en iyi eşleşme olarak örneği. Yeni sözdiziminde, eşleştirilecek gerekli dönüştürme `"abc"` için `const char*` ve `String^` artık diğer bir deyişle - eşdeğerdir, eşit derecede iyi - ve çağrının diğer bir deyişle, - hatalı işaretlenir gibi belirsiz.

Bu bize iki sorulara neden olur:

- Gerçek bağımsız değişken türünü nedir `"abc"`?

- Bir tür dönüştürme diğerinden daha iyi olduğunda belirlemeye yönelik algoritma nedir?

Dize sabit değeri türünü `"abc"` olduğu `const char[4]` -olduğunu her dizenin sonunda örtük bir null Sonlandırıcı karakter sabit değeri unutmayın.

Bir hiyerarşide olası tür dönüştürmeleri yerleştirme algoritması, bir tür dönüştürme diğerinden daha iyi olduğunu belirlemek için içerir. İşte benim anlama, hiyerarşisini - bu dönüştürmeler, örtük. Açık tür dönüştürme gösterimini kullanarak geçersiz kılar benzer şekilde hiyerarşi parantez ifade normal İşleç önceliği geçersiz kılar.

1. Tam bir eşleşme en iyisidir. İlginçtir ki, bir değişken tam olarak eşleşmelidir, parametre türüyle tam olarak eşleşmesi gerekmez; Bunu yalnızca yeterince yakın olması gerekir. Bu örnekte ve dil nasıl değiştiğini neler olduğunu anlama anahtarına budur.

1. Bir promosyon standart bir dönüştürme iyidir. Örneğin, yükseltme bir `short int` için bir `int` dönüştürmekten daha iyidir bir `int` içine bir `double`.

1. Standart bir dönüştürme, bir paketleme dönüştürmesi iyidir. Örneğin, dönüştürme bir `int` içine bir `double` kutulama olan daha iyi bir `int` içine bir `Object`.

1. Paketleme dönüştürmesi, örtük bir kullanıcı tanımlı dönüştürme iyidir. Örneğin, kutulama bir `int` içine bir `Object` dönüştürme işlecini uygulamaktan daha iyidir bir `SmallInt` değer sınıfı.

1. Örtük kullanıcı tanımlı dönüştürme hiçbir dönüştürme iyidir. Örtük kullanıcı tanımlı dönüştürme hatası önce son çıkış (ile uyarı biçimsel imzası bir param dizisi ya da üç nokta bu konumda içerebilir) ' dir.

Bu nedenle, tam bir eşleşme mutlaka tam bir eşleşme olmadığını düşünelim ne demektir? Örneğin, `const char[4]` ya da tam olarak eşleşmiyor `const char*` veya `String^`, Örneğimizdeki belirsizliği arasında çakışan iki tam eşleşme.!

Olduğu sürece, tam bir eşleşme Önemsiz dönüşümler içerir. Dört basit dönüştürme uygulanabilir ve yine de tam bir eşleşme uygun ISO C++ altında vardır. Üç lvalue dönüşümleri adlandırılır. Dördüncü bir tür, nitelik dönüştürme çağrılır. Üç lvalue dönüştürmeler bir nitelik dönüştürme gerektiren bir daha iyi tam eşleşme olarak kabul edilir.

Bir lvalue dönüşümü yerel dizi için işaretçi dönüştürme biçimidir. Bu tam olarak ne dahil olan bir `const char[4]` için `const char*`. Bu nedenle, eşleşen `f("abc")` için `f(const char*)` tam eşleşme. İçinde önceki incarnations bizim dilinin bu en iyi eşleşmeyi aslında değildi.

Derleyicinin çağrısı belirsiz olarak işaretlemek için bu nedenle, gerektiren dönüştürülmesi bir `const char[4]` için bir `String^` dönüştürmelerden geçen tam bir eşleşme de. Bu, yeni dil sürümünde tanıtılan değişikliktir. Ve çağrının neden belirsiz olarak budur.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[dize](../windows/string-cpp-component-extensions.md)