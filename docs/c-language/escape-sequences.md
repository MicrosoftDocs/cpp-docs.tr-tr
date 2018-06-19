---
title: Kaçış dizilerine | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- "\r escape sequence"
- double backslash
- horizontal-tab 	 escape sequence
- (') single quotation mark
- "bell character \a escape sequence"
- escape sequences
- hexadecimal escape sequence
- carriage returns
- tab 	 escape sequence
- "\f escape sequence"
- quotation marks, single
- "formfeed \f escape sequence"
- "\v escape sequence"
- control character escape sequences
- " symbol in escape sequences"
- octal escape sequence
- escape characters
- "newline character \n escape sequence"
- nongraphic control characters
- question mark, literal
- "\nescape sequence"
- "vertical tab \v escape sequence"
- "\a escape sequence"
- '? symbol'
- '? symbol, escape sequence character'
- "	 escape sequence"
- backspace escape sequence
ms.assetid: 5aef377f-a76c-4d5c-aa04-8308758ad6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd58f7418e2e6a2ca7592c345c5d71729cf8324
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32388834"
---
# <a name="escape-sequences"></a>Çıkış Sıraları
Karakter bir ters eğik çizgi oluşan birleşimler (**\\**) bir harfle veya bir basamak bileşimiyle "kaçış dizilerine." olarak adlandırılır Yeni satır karakterini, tek tırnak işaretini veya bir karakter sabitindeki diğer belirli karakterleri göstermek için kaçış dizileri kullanmanız gerekir. Kaçış dizisi, tek bir karakter olarak kabul edilir ve bu nedenle karakter sabiti olarak geçerlidir.  
  
 Kaçış dizileri, genellikle terminallerde ve yazıcılarda satır başları ve sekme hareketleri gibi eylemleri belirtmek için kullanılır. Bunlar ayrıca yazdırılmayan ve genellikle çift tırnak işareti gibi özel anlamlara sahiptir karakterler değişmez değer gösterimlerini sağlamak için kullanılır (**"**). Aşağıdaki tabloda, ANSI kaçış dizileri ve neyi gösterdikleri listelenmektedir.  
  
 Soru işareti bir ters eğik unutmayın (**\\?**) burada karakter dizisi yanlış yorumlayan trigrafı durumlarda değişmez değer soru işareti belirtir. Bkz: [Trigrafları](../c-language/trigraphs.md) daha fazla bilgi için.  
  
### <a name="escape-sequences"></a>Çıkış Sıraları  
  
|Çıkış Sırası|Temsil eder|  
|---------------------|----------------|  
|**\a**|Bell (uyarı)|  
|**\b**|Geri Al tuşu|  
|**\f**|Form besleme|  
|**\n**|Yeni satır|  
|**\r**|satır başı|  
|**\t**|Yatay sekme|  
|**\v**|Dikey sekme|  
|**\\'**|Tek tırnak işareti|  
|**\\"**|Çift tırnak işareti|  
|**\\\\**|ters eğik çizgi|  
|**\\?**|Sabit soru işareti|  
|**\\** *OOO*|Sekizlik gösterimde ASCII karakteri|  
|**\x** *hh*|Onaltılık gösterimde ASCII karakteri|  
|**\x** *ssss*|Bu kaçış dizisi geniş karakter sabitinde veya Unicode dize sabit değerinde kullanılıyorsa onaltılık gösterimde Unicode karakter.<br /><br /> Örneğin, `WCHAR f = L'\x4e00'` veya `WCHAR b[] = L"The Chinese character for one is \x4e00"`.|  
  
 **Microsoft özel**  
  
 Tabloda görünmeyen bir karakterden önce ters eğik çizgi geliyorsa, derleyici tanımlanmamış karakteri, karakterin kendisi gibi işler. Örneğin, `\c` olarak işlem görür bir `c`.  
  
 **SON Microsoft özel**  
  
 Kaçış dizileri, görüntü bağdaştırıcısına grafik olmayan denetim karakterleri göndermenizi sağlar. Örneğin, ESC karakteri (**\033**) genellikle bir denetim komutu ilk karakteri olarak terminal veya yazıcı için kullanılır. Bazı kaçış dizileri cihaza özgüdür. Örneğin, form besleme ve dikey sekme kaçış dizilerine (**\v** ve **\f**) ekran çıkışına etkilemez, ancak uygun yazıcı işlemleri gerçekleştirme.  
  
 Ters eğik çizgi de kullanabilirsiniz (**\\**) devamlılığı karakteri olarak. Ters eğik çizginin hemen arkasından bir yeni satır karakteri (RETURN anahtarına basmaya eşdeğerdir) geliyorsa, derleyici ters eğik çizgiyi ve yeni satır karakterini yoksayar ve sonraki satırı önceki satırın bir parçası olarak değerlendirir. Bu, özellikle tek satırdan uzun olan önişlemci tanımları için kullanışlıdır. Örneğin:  
  
```  
#define assert(exp) \  
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Karakter Sabitleri](../c-language/c-character-constants.md)