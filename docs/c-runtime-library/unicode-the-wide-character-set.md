---
title: 'Unicode: Joker Karakter Kümesi'
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: b27641b9843d4f6f1ef39d893df5d3f26af372e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220658"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Geniş bir karakter 2 baytlık çok dilli karakter kodudur. Teknik semboller ve özel yayımlama karakterleri dahil olmak üzere modern bilgi işlem ortamında kullanılan herhangi bir karakter, Unicode belirtimine göre geniş bir karakter olarak temsil edilebilir. Microsoft 'un bulunduğu büyük bir konsorsiyum tarafından geliştirilen ve korunan, Unicode standardı artık yaygın olarak kabul edilir.

Geniş bir karakter türü **`wchar_t`** . Geniş karakterli bir dize **wchar_t []** dizisi olarak temsil edilir ve bir işaretçi tarafından işaret edilir `wchar_t*` . Karakteri harfe **lvalue** olarak ekleyerek HERHANGI bir ASCII karakterini geniş bir karakter olarak temsil edebilirsiniz. Örneğin, L ' \ 0 ', Sonlandırıcı geniş (16 bit) null karakterdir. Benzer şekilde, ASCII değişmez değeri (L "Hello") için L harfine önek ekleyerek yalnızca bir ASCII dize sabit değerini geniş karakterli bir dize sabiti olarak temsil edebilirsiniz.

Genellikle, geniş karakterler çok baytlı karakterlerden çok daha fazla alan kaplar ancak işlemek daha hızlıdır. Ayrıca, çok baytlı kodlamada yalnızca bir yerel ayar gösterilebilir, ancak dünyanın tüm karakter kümeleri aynı anda Unicode temsili tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
