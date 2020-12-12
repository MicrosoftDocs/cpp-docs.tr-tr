---
description: 'Daha fazla bilgi edinin: check_stack pragma'
title: check_stack pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 55a639e22ded788bd731aad83eb7918e1006ae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300859"
---
# <a name="check_stack-pragma"></a>check_stack pragması

, (Veya) belirtilirse, derleyicinin yığın araştırmasını **kapatmasını** **-** veya (veya) **belirtilmişse** yığın araştırmasını kullanmasını söyler **+** .

## <a name="syntax"></a>Syntax

> **#pragma check_stack (** **[{**  |  **off** }] **)**\
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>Açıklamalar

Bu pragma, pragma görüntülendikten sonra tanımlanan ilk işlevde devreye girer. Yığın araştırmaları, makroların veya satır içi oluşturulan işlevlerin bir parçası değil.

**Check_stack** pragma için bir bağımsız değişken vermezseniz, yığın denetimi komut satırında belirtilen davranışa geri döner. Daha fazla bilgi için bkz. [derleyici seçenekleri](../build/reference/compiler-options.md). `#pragma check_stack`Ve [/GS](../build/reference/gs-control-stack-checking-calls.md) seçeneğinin etkileşimi aşağıdaki tabloda özetlenmiştir.

### <a name="using-the-check_stack-pragma"></a>Check_stack pragma 'ı kullanma

|Syntax|İle derlenen<br /><br /> /GS seçeneği?|Eylem|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` veya<br /><br /> `#pragma check_stack`|Evet|İzleyen işlevler için yığın denetimini kapatır|
|`#pragma check_stack( )` veya<br /><br /> `#pragma check_stack`|Hayır|İzleyen işlevler için yığın denetimini etkinleştirir|
|`#pragma check_stack(on)`<br /><br /> veya `#pragma check_stack +`|Evet veya Hayır|İzleyen işlevler için yığın denetimini etkinleştirir|
|`#pragma check_stack(off)`<br /><br /> veya `#pragma check_stack -`|Evet veya Hayır|İzleyen işlevler için yığın denetimini kapatır|

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
