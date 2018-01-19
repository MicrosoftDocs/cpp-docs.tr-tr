---
title: /DISASM | Microsoft Docs
ms.date: 1/17/2018
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /disasm
dev_langs: C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d448b92c3436f3d2875bd8d9b8e0af6a7149e065
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="disasm"></a>/DISASM

DUMPBIN çıkış kodu bölümlerde ayrıştırılmış yazdırın.

## <a name="syntax"></a>Sözdizimi

> **/ DISASM**{**:**\[**BAYT**|**NOBYTES**]}  

### <a name="arguments"></a>Arguments

**BAYT**  
Yorumlanan işlem kodları ve bağımsız değişkenler ile birlikte yönerge bayt ayrıştırılmış çıktısında içerir. Varsayılan seçenek budur.

**NOBYTES**  
Yönerge bayt ayrıştırılmış çıktısında içermez.

## <a name="remarks"></a>Açıklamalar

**/DISASM** seçenek dosyasında ayrıştırılmış kodu bölümlerin görüntüler. Dosyada mevcut olup olmadığını hata ayıklama simgeleri kullanır.

**/ DISASM** yalnızca yerel, yönetilmiyor, görüntülerinde kullanılmalıdır. Yönetilen kod için eşdeğer bir araçtır [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Yalnızca [/HEADERS](../../build/reference/headers.md) DUMPBIN seçeneği tarafından üretilen dosyalar üzerinde kullanıma [/GL (bütün program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)  
