---
title: "Tanımlar ve kurallar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fcb72c4e001a087b49967c64b10974ee41cc49ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md)