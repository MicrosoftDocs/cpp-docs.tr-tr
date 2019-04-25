---
title: check_stack
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 49477a3b39db17047f349e341bd05c04954c964c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212405"
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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)