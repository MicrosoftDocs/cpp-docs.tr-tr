---
title: Yineleme Deyimleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: 72f81e2fc58a31db0c4cd3f77ba182bd8b8152a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366582"
---
# <a name="iteration-statements-c"></a>Yineleme Deyimleri (C++)

Yineleme deyimleri neden: Bazı döngü sonlandırma ölçütünü tabi sıfır veya daha fazla kez yürütülecek deyimler (veya bileşik deyimlerin). Bu deyimler bileşik deyimler olduğunda bunlar, aşağıdakiler haricinde sırayla yürütülür ya da [sonu](../cpp/break-statement-cpp.md) deyimi veya [devam](../cpp/continue-statement-cpp.md) deyimi karşılaştı.

C++, dört yineleme deyimleri sağlar — [sırada](../cpp/while-statement-cpp.md), [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), ve [aralık tabanlı for](../cpp/range-based-for-statement-cpp.md). Bunların her biri sıfır (false), sonlandırma ifade sonucunu verene kadar veya döngü sonlandırma ile zorlamalı kadar yinelenir bir **sonu** deyimi. Aşağıdaki tabloda, bu deyimler ve eylemlerinin özetlenmiştir; her ayrıntılı olarak bölümlerde ele alınmıştır.

### <a name="iteration-statements"></a>Yineleme Deyimleri

|Deyim|Sırasında değerlendirilen|Başlatma|Artırma|
|---------------|------------------|--------------------|---------------|
|**while**|Döngü en üstüne|Hayır|Hayır|
|**do**|Alt döngüsü|Hayır|Hayır|
|**for**|Döngü en üstüne|Evet|Evet|
|**Aralık tabanlı for**|Döngü en üstüne|Evet|Evet|

Bir bildirim deyimi bir yineleme deyiminin bir parçası olamaz. Ancak, bir bildirimi içeren bir bileşik deyim olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)