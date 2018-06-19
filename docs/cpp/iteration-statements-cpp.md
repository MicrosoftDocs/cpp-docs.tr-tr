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
ms.openlocfilehash: 1973223d6aab44d4c5d8652111d3e6b8251676fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418919"
---
# <a name="iteration-statements-c"></a>Yineleme Deyimleri (C++)
Yineleme deyimleri bazı döngü sonlandırma ölçütleri tabi sıfır veya daha fazla kez yürütülecek deyimleri (veya bileşik deyimler) neden. Bu deyimler bileşik deyimler olduğunda ne zaman dışında sırada yürütülür ya da [sonu](../cpp/break-statement-cpp.md) deyimi veya [devam](../cpp/continue-statement-cpp.md) deyimi karşılaştı.  
  
 C++ dört yineleme deyimleri sağlar — [sırada](../cpp/while-statement-cpp.md), [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), ve [aralık tabanlı için](../cpp/range-based-for-statement-cpp.md). Bunların her biri sıfır (false), sonlandırma ifadeyi hesaplar kadar veya döngü sonlandırma ile zorlanır kadar tekrarlanan bir **sonu** deyimi. Aşağıdaki tabloda, bu deyimleri ve eylemlerinin özetlenmiştir; her izleyen bölümlerde ayrıntılı olarak ele alınmıştır.  
  
### <a name="iteration-statements"></a>Yineleme Deyimleri  
  
|Deyim|Konumundaki hesaplanan|Başlatma|Artırma|  
|---------------|------------------|--------------------|---------------|  
|`while`|Döngü üstündeki|Hayır|Hayır|  
|**do**|Alt döngüsü|Hayır|Hayır|  
|**for**|Döngü üstündeki|Evet|Evet|  
|**Aralık tabanlı için**|Döngü üstündeki|Evet|Evet|  
  
 Bir yineleme deyimi deyim bölümü bildirimi olamaz. Ancak, bir bildirimi içeren bileşik bir ifade olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)