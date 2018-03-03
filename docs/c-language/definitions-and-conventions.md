---
title: "Tanımlar ve kurallar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02a6cc8ffcb5748544191673de8f07e87449e806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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