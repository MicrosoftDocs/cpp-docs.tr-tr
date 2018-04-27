---
title: 'Unicode: Joker karakter kümesi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3551ee39896ea7b5c9e64456bed728ec884d7db
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Geniş karakter 2-bayt çok dilli karakter kodudur. Modern dünya çapında teknik simgeleri ve özel yayımlama karakterleri dahil olmak üzere bilgi işlem kullanımda herhangi bir karakter geniş karakter olarak Unicode belirtimine göre temsil edilebilir. Microsoft içeren büyük bir Konsorsiyumu tarafından geliştirilen ve korunan, standart Unicode artık yaygın olarak kabul edilir.

Geniş karakter türünde **wchar_t**. Bir joker karakter dizesi olarak temsil edilen bir **wchar_t** dizi ve işaret ediyor bir `wchar_t*` işaretçi. Herhangi bir ASCII karakter harf ekleyerek geniş karakter olarak temsil edebilir **L** karakter. Örneğin, geniş sonlandırma L '\0' dir (16-bit) **NULL** karakter. Benzer şekilde, L Harfi ASCII değişmez değeri (L "Hello") ekleyerek bir joker karakter dize sabit değeri değişmez değer herhangi bir ASCII dize temsil edebilir.

Genellikle, geniş karakterler birden çok baytlı karakterler bellekte daha fazla alan kaplamaları ancak işlem daha hızlıdır. Ayrıca, yalnızca bir yerel ayar aynı anda birden çok baytlı kodlamada temsil, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
