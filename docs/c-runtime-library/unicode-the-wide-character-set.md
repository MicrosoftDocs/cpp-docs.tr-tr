---
title: 'Unicode: Joker karakter kümesi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fcd1c874c1701f471026deec73ab596971d3ad4
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Geniş karakter 2-bayt çok dilli karakter kodudur. Modern dünya çapında teknik simgeleri ve özel yayımlama karakterleri dahil olmak üzere bilgi işlem kullanımda herhangi bir karakter geniş karakter olarak Unicode belirtimine göre temsil edilebilir. Microsoft içeren büyük bir Konsorsiyumu tarafından geliştirilen ve korunan, standart Unicode artık yaygın olarak kabul edilir.

Geniş karakter türünde **wchar_t**. Bir joker karakter dizesi olarak temsil edilen bir **wchar_t** dizi ve işaret ediyor bir `wchar_t*` işaretçi. Herhangi bir ASCII karakter harf ekleyerek geniş karakter olarak temsil edebilir **L** karakter. Örneğin, L '\0' sonlandırma wide (16-bit) null karakterdir. Benzer şekilde, L Harfi ASCII değişmez değeri (L "Hello") ekleyerek bir joker karakter dize sabit değeri değişmez değer herhangi bir ASCII dize temsil edebilir.

Genellikle, geniş karakterler birden çok baytlı karakterler bellekte daha fazla alan kaplamaları ancak işlem daha hızlıdır. Ayrıca, yalnızca bir yerel ayar aynı anda birden çok baytlı kodlamada temsil, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
