---
title: "Unicode desteği | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fde7674d30d84385eb1f94f42056a82bfaac99fe
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="support-for-unicode"></a>Unicode Desteği

Unicode temsil edilemeyen yalnızca bir bayt (diğer bir deyişle, bunların çoğu) dahil olmak üzere tüm karakter kümelerini desteklemek için bir özelliğidir. Uluslararası pazar için programlama yapıyorsanız ya da Unicode kullanmanızı öneririz veya [birden çok baytlı karakter kümesi](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS) veya bir anahtarı değiştirerek ya da oluşturabilirsiniz programınızı kodlayın.

Geniş karakter 2-bayt çok dilli karakter kodudur. On binlerce teknik simgeleri ve özel yayımlama karakterleri dahil olmak üzere modern dünyanın her yerinde, bilgi işlem içinde kullanılan neredeyse tüm karakterden oluşan karakterler temsil tek wide olarak Unicode belirtimine göre karakter kodlanmış tarafından UTF-16 kullanma. Yalnızca bir geniş karakter temsil edilemeyen karakterler Unicode yedek çifti özelliğini kullanarak bir Unicode çift gösterilebilir. Geniş karakterler kullanarak, ortak kullanıma neredeyse her karakter UTF-16 tek 16 bit geniş karakter olarak temsil edilir gerektiğinden, uluslararası karakter kümeleri ile programlama kolaylaştırır. Geniş karakterler UTF-16LE (little endian için) kullanılarak kodlanmış Windows yerel karakter biçimini olur.

Bir joker karakter dizesi olarak temsil edilen bir `wchar_t[]` dizi ve işaret ediyor bir `wchar_t*` işaretçi. Herhangi bir ASCII karakter karakterin Harf L ekleyerek geniş karakter olarak gösterilebilir. Örneğin, geniş sonlandırma L '\0' dir (16-bit) **NULL** karakter. Benzer şekilde, herhangi bir ASCII dize sabit değeri bir joker karakter dize sabit değeri ASCII değişmez değeri (L "Hello") L Harfi ekleyerek temsil edilebilir.

Genellikle, geniş karakterler çok baytlı karakter bellekte daha fazla yer kaplar ancak işlem daha hızlıdır. Ayrıca, yalnızca bir yerel ayar aynı anda birden çok baytlı kodlamada temsil, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

MFC çerçevesi Unicode boyunca etkindir ve MFC Unicode taşınabilir makroları kullanarak aşağıdaki tabloda gösterildiği gibi etkinleştirmesini gerçekleştirir.

## <a name="portable-data-types-in-mfc"></a>MFC'deki taşınabilir veri türleri

|Olmayan taşınabilir veri türü|Bu makro tarafından değiştirildi|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Win32 veri türü)`LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32 veri türü)`LPCWSTR`|`LPCTSTR`|

Sınıf `CString` kullanan `_TCHAR` tabanı olarak ve kolay dönüştürmelerde oluşturucular ve işleçler sağlar. Temel işlem birimi bir 8 bit bayt yerine bir 16 bit karakter olması dışında Windows ANSI karakter kümesini işlemek için kullanılan aynı mantığı kullanarak dize işlemlerinin çoğu Unicode için yazılabilir. Birden çok baytlı karakter kümeleri ile çalışma, aksine, gerekmez (ve gerekmemelidir) iki ayrı bayt değilmiş gibi bir Unicode karakter kabul eder. Ancak, geniş karakterler yedek çifti tarafından temsil edilen tek bir karakter olasılığını uğraşmanız zorunda. Genel olarak, dar ya da geniş, onu içeren bir dize uzunluğu karakter sayısı ile aynı olduğunu varsayar kod yazma.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC Unicode ve çok baytlı karakter kümesi (MBCS) desteği kullanın](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Kendi programımı Unicode etkinleştir](../text/international-enabling.md)

- [Unicode ve MBCS kendi programımı etkinleştir](../text/internationalization-strategies.md)

- [Unicode uluslararası bir program oluşturmak için kullanın](../text/unicode-programming-summary.md)

- [Unicode avantajları hakkında bilgi edinin](../text/benefits-of-character-set-portability.md)

- [Kendi programımı joker karakter bağımsız değişkenler geçirebilirsiniz wmain kullanın](../text/support-for-using-wmain.md)

- [Unicode Programlama Özeti bakın](../text/unicode-programming-summary.md)

- [Bayt genişliği taşınabilirliği için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve Dizeler](../text/text-and-strings-in-visual-cpp.md)  
[wmain Kullanma Desteği](../text/support-for-using-wmain.md)  
