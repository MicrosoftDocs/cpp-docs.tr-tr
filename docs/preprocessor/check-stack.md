---
title: check_stack | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
dev_langs:
- C++
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70f88d1eabb58f384d754803674b35f0bd9dbeda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="checkstack"></a>check_stack
Gerekirse yığın yoklamalarını devre dışı bırakmak için derleyiciye **kapalı** (veya  **-** ) belirtilirse, veya yığın yoklamalarını varsa açmak için **üzerinde** (veya  **+** ) belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken belirtilmezse yığın yoklamalarını göre varsayılan kabul edilir. Bu pragma pragma görülen sonra tanımlanan konumundaki ilk işlev etkinleşir. Yığın yoklamalarını hiçbiri bir makro oluşturulan satır içi işlevlerin ne de bir parçasıdır.  
  
 Bir bağımsız değişken vermeyin varsa **check_stack** pragma, komut satırında belirtilen davranışı döner yığını denetleme. Daha fazla bilgi için bkz: [derleyici başvurusu](../build/reference/compiler-options.md). Etkileşimini **#pragma check_stack** ve [/Gs](../build/reference/gs-control-stack-checking-calls.md) seçeneği aşağıdaki tabloda özetlenmiştir.  
  
### <a name="using-the-checkstack-pragma"></a>Check_stack Pragması kullanma  
  
|Sözdizimi|İle derlenmiş<br /><br /> /GS seçeneği?|Eylem|  
|------------|------------------------------------|------------|  
|**#pragma check_stack( )** or<br /><br /> **#pragma check_stack**|Evet|Aşağıdaki işlevleri için yığını kapatır|  
|**#pragma check_stack( )** or<br /><br /> **#pragma check_stack**|Hayır|Aşağıdaki işlevleri için yığını açar|  
|**#pragma check_stack(on)**<br /><br /> veya **#pragma check_stack +**|Evet veya Hayır|Aşağıdaki işlevleri için yığını açar|  
|**#pragma check_stack(off)**<br /><br /> or **#pragma check_stack -**|Evet veya Hayır|Aşağıdaki işlevleri için yığını kapatır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)