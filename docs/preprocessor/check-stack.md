---
title: check_stack | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b16a3d87741b8dda3b130c09d74e86a2350cd7be
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465065"
---
# <a name="checkstack"></a>check_stack
Gerekirse yığın yoklamalarını devre dışı bırakmak için derleyiciye `off` (veya `-`) belirtilirse, yığın yoklamalarını üzerinde etkinleştirin veya `on` (veya `+`) belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>Açıklamalar 

Hiçbir bağımsız değişken belirtilmezse, yığın yoklamalarını göre varsayılan kabul edilir. Bu pragmayı pragma görüldüğünde sonra tanımlanmış konumundaki ilk işlev etkinleşir. Yığın yoklamalarını hiçbiri bir makro oluşturulan satır içi işlevlerin ne de bir parçasıdır.  
  
Bir bağımsız değişken vermediyseniz **check_stack** pragması, komut satırında belirtilen davranışı döner yığın denetimi. Daha fazla bilgi için [derleyici başvurusu](../build/reference/compiler-options.md). Etkileşimi `#pragma check_stack` ve [/Gs](../build/reference/gs-control-stack-checking-calls.md) seçeneği aşağıdaki tabloda özetlenmiştir.  
  
### <a name="using-the-checkstack-pragma"></a>Check_stack Pragması kullanma  
  
|Sözdizimi|İle derlenmiş<br /><br /> /GS seçeneği?|Eylem|  
|------------|------------------------------------|------------|  
|`#pragma check_stack( )` veya<br /><br /> `#pragma check_stack`|Evet|Aşağıdaki işlevler için yığın kapatır|  
|`#pragma check_stack( )` veya<br /><br /> `#pragma check_stack`|Hayır|Aşağıdaki işlevler için yığın açar|  
|`#pragma check_stack(on)`<br /><br /> veya `#pragma check_stack +`|Evet veya Hayır|Aşağıdaki işlevler için yığın açar|  
|`#pragma check_stack(off)`<br /><br /> veya `#pragma check_stack -`|Evet veya Hayır|Aşağıdaki işlevler için yığın kapatır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)