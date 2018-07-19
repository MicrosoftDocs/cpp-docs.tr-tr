---
title: Yineleme deyimleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8f2853189d6b31b2f3b4e371f3583d3abb6f165
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939435"
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)