---
title: 'Unicode: Joker karakter kümesi'
ms.date: 11/04/2016
f1_keywords:
- c.international
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: dc9028be85870766af0274ede091d74a9b4d5130
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745431"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker karakter kümesi

Bir geniş karakter 2 baytlık çok dilli karakter kodudur. Modern tüm dünyada teknik simgeleri ve yayımlama özel karakterler dahil olmak üzere bilgi işlem kullanımı herhangi bir karakter olarak geniş bir karakter Unicode belirtimine göre temsil edilebilir. Microsoft içeren büyük bir consortium tarafından geliştirilen ve korunan, Unicode standardı artık yaygın olarak kabul edilir.

Bir geniş karakter türüdür **wchar_t**. Geniş karakterli dize olarak temsil edilen bir **wchar_t** dizisi ve tarafından işaret edilen bir `wchar_t*` işaretçi. Herhangi bir ASCII karakteri harf ekleyerek bir geniş karakter temsil edebilen **L** karakter. Örneğin, sonlandırıcı geniş (16-bit) null karakteri '\0' L değeridir. Benzer şekilde, ASCII değişmez değeri (L "Merhaba") için Harf L ekleyerek herhangi bir ASCII dize değişmez geniş karakter dize sabit değeri olarak temsil edebilir.

Genellikle, geniş karakterler çok baytlı karakterden daha fazla bellek alan alır ancak işlemine daha hızlıdır. Ayrıca, yalnızca bir yerel ayar çok baytlı kodlama anında temsil edilebilir, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
