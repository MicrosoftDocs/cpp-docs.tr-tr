---
description: 'Daha fazla bilgi edinin: kaçış dizileri'
title: Çıkış Sıraları
ms.date: 11/04/2016
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
- "form feed \f escape sequence"
- "\v escape sequence"
- control character escape sequences
- " symbol in escape sequences"
- octal escape sequence
- escape characters
- "newline character \n escape sequence"
- nongraphic control characters
- question mark, literal
- "\n escape sequence"
- "vertical tab \v escape sequence"
- "\a escape sequence"
- '? symbol'
- '? symbol, escape sequence character'
- "	 escape sequence"
- backspace escape sequence
ms.assetid: 5aef377f-a76c-4d5c-aa04-8308758ad6a8
ms.openlocfilehash: 860c9b490a0d67f27da612f113cf6233f32b7188
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196548"
---
# <a name="escape-sequences"></a>Çıkış Sıraları

Bir ters eğik çizgi () ve **\\** ardından bir harf ile veya bir basamak birleşimiyle oluşan karakter bileşimleri "kaçış dizileri" olarak adlandırılır. Yeni satır karakterini, tek tırnak işaretini veya bir karakter sabitindeki diğer belirli karakterleri göstermek için kaçış dizileri kullanmanız gerekir. Kaçış dizisi, tek bir karakter olarak kabul edilir ve bu nedenle karakter sabiti olarak geçerlidir.

Kaçış dizileri, genellikle terminallerde ve yazıcılarda satır başları ve sekme hareketleri gibi eylemleri belirtmek için kullanılır. Bunlar, genellikle çift tırnak işareti (**"**) gibi özel anlamlara sahip yazdırılmayan karakterlerin ve karakterlerin sabit gösterimlerini sağlamak için de kullanılır. Aşağıdaki tabloda, ANSI kaçış dizileri ve neyi gösterdikleri listelenmektedir.

Önünde ters eğik çizgi (**\\ ?**) olan soru işaretinin, karakter sırasının bir trigraf olarak yanlış yorumlanacağı durumlarda sabit bir soru işareti belirttiğinden emin olun. Daha fazla bilgi için bkz. [Trigraf](../c-language/trigraphs.md) .

### <a name="escape-sequences"></a>Çıkış Sıraları

|Çıkış Sırası|Temsil eder|
|---------------------|----------------|
|**\**|Bell (uyarı)|
|**\b**|Geri Al tuşu|
|**\f**|Form akışı|
|**\n**|Yeni satır|
|**\r**|Satır başı|
|**t**|Yatay sekme|
|**\v**|Dikey sekme|
|**\\'**|Tek tırnak işareti|
|**\\"**|Çift tırnak işareti|
|**\\\\**|Sola|
|**\\?**|Sabit soru işareti|
|**\\***ooo*|Sekizlik gösterimde ASCII karakteri|
|**\x** *HH*|Onaltılık gösterimde ASCII karakteri|
|**\x** *sshh*|Bu kaçış dizisi geniş karakter sabitinde veya Unicode dize sabit değerinde kullanılıyorsa onaltılık gösterimde Unicode karakter.<br /><br /> Örneğin `WCHAR f = L'\x4e00'` veya `WCHAR b[] = L"The Chinese character for one is \x4e00"` olabilir.|

**Microsoft'a Özgü**

Tabloda görünmeyen bir karakterden önce ters eğik çizgi geliyorsa, derleyici tanımlanmamış karakteri, karakterin kendisi gibi işler. Örneğin, `\c` olarak değerlendirilir `c` .

**SON Microsoft 'a özgü**

Kaçış dizileri, görüntü bağdaştırıcısına grafik olmayan denetim karakterleri göndermenizi sağlar. Örneğin, ESC karakteri (**\ 033**), genellikle bir Terminal veya yazıcı için bir denetim komutunun ilk karakteri olarak kullanılır. Bazı kaçış dizileri cihaza özgüdür. Örneğin, dikey sekme ve form besleme kaçış dizileri (**\v** ve **\f**) ekran çıkışını etkilemez, ancak uygun yazıcı işlemlerini gerçekleştirir.

Ayrıca, **\\** bir devam karakteri olarak ters eğik çizgi () kullanabilirsiniz. Ters eğik çizginin hemen arkasından bir yeni satır karakteri (RETURN anahtarına basmaya eşdeğerdir) geliyorsa, derleyici ters eğik çizgiyi ve yeni satır karakterini yoksayar ve sonraki satırı önceki satırın bir parçası olarak değerlendirir. Bu, özellikle tek satırdan uzun olan önişlemci tanımları için kullanışlıdır. Örneğin:

```
#define assert(exp) \
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )
```

## <a name="see-also"></a>Ayrıca bkz.

[C karakter sabitleri](../c-language/c-character-constants.md)
