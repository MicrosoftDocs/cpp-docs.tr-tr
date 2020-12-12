---
description: Daha fazla bilgi edinin:/DISASM
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 764754e017958a57afd53236b7fc1ffb6217d850
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192908"
---
# <a name="disasm"></a>/DISASM

Kod bölümlerinin ayrıştırılmış derlemesini DUMPBIN çıktısında yazdırın.

## <a name="syntax"></a>Syntax

> **/disasm**{**:** \[ **bayt** | **nobytes**]}

### <a name="arguments"></a>Arguments

**SAYACıNıN**<br/>
Açıklama baytlarını, yorumlanan işlem kodları ve bağımsız değişkenlerle birlikte, ayırt derleme çıktısında içerir. Bu varsayılan seçenektir.

**Yanıt sayısı**<br/>
, Deassembly çıktısına yönerge baytlarını içermez.

## <a name="remarks"></a>Açıklamalar

**/Disasm** seçeneği, dosyadaki kod bölümlerinin ayrıştırılmış derlemesini görüntüler. Dosyada varsa hata ayıklama sembolleri kullanır.

**/Disasm** yalnızca yerel, yönetilmeyen ve görüntülerde kullanılmalıdır. Yönetilen kod için eşdeğer araç [ıldadsm](/dotnet/framework/tools/ildasm-exe-il-disassembler)' dir.

Yalnızca [/Headers](headers.md) dumpbin seçeneği [/GL (tüm program iyileştirmesi)](gl-whole-program-optimization.md) derleyici seçeneği tarafından oluşturulan dosyalarda kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
