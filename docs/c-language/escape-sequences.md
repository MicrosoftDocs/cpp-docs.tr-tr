---
title: Kaçış dizileri | Microsoft Docs
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
ms.openlocfilehash: 58691bbd4a078056599363028433788d529b266e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068604"
---
# <a name="escape-sequences"></a>Çıkış Sıraları

Karakter birleşimlerine, bir ters eğik çizgi (**\\**) harften veya bir basamak birleşiminden oluşan "kaçış dizileri" adı verilir Yeni satır karakterini, tek tırnak işaretini veya bir karakter sabitindeki diğer belirli karakterleri göstermek için kaçış dizileri kullanmanız gerekir. Kaçış dizisi, tek bir karakter olarak kabul edilir ve bu nedenle karakter sabiti olarak geçerlidir.

Kaçış dizileri, genellikle terminallerde ve yazıcılarda satır başları ve sekme hareketleri gibi eylemleri belirtmek için kullanılır. Bunlar ayrıca yazdırılmayan karakterlerin ve genellikle çift tırnak işareti gibi özel anlamları olan karakterlerin sabit gösterimlerini sağlamak için kullanılır (**"**). Aşağıdaki tabloda, ANSI kaçış dizileri ve neyi gösterdikleri listelenmektedir.

Soru işareti bir ters eğik unutmayın (**\\?**) burada karakter dizisinin yanlış bir trigraf durumlarda bir sabit soru işareti belirtir. Bkz: [Trigrafları](../c-language/trigraphs.md) daha fazla bilgi için.

### <a name="escape-sequences"></a>Çıkış Sıraları

|Çıkış Sırası|Temsil eder|
|---------------------|----------------|
|**\a**|Bell (uyarı)|
|**\b**|Geri Al tuşu|
|**\f**|Form besleme|
|**\n**|Yeni satır|
|**\r**|satır başı|
|**\t**|Yatay sekme|
|**\v**|dikey sekme|
|**\\'**|Tek tırnak işareti|
|**\\"**|Çift tırnak işareti|
|**\\\\**|Ters eğik çizgi|
|**\\?**|Sabit soru işareti|
|**\\** *OOO*|Sekizlik gösterimde ASCII karakteri|
|**\x** *hh*|Onaltılık gösterimde ASCII karakteri|
|**\x** *hhhh*|Bu kaçış dizisi geniş karakter sabitinde veya Unicode dize sabit değerinde kullanılıyorsa onaltılık gösterimde Unicode karakter.<br /><br /> Örneğin, `WCHAR f = L'\x4e00'` veya `WCHAR b[] = L"The Chinese character for one is \x4e00"`.|

**Microsoft'a özgü**

Tabloda görünmeyen bir karakterden önce ters eğik çizgi geliyorsa, derleyici tanımlanmamış karakteri, karakterin kendisi gibi işler. Örneğin, `\c` olarak kabul bir `c`.

**END Microsoft özgü**

Kaçış dizileri, görüntü bağdaştırıcısına grafik olmayan denetim karakterleri göndermenizi sağlar. Örneğin, ESC karakteri (**\033**) bir terminal veya yazıcı için bir denetim komutunun ilk karakteri sıklıkla kullanılır. Bazı kaçış dizileri cihaza özgüdür. Örneğin, dikey sekme ve form besleme kaçış dizileri (**\v** ve **\f**) ekran çıktısını etkilemez, ancak uygun yazıcı işlemlerini gerçekleştirin.

Ters eğik çizgi de kullanabilirsiniz (**\\**) devam karakteri olarak. Ters eğik çizginin hemen arkasından bir yeni satır karakteri (RETURN anahtarına basmaya eşdeğerdir) geliyorsa, derleyici ters eğik çizgiyi ve yeni satır karakterini yoksayar ve sonraki satırı önceki satırın bir parçası olarak değerlendirir. Bu, özellikle tek satırdan uzun olan önişlemci tanımları için kullanışlıdır. Örneğin:

```
#define assert(exp) \
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )
```

## <a name="see-also"></a>Ayrıca Bkz.

[C Karakter Sabitleri](../c-language/c-character-constants.md)