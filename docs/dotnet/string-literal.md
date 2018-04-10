---
title: Dize değişmez değeri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals
- strings [C++], string literals
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd62f85b87473d1371daf2d2fa009d8620e59b57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="string-literal"></a>Değişmez Dize Değeri
Dize değişmez değerleri işlenmesi için Visual C++ C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 C++ dili tasarımı için Yönetilen Uzantılar yönetilen dize sabit değeri dize sabit değeri ile tarafından gösterilirdi bir `S`. Örneğin:  
  
```  
String *ps1 = "hello";  
String *ps2 = S"goodbye";  
```  
  
 Önemsiz olmayan olmasını yükü iki başlatmaları arasındaki performans öyle, görülen gösterimi aşağıdaki CIL gösterir **ildasm**:  
  
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
  
 İle olağanüstü tasarruf sabit değerli bir dize öneki hatırlamak (veya öğrenme) olan bir `S`. Yeni sözdiziminde dize değişmez değerleri işleme kullanım bağlam tarafından belirlenen saydam yapılır. `S` Artık ihtiyaç belirtilmelidir.  
  
 Ne hakkında biz açıkça gereken durumlarda bir yorumlama ya da başka bir derleyiciye doğrudan? Bu durumlarda, açık bir dönüştürme uygulanır. Örneğin:  
  
```  
f( safe_cast<String^>("ABC") );  
```  
  
 Ayrıca, dize sabit değeri şimdi eşleşen bir `String` standart dönüştürme yerine basit bir dönüştürme ile. Çok dahil aşırı yüklenmiş işlevi kümeleri çözünürlüğü değişiklikleri gibi bu ses değil ancak bir `String` ve `const char*` rakip biçimsel parametresi olarak. Bir kez çözümlendi çözümleme bir `const char*` örneği şimdi bayrak olarak belirsiz. Örneğin:  
  
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
  
 Neden bir fark var mıdır? Adlı birden fazla örneğini itibaren `f` var. programında, bu çağrısı uygulanacak işlev aşırı yüklemesi çözümleme algoritması gerektirir. Aşırı yükleme işlevi resmi çözümlemesi üç adımdan oluşur.  
  
1.  Aday işlevler koleksiyonu. Aday işlevler sözcüksel olarak çağrılan işlev adı eşleşen bu kapsamdaki yöntemleridir. Örneğin, bu yana `f()` bir örneği üzerinden çağrılan `R`, tüm işlevleri adlı `f` üyesi olmayan `R` (veya onun temel sınıf hiyerarşisinin) aday işlev değildir. Bizim örneğimizde, iki aday işlev vardır. İki üye işlevlerini bunlar `R` adlı `f`. Aday işlev kümesi boşsa, bu aşamada bir çağrı başarısız olur.  
  
2.  Aday işlevler arasındaki önemli işlevler kümesi. Bir uygulanabilir bağımsız değişken sayısı ve bunların türlerine verilen çağrısında belirtilen bağımsız değişkenlerle çağrılabilen bir işlevdir. Bizim örneğimizde, iki aday işlev de uygulanabilir işlevlerdir. Önemli işlev kümesi boşsa, bu aşamada bir çağrı başarısız olur.  
  
3.  Çağrının en iyi eşleşmeyi temsil işlevi seçin. Bu bağımsız değişkenler uygulanabilir işlevi parametre türüne dönüştürmek için uygulanan dönüştürmeleri sıralaması tarafından gerçekleştirilir. Bu göreceli olarak doğrudan tek bir parametre işleviyle iletme; birden çok parametreler biraz daha karmaşık hale gelir. En iyi eşleşme yoksa bu aşamada bir çağrı başarısız olur. Diğer bir deyişle, değişkenin türü ile gerçek biçimsel parametresi türüne dönüştürmek için gerekli dönüşümleri eşit iyi varsa. Çağrı belirsiz olarak işaretlenir.  
  
 Yönetilen Uzantılar, çağrılan çağrısı çözümleme `const char*` en iyi eşleşme olarak örneği. Eşleştirilecek gerekli dönüştürme yeni sözdiziminde `"abc"` için `const char*` ve `String^` artık başka bir deyişle - eşdeğerdir eşit derecede iyidir - ve çağrı diğer bir deyişle, hatalı - işaretlenir belirsiz olarak.  
  
 Bu bize iki soruya yol açar:  
  
