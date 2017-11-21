---
title: "NMAKE makrosu tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b355431576a4662062a00ce2c4e44f3a0a52ffdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-an-nmake-macro"></a>NMAKE Makrosu Tanımlama
## <a name="syntax"></a>Sözdizimi  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Makroadı* bir harf, rakam ve alt çizgi (_) en çok 1024 karakter bileşimidir ve önemli bir durumdur. *Makroadı* çağrılan makrosu içerebilir. Varsa *makroadı* oluşur tamamen bir çağrılan makro, çağrılan makrosu null veya tanımsız olamaz.  
  
 `string` Herhangi bir dizi sıfır veya daha fazla karakter olabilir. Boş bir dize sıfır karakter veya yalnızca boşluk ya da sekme içerir. `string` Makrosu çağırma içerebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Makrolardaki özel karakterler](../build/special-characters-in-macros.md)  
  
 [Boş ve tanımlanmamış makrolar](../build/null-and-undefined-macros.md)  
  
 [Makroları nerede tanımlamalı](../build/where-to-define-macros.md)  
  
 [Makro tanımlarında öncelik](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve NMAKE](../build/macros-and-nmake.md)