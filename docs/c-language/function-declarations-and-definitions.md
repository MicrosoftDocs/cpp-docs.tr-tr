---
title: "İşlev bildirimlerinin ve tanımlarının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea315c065e6f76215939bc4ccd70bcc907361ff4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="function-declarations-and-definitions"></a>İşlev Bildirimleri ve Tanımlar (C++)
İşlev prototipleri; işlevin türünü, dönüş türünü ve biçimsel parametrelerinin türünü ve sayısını belirler. İşlev tanımı işlev gövdesini içerir.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev tanımının içinde veya dışında hem işlev hem de değişken bildirimleri görünebilir. Bir işlev tanımı içerisindeki herhangi bir bildirimin "iç" veya "yerel" düzeyde göründüğü bildirilir. Tüm işlev tanımlarının dışında yer alan bir bildirimin, "dış", "genel" veya "dosya kapsamı" düzeyinde olduğu bildirilir. Bildirimler gibi değişken tanımlar, iç düzeyde (işlev tanımı içerisinde) veya dış düzeyde (tüm işlev tanımlarının dışında) görünebilir. İşlev tanımları her zaman dış düzeyde ortaya çıkar. İşlev tanımları tartışılır daha ayrıntılı olarak [işlev tanımları](../c-language/c-function-definitions.md). İşlev prototipleri ele alınmıştır [işlev prototipleri](../c-language/function-prototypes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)