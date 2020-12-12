---
description: 'Daha fazla bilgi edinin: yineleme deyimleri (C++)'
title: Yineleme Deyimleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: 71edf526ed641a5bcd7944c546486cf3d2fb5059
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190295"
---
# <a name="iteration-statements-c"></a>Yineleme Deyimleri (C++)

Yineleme deyimleri, bazı döngü sonlandırma ölçütlerine tabi olarak deyimlerin (veya bileşik deyimlerin) sıfır veya daha fazla kez yürütülmesine neden olur. Bu deyimler bileşik deyimler olduğunda, [Break](../cpp/break-statement-cpp.md) deyimi veya [Continue](../cpp/continue-statement-cpp.md) deyimi ile karşılaşılması dışında, bunlar sırayla yürütülür.

C++ dört yineleme deyimi sağlar — [while](../cpp/while-statement-cpp.md), [Do](../cpp/do-while-statement-cpp.md), [,](../cpp/for-statement-cpp.md)ve [Aralık tabanlı](../cpp/range-based-for-statement-cpp.md). Bunların her biri sonlandırma ifadesi sıfıra (false) hesaplanana kadar veya döngü sonlandırmasına kadar bir deyimle zorlanana kadar yinelenir **`break`** . Aşağıdaki tabloda bu deyimler ve eylemleri özetlenmektedir; her biri, izleyen bölümlerde ayrıntılı olarak ele alınmıştır.

### <a name="iteration-statements"></a>Yineleme Deyimleri

|Deyim|Değerlendirilen:|Başlatma|Artış|
|---------------|------------------|--------------------|---------------|
|**`while`**|Döngünün başı|Hayır|Hayır|
|**`do`**|Döngünün altı|Hayır|Hayır|
|**`for`**|Döngünün başı|Evet|Evet|
|**Aralık tabanlı**|Döngünün başı|Evet|Evet|

Yineleme ifadesinin ifade bölümü bir bildirim olamaz. Ancak, bildirim içeren bir bileşik ifade olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ deyimlerine genel bakış](../cpp/overview-of-cpp-statements.md)
