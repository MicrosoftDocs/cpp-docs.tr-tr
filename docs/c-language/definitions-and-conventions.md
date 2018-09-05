---
title: Tanımlar ve kurallar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74a29acfcdc58b068ebabe9bc1c9b033cf801c21
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760412"
---
# <a name="definitions-and-conventions"></a>Tanımlar ve Kurallar
Terminaller bir söz dizimi tanımı noktalarıdır. Herhangi bir çözüm mümkündür. Terminaller ayrılmış sözcükler ve kullanıcı tanımlı tanımlayıcıları kümesi içerir.  
  
Terminal dışı sözdizimi içindeki yer tutucuları olan ve bu sözdizimi özeti başka bir yerde tanımlanır. Tanımları özyinelemeli olabilir.  
  
İsteğe bağlı bir bileşen belirtilen tarafından da simgeli <sub>iyileştirilmiş</sub>. Örneğin,  
  
> **{** *ifade*<sub>iyileştirilmiş</sub> **}**
  
Küme ayraçları içine alınmış bir isteğe bağlı ifade gösterir.  
  
Sözdizimi kurallarının, sözdiziminin farklı bileşenleri için farklı yazı tipi özniteliklerini kullanın. Simgeler ve yazı tipleri aşağıdaki gibidir:  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|*bildirimlere*|İtalik tür terminal olmayanları gösterir.|  
|**const**|Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır.|  
|<sub>iyileştirilmiş</sub>|Terminal dışı arkasından <sub>iyileştirilmiş</sub> her zaman isteğe bağlıdır.|  
|varsayılan yazı tipi|Açıklanan veya listelenen bu yazı kümesindeki C deyimlerde terminaller olarak kullanılabilir.|  
  
Bir iki nokta üst üste (**:**) bir Terminal olmayanın tanımını tanıtır. Alternatif tanımlar listelenen ayrı satırlarda dışında kelimelerinizle başında, "birini."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)