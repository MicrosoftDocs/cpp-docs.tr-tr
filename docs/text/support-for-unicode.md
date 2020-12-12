---
description: 'Hakkında daha fazla bilgi edinin: Unicode desteği'
title: Unicode desteği
ms.date: 01/09/2018
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.openlocfilehash: 3226f488afc8d9899777ac0b717dd012fec2cc3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335760"
---
# <a name="support-for-unicode"></a>Unicode desteği

Unicode, tek bir bayt içinde temsil edileyenler dahil olmak üzere tüm karakter kümelerini desteklemeye yönelik bir belirtimdir.  Uluslararası bir pazar için programlama yapıyorsanız, Unicode veya [çok baytlı karakter kümesi](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS) kullanmanızı öneririz. Ya da programınızı bir anahtarı değiştirerek derlemenize olanak sağlayacak şekilde kodlayabilirsiniz.

Geniş bir karakter 2 baytlık çok dilli karakter kodudur. Tüm dünyada modern bilgi işlem için kullanılan neredeyse tüm karakterlerden oluşan on binlerce karakter, teknik semboller ve özel yayımlama karakterleri de dahil olmak üzere Unicode belirtimine göre, UTF-16 kullanılarak kodlanmış tek bir geniş karakter olarak temsil edilebilir. Yalnızca bir geniş karakter içinde gösterilemeyen karakterler Unicode vekil çifti özelliği kullanılarak Unicode çiftinde gösterilebilir. Yaygın olarak kullanılan her karakter tek bir 16 bit geniş karakterde UTF-16 olarak temsil edildiğinden, geniş karakterlerin kullanılması uluslararası karakter kümeleriyle programlamayı basitleştirir. UTF-16LE (little-endian için) kullanılarak kodlanan geniş karakterler Windows için yerel karakter biçimidir.

Geniş karakterli bir dize, dizi olarak temsil edilir `wchar_t[]` ve bir işaretçi tarafından işaret edilir `wchar_t*` . Herhangi bir ASCII karakteri, z harfine harfe önek eklenerek geniş bir karakter olarak gösterilebilir. Örneğin, L ' \ 0 ', Sonlandırıcı geniş (16 bit) NULL karakterdir. Benzer şekilde, herhangi bir ASCII dize değişmez değeri, L harfinin ASCII değişmez değerine (L "Hello") eklenerek geniş karakterli bir dize sabit değeri olarak temsil edilebilir.

Genellikle, geniş karakterler çok baytlı karakterlerden çok daha fazla alan kaplar, ancak işlemek daha hızlıdır. Ayrıca, çok baytlı kodlamada yalnızca bir yerel ayar gösterilebilir, ancak dünyanın tüm karakter kümeleri aynı anda Unicode temsili tarafından temsil edilir.

MFC çerçevesi genelinde Unicode özellikli etkindir ve MFC, aşağıdaki tabloda gösterildiği gibi taşınabilir makroları kullanarak Unicode 'U etkinleştirir.

## <a name="portable-data-types-in-mfc"></a>MFC 'de taşınabilir veri türleri

|Taşınabilir olmayan veri türü|Bu makro ile değiştirilmiştir|
|-----------------------------|----------------------------|
|**`char`**, **`wchar_t`**|`_TCHAR`|
|**`char*`**, `LPSTR` (Win32 veri türü), `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32 veri türü), `LPCWSTR`|`LPCTSTR`|

Sınıfı `CString` `_TCHAR` , temeli olarak kullanılır ve kolay dönüştürmeler için oluşturucular ve işleçler sağlar. Unicode için dize işlemlerinin çoğu, Windows ANSI karakter kümesini işlemek için kullanılan mantığla kullanılarak yazılabilir, ancak temel işlem birimi 8 bitlik bir bayt yerine 16 bitlik bir karakter olabilir. Çok baytlı karakter kümeleriyle çalışmaktan farklı olarak, bir Unicode karakteri iki farklı bayt gibi kabul etmeniz gerekmez (ve kullanmamalısınız). Bununla birlikte, tek bir karakterin bir vekil çift karakter çifti tarafından temsil edildiği olasılığa karşı uğraşmanız gerekir. Genel olarak, bir dizenin uzunluğunu, dar veya geniş olan karakterlerin sayısı ile aynı olduğunu varsayan bir kod yazın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC Unicode ve çok baytlı karakter kümesi (MBCS) desteğini kullanın](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Programmda Unicode 'U etkinleştir](../text/international-enabling.md)

- [Programmda hem Unicode hem de MBCS 'yi etkinleştir](../text/internationalization-strategies.md)

- [Uluslararası bir program oluşturmak için Unicode kullanın](../text/unicode-programming-summary.md)

- [Unicode 'un avantajlarını öğrenin](../text/benefits-of-character-set-portability.md)

- [Çok karakterli bağımsız değişkenleri programımı ile geçirebilmem için wmain kullanın](../text/support-for-using-wmain.md)

- [Bkz. Unicode Programlama Özeti](../text/unicode-programming-summary.md)

- [Bayt genişlikli taşınabilirlik için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
[Wmain kullanma desteği](../text/support-for-using-wmain.md)
