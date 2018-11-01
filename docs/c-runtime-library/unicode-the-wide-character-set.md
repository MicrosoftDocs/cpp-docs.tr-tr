---
title: 'Unicode: Joker Karakter Kümesi'
ms.date: 11/04/2016
f1_keywords:
- c.international
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: 0432de1203d595947eb958a032870a929f00aeb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618302"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Bir geniş karakter 2 baytlık çok dilli karakter kodudur. Modern tüm dünyada teknik simgeleri ve yayımlama özel karakterler dahil olmak üzere bilgi işlem kullanımı herhangi bir karakter olarak geniş bir karakter Unicode belirtimine göre temsil edilebilir. Microsoft içeren büyük bir consortium tarafından geliştirilen ve korunan, Unicode standardı artık yaygın olarak kabul edilir.

Bir geniş karakter türüdür **wchar_t**. Geniş karakterli dize olarak temsil edilen bir **wchar_t** dizisi ve tarafından işaret edilen bir `wchar_t*` işaretçi. Herhangi bir ASCII karakteri harf ekleyerek bir geniş karakter temsil edebilen **L** karakter. Örneğin, sonlandırıcı geniş (16-bit) null karakteri '\0' L değeridir. Benzer şekilde, ASCII değişmez değeri (L "Merhaba") için Harf L ekleyerek herhangi bir ASCII dize değişmez geniş karakter dize sabit değeri olarak temsil edebilir.

Genellikle, geniş karakterler çok baytlı karakterden daha fazla bellek alan alır ancak işlemine daha hızlıdır. Ayrıca, yalnızca bir yerel ayar çok baytlı kodlama anında temsil edilebilir, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
