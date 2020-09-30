---
title: 'Unicode: Joker Karakter Kümesi'
description: Microsoft C çalışma zamanı 'nda Unicode geniş karakter kümesine giriş.
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: 751017a62a960eaf2afa2354a43a13971b89252a
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590166"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Joker Karakter Kümesi

Geniş bir karakter 2 baytlık çok dilli karakter kodudur. Teknik semboller ve özel yayımlama karakterleri dahil olmak üzere modern bilgi işlem ortamında kullanılan herhangi bir karakter, Unicode belirtimine göre geniş bir karakter olarak temsil edilebilir. Microsoft 'un bulunduğu büyük bir konsorsiyum tarafından geliştirilen ve korunan, Unicode standardı artık yaygın olarak kabul edilir.

Geniş bir karakter türü **`wchar_t`** . Geniş karakterli bir dize, dizi olarak temsil edilir **`wchar_t[]`** . Bir işaretçiyle diziyi işaret edersiniz `wchar_t*` . 

Harfine önek ekleyerek herhangi bir ASCII karakterini geniş bir karakter olarak temsil edebilirsiniz `L` . Örneğin, `L'\0'` Sonlandırıcı geniş (16 bit) null karakterdir.

Herhangi bir ASCII dize sabit değerini, harfe önek ekleyerek geniş karakterli bir dize sabiti olarak temsil edebilirsiniz `L` . Örneğin, `L"Hello"`.

Genellikle, geniş karakterler çok baytlı karakterlerden çok daha fazla alan kullanır. Ancak çok sayıda karakter işlemek daha hızlıdır. Çok baytlı Kodlamadaki bir anda yalnızca bir yerel ayar gösterilebilir. Dünyanın tüm karakter kümeleri aynı anda Unicode temsili tarafından temsil edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)\
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