-   Gerçek bağımsız değişkenin türü nedir `"abc"`?  
  
-   Bir tür dönüştürmenin diğerinden daha iyi olduğunda belirlemek için algoritma nedir?  
  
 Değişmez değer dize türü `"abc"` olan `const char[4]` -olduğunu her dizesi sonunda örtük null sonlandırma karakter değişmez değer unutmayın.  
  
 Bir tür dönüştürmenin diğerinden daha iyi olduğunda belirlemek için algoritma olası tür dönüştürmeleri bir hiyerarşiye koymayı içerir. My anlama İşte bu hiyerarşisini - bu dönüşümleri doğal olarak, örtük. Bir açık atama gösterimini kullanarak geçersiz kılar benzer şekilde hiyerarşi parantez ifade olağan İşleç önceliği geçersiz kılar.  
  
1.  Tam bir eşleşme en iyisidir. Şaşırtıcı, tam olarak eşleşmelidir bağımsız değişken için bu parametre türüyle tam olarak eşleşmesi gerekmez; Bunu yalnızca yeterince yakın olması gerekir. Bu örnek ve dil nasıl değiştiğini neler olduğunu anlama anahtarına budur.  
  
2.  Bir yükseltme standart dönüştürmeden daha iyidir. Örneğin, yükseltme bir `short int` için bir `int` dönüştürmekten daha iyidir bir `int` içine bir `double`.  
  
3.  Standart dönüştürme kutulama dönüştürmesinden daha iyidir. Örneğin, dönüştürme bir `int` içine bir `double` kutulama daha iyi olan bir `int` içine bir `Object`.  
  
4.  Kutulama dönüştürmesi örtük bir kullanıcı tarafından tanımlanan dönüştürme iyidir. Örneğin, kutulama bir `int` içine bir `Object` dönüştürme işlecini uygulamaktan daha iyidir bir `SmallInt` değer sınıfı.  
  
5.  Kullanıcı tanımlı bir örtük dönüştürme hiç dönüştürme iyidir. Kullanıcı tanımlı bir örtük dönüştürme son çıkış hata önce (resmi imza param dizisi ya da bu konumda üç nokta içerebilir uyarısıyla) olur.  
  
 Bu nedenle, ne tam bir eşleşme mutlaka tam bir eşleşme olmadığını söylemek anlama geliyor? Örneğin, `const char[4]` ya da tam olarak eşleşmiyor `const char*` veya `String^`, henüz örneğimizde belirsizliği arasında iki çakışan tam eşleşme.!  
  
 Olduğu sürece, tam bir eşleşme birkaç Önemsiz dönüşümler içerir. Uygulanabilir ve hala tam bir eşleşme nitelemek ISO-C++ altında dört basit dönüştürme vardır. Üç lvalue dönüştürmeleri adı verilir. Dördüncü tür nitelik dönüştürmesi adı verilir. Üç lvalue dönüştürmeleri nitelik dönüştürmesi gerektiren olandan daha iyi tam eşleşme olarak kabul edilir.  
  
 Bir lvalue dönüştürme işaretçi için yerel dizi dönüştürme biçimidir. Bu ne eşleştirmelerinde dahil olduğu bir `const char[4]` için `const char*`. Bu nedenle, eşleştirmesinin `f("abc")` için `f(const char*)` tam bir eşleşmedir. İçinde önceki incarnations bizim dilinin en iyi eşleşmeyi aslında, bu.  
  
 Derleyicinin çağrıyı belirsiz olarak bayrak için bu nedenle, gerektiren dönüştürülmesi bir `const char[4]` için bir `String^` Önemsiz dönüştürme aracılığıyla tam bir eşleşme de. Bu yeni dil sürümünde sunulan değişikliktir. Ve çağrının neden bu kadar belirsiz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel dil değişiklikleri (C + +/ CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [Dize](../windows/string-cpp-component-extensions.md)