---
title: Unicode desteği | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b4f83d4d991b55ec7151db22a9b21424914bd04
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590201"
---
# <a name="support-for-unicode"></a>Unicode Desteği

Unicode temsil edilemeyen yalnızca bir bayt (diğer bir deyişle, bunların çoğu) dahil olmak üzere, tüm karakter kümeleri destekleyen bir özelliğidir. Uluslararası pazar için programlama yapıyorsanız ya da Unicode kullanmanızı öneririz veya [çok baytlı karakter kümesi](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS) veya şekilde değiştirerek bir anahtar ya da derleme programınızı kodlayın.

Bir geniş karakter 2 baytlık çok dilli karakter kodudur. On binlerce teknik simgeleri ve yayımlama özel karakterler dahil olmak üzere dünya çapında, modern işlem alanında kullanılan neredeyse tüm karakterleri içeren karakter olarak tek bir geniş Unicode belirtimine göre gösterilebileceği kodlanmış karakter tarafından UTF-16 kullanılarak. Yalnızca bir geniş karakter olarak temsil edilemeyen karakterler Unicode vekil çifti özelliğini kullanarak bir Unicode çift gösterilebilir. Yaygın olarak kullanılan neredeyse her karakter UTF-16 tek 16 bit geniş karakter olarak temsil edilir çünkü geniş karakterlerin kullanılması uluslararası karakter kümeleriyle programlamayı basitleştirir. Windows için yerel karakter biçimi UTF-16LE (endian için) kullanılarak kodlanmış geniş karakterler var.

Geniş karakterli dize olarak temsil edilen bir `wchar_t[]` dizisi ve tarafından işaret edilen bir `wchar_t*` işaretçi. Herhangi bir ASCII karakterini bir geniş karakter ' % s'Harf L karakter koyarak temsil edilebilir. Örneğin, sonlandırıcı geniş (16-bit) NULL karakteri '\0' L değeridir. Benzer şekilde, herhangi bir ASCII dize sabit değeri geniş karakterli dize sabit değeri olarak ' % s'Harf L ASCII değişmez değeri (L "Merhaba") için koyarak temsil edilebilir.

Genellikle, geniş karakterler, çok baytlı karakter bellekte daha fazla alan alır ancak işlemine daha hızlıdır. Ayrıca, yalnızca bir yerel ayar bir çok baytlı kodlama anında temsil edilebilir, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

MFC çerçevesi boyunca Unicode olarak etkin olan ve MFC Unicode taşınabilir makroları kullanarak aşağıdaki tabloda gösterildiği gibi etkinleştirmesini gerçekleştirir.

## <a name="portable-data-types-in-mfc"></a>MFC içinde taşınabilir veri türleri

|Taşınabilir olmayan veri türü|Bu makro tarafından değiştirildi|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Win32 veri türü) `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32 veri türü) `LPCWSTR`|`LPCTSTR`|

Sınıf `CString` kullanır `_TCHAR` olarak oluşturucularını ve taşıma oluşturucuları ve işleçleri için kolay dönüştürmeler sağlar. Unicode dize işlemlerinin çoğu, temel işlem birimi bir 16-bit karakteri yerine bir 8 bit bayt olması dışında Windows ANSI karakter kümesi işlemek için kullanılan aynı mantığı kullanarak yazılabilir. Çok baytlı karakter kümeleri ile çalışma, aksine, gerekmez (ve kullanmalısınız değil) iki ayrı bayt değilmiş gibi bir Unicode karakter değerlendir. Ancak, bir geniş karakter yedek çifti tarafından temsil edilen tek bir karakter olasılığını ile uğraşmak zorunda. Genel olarak, bir dizenin uzunluğunu karakter sayısını ile aynıdır, dar veya geniş içerdiğinden emin olup olmadığını varsayar kod yazma.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Kendi programımı içinde Unicode etkinleştir](../text/international-enabling.md)

- [Kendi programımı içinde Unicode ve MBCS etkinleştir](../text/internationalization-strategies.md)

- [Uluslararası hale getirilmiş bir program oluşturmak için Unicode kullan](../text/unicode-programming-summary.md)

- [Unicode avantajlarını öğrenin](../text/benefits-of-character-set-portability.md)

- [Kendi programımı için geniş karakter bağımsız değişkenlerini iletebilirsiniz wmain kullanın](../text/support-for-using-wmain.md)

- [Unicode Programlama Özeti bakın](../text/unicode-programming-summary.md)

- [Bayt genişlikli taşınabilirlik için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca bkz.
 [Metin ve Dizeler](../text/text-and-strings-in-visual-cpp.md)  
 [wmain Kullanma Desteği](../text/support-for-using-wmain.md)  