---
description: pragmaMicrosoft C/C++ ' da check_stack yönergesi hakkında daha fazla bilgi edinin
title: check_stack pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragma, check_stack
- pragma, check_stack usage table
no-loc:
- pragma
ms.openlocfilehash: a395471625fed60fcf750ebac8f3159a89ba1487
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713720"
---
# <a name="check_stack-no-locpragma"></a>`check_stack` pragma

**`off`**(Veya) **`-`** belirtilmişse ve **`on`** (veya) belirtilirse yığın araştırmalarını etkinleştirmek için derleyiciye yığın araştırmaları kullanmasını söyler **`+`** .

## <a name="syntax"></a>Syntax

> **`#pragma check_stack(`** [{ **`on`** | **`off`** }] **`)`**\
> **`#pragma check_stack`** { **`+`** | **`-`** }

## <a name="remarks"></a>Açıklamalar

Bu pragma , görünmeden sonra tanımlanan ilk işlevde etkili olur pragma . Yığın araştırmaları, makroların veya satır içi oluşturulan işlevlerin bir parçası değil.

İçin bir bağımsız değişken vermezseniz **`check_stack`** pragma , yığın denetimi komut satırında belirtilen davranışa geri döner. Daha fazla bilgi için bkz. [derleyici seçenekleri](../build/reference/compiler-options.md). `#pragma check_stack`Ve [`/Gs`](../build/reference/gs-control-stack-checking-calls.md) seçeneklerinin etkileşimi aşağıdaki tabloda özetlenmiştir.

### <a name="using-the-check_stack-pragma"></a>Check_stack pragma 'ı kullanma

| Syntax | İle derlenen<br /><br /> `/Gs` seçeneği? | Eylem |
|--|--|--|
| `#pragma check_stack( )` veya<br /><br /> `#pragma check_stack` | Yes | İzleyen işlevler için yığın denetimini kapatır |
| `#pragma check_stack( )` veya<br /><br /> `#pragma check_stack` | Hayır | İzleyen işlevler için yığın denetimini etkinleştirir |
| `#pragma check_stack(on)`<br /><br /> veya `#pragma check_stack +` | Evet veya Hayır | İzleyen işlevler için yığın denetimini etkinleştirir |
| `#pragma check_stack(off)`<br /><br /> veya `#pragma check_stack -` | Evet veya Hayır | İzleyen işlevler için yığın denetimini kapatır |

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
