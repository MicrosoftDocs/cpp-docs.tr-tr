---
title: C tanımlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- identifiers, C
- naming identifiers
- identifiers
- symbols, C identifiers
- identifiers, case sensitivity
- symbols, case sensitivity
ms.assetid: d02edbbc-85a0-4118-997b-84ee6b972eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cca0381392a1f7c2f227c3296597dc3c614ae0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-identifiers"></a>C Tanımlayıcıları
"Tanımlayıcıları" veya "simgelerini" sağladığınız değişkenleri, türleri, İşlevler ve etiketleri programınızdaki adlardır. Yazım denetimi ve herhangi bir anahtar sözcük durumundan tanımlayıcı adları farklı olmalıdır. Anahtar sözcükler (C ya da Microsoft) tanımlayıcı olarak kullanamazsınız; Bunlar, özel kullanım için ayrılmıştır. Tanımlayıcı değişkeni, tür veya işlev bildiriminde belirterek oluşturun. Bu örnekte, `result` bir tamsayı değişken için bir tanımlayıcıdır ve `main` ve `printf` işlevleri için tanımlayıcı adları.  
  
```  
#include <stdio.h>  
  
int main()  
{  
    int result;  
  
    if ( result != 0 )  
        printf_s( "Bad file handle\n" );  
}  
```  
  
 Bildirilen sonra ilişkili değere başvurmak için daha sonra program deyimlerinde tanımlayıcısı kullanabilirsiniz.  
  
 Bir bildirim etiketi tanımlayıcısından, özel bir tür kullanılabilir `goto` deyimleri. (Bildirimler bölümünde açıklanmıştır [bildirimler ve türler](../c-language/declarations-and-types.md) deyimi etiketler bölümünde açıklanmıştır [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md).)  
  
## <a name="syntax"></a>Sözdizimi  
 *tanımlayıcı*:  
 *sayı olmayan*  
  
 *tanımlayıcı sayı olmayan*  
  
 *tanımlayıcı basamak*  
  
 `nondigit`: biri  
 **_ b c d e f g h ı j k l m n o p q r s t u v z y x w**  
  
 **BİR B C D E F G H I J K L M N O P Q R S T U V W Y Z X**  
  
 `digit`: biri  
 **0 1 2 3 4 5 6 7 8 9**  
  
 Tanımlayıcı adı ilk karakteri olmalıdır bir `nondigit` (diğer bir deyişle, ilk karakteri bir alt çizgi veya bir büyük veya küçük harf olmalıdır). Bir dış kimliğinin adında altı önemli karakterler ve 31 (işlev içinde) iç tanımlayıcı adları için ANSI sağlar. Dış tanımlayıcıları (olanları genel kapsamda bildirilen veya depolama sınıfı ile bildirilen `extern`) tanımlayıcıları linkers gibi diğer yazılım tarafından işlenmek üzere olduğundan ek adlandırma kısıtlamaları tabi olabilir.  
  
 **Microsoft özel**  
  
 Dış tanımlayıcı adları 6 önemli karakterler ve 31 (işlev içinde) iç tanımlayıcı adları için ANSI olanak sağlasa da, Microsoft C Derleyici bir iç veya dış tanımlayıcı adı 247 karakterden oluşabilir. ANSI uyumluluğu ile ilgili değilse, bu varsayılan /H kullanarak küçük veya büyük bir sayıya değiştirebilirsiniz (Dış adların uzunluğunu kısıtla) seçeneği.  
  
 **SON Microsoft özel**  
  
 C derleyicisi farklı karakter olacak şekilde büyük ve küçük harfler göz önünde bulundurur. "Duyarlılık, bu durumda" olarak adlandırılan bu özellik, aynı olan ayrı tanımlayıcıları oluşturmanızı sağlar ancak farklı durumlarda bir veya daha fazla harf için yazım denetimi. Örneğin, her biri aşağıdaki tanımlayıcıları benzersiz içerir:  
  
```  
add  
ADD  
Add  
aDD  
```  
  
 **Microsoft özel**  
  
 Adları büyük harfle tarafından izlenen bir alt çizgi veya iki alt çizgi ile başlayan tanımlayıcıları için seçmeyin. ANSI C standardı derleyici kullanım için ayrılmış olması için bu karakter bileşimleri ile başlayan tanımlayıcı adları izin verir. Dosya düzeyinde kapsamlı tanımlayıcıları da bir alt çizgi ve küçük harf ilk iki harf adlı olmalıdır değil. Ayrıca bu karakterleri ile başlayan tanımlayıcı adları ayrılmıştır. Microsoft, kurala göre makro adları ve Microsoft'a özgü anahtar sözcüğü adları için çift alt çizgi başlamak için bir alt çizgi ve bir büyük harf kullanır. Adlandırma çakışmaları önlemek için her zaman bir veya iki alt çizgi ile başlamayan tanımlayıcı adları veya bir büyük harf tarafından izlenen bir alt çizgi ile başlayan adlar seçin.  
  
 **SON Microsoft özel**  
  
 ANSI veya Microsoft adlandırma kısıtlamaları uygun geçerli tanımlayıcıları örnekleri verilmiştir:  
  
```  
j  
count  
temp1  
top_of_page  
skip12  
LastNum  
```  
  
 **Microsoft özel**  
  
 Kaynak dosyalardaki tanımlayıcıları varsayılan olarak büyük küçük harfe duyarlı olsa da, nesne dosyaları sembolleri değildir. Microsoft C tanımlayıcıları derleme birimindeki büyük küçük harfe duyarlı olarak değerlendirir.  
  
 Microsoft bağlayıcı büyük küçük harfe duyarlıdır. Tutarlı bir şekilde çalışması göre tüm tanımlayıcılar belirtmeniz gerekir.  
  
 "Kaynak karakter kümesi" kaynak dosyalarında görünebilir yasal karakter kümesidir. Microsoft C için standart ASCII karakter kümesi kaynağı kümesidir. Yürütme karakter kümesi ve kaynak karakter kümesi kaçış sıraları olarak kullanılan ASCII karakterler içeriyor. Bkz: [karakter sabitleri](../c-language/c-character-constants.md) yürütme karakter hakkında bilgi için ayarlayın.  
  
 **SON Microsoft özel**  
  
 Tanımlayıcı "adı verilir program ve"aynı adlı başka bir kapsamda aynı tanımlayıcısına başvuruyor olup olmadığını belirleyen bağlantı,"bölgesi kapsamına" vardır. Bu konularda açıklanmıştır [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Öğeleri](../c-language/elements-of-c.md)