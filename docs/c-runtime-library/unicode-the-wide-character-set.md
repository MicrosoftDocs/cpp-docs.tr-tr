---
title: 'Unicode: Joker Karakter Kümesi'
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: 3a0c5698544c72e19feea8f35b7f5a516d95d561
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444492"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Geniş bir karakter 2 baytlık çok dilli karakter kodudur. Teknik semboller ve özel yayımlama karakterleri dahil olmak üzere modern bilgi işlem ortamında kullanılan herhangi bir karakter, Unicode belirtimine göre geniş bir karakter olarak temsil edilebilir. Microsoft 'un bulunduğu büyük bir konsorsiyum tarafından geliştirilen ve korunan, Unicode standardı artık yaygın olarak kabul edilir.

Geniş bir karakter **wchar_t**türündedir. Geniş karakterli bir dize **wchar_t []** dizisi olarak temsil edilir ve bir `wchar_t*` işaretçisi tarafından işaret edilir. Karakteri harfe **lvalue** olarak ekleyerek HERHANGI bir ASCII karakterini geniş bir karakter olarak temsil edebilirsiniz. Örneğin, L ' \ 0 ', Sonlandırıcı geniş (16 bit) null karakterdir. Benzer şekilde, ASCII değişmez değeri (L "Hello") için L harfine önek ekleyerek yalnızca bir ASCII dize sabit değerini geniş karakterli bir dize sabiti olarak temsil edebilirsiniz.

Genellikle, geniş karakterler çok baytlı karakterlerden çok daha fazla alan kaplar ancak işlemek daha hızlıdır. Ayrıca, çok baytlı kodlamada yalnızca bir yerel ayar gösterilebilir, ancak dünyanın tüm karakter kümeleri aynı anda Unicode temsili tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
