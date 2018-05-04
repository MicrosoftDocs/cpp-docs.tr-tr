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
ms.openlocfilehash: 99f227f37f4a9de92f244df5988f7ee8088e41d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="definitions-and-conventions"></a>Tanımlar ve Kurallar
Terminal sözdizimi tanımında noktalarıdır. Herhangi bir çözüm mümkündür. Terminal ayrılmış sözcükler ve kullanıcı tanımlı tanımlayıcıları kümesi içerir.  
  
 Terminal dışı sözdizimi yer tutucuları olan ve bu Özet sözdiziminde başka bir yerde tanımlanır. Tanımları özyinelemeli olabilir.  
  
 İsteğe bağlı bir bileşen tarafından alt opt belirtilir. Örneğin,  
  
```  
  
{  
expression <SUB>opt</SUB> }  
```  
  
 ayraçlar içinde isteğe bağlı bir ifadeyi belirtir.  
  
 Sözdizimi kurallarına farklı yazı tipi özniteliklerini sözdizimi farklı bileşenler için kullanın. Simgeler ve yazı tipleri aşağıdaki gibidir:  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|*nonterminal*|İtalik tür terminal olmayanları gösterir.|  
|**const**|Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır.|  
|opt|Opt'un arkasından gelen terminal olmayanlar zaman isteğe bağlıdır.|  
|varsayılan yazı tipi|Karakter kümesinde açıklanan veya bu yazı listelenen C deyimlerinde Terminal olarak kullanılabilir.|  
  
 İki nokta (**:**) bir nonterminal aşağıdaki tanımına tanıtır. Alternatif tanımları listelenen ayrı satırlara dışında sözcüklerle başında zaman "birini."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Dili Sözdizimi Özeti](../c-language/c-language-syntax-summary.md)