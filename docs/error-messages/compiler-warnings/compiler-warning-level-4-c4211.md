---
title: Derleyici Uyarısı (düzey 4) C4211 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4211
dev_langs:
- C++
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e38764970b8afde477c4f627e5cd3e5874d3b129
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054545"
---
# <a name="compiler-warning-level-4-c4211"></a>Derleyici Uyarısı (düzey 4) C4211

Standart olmayan uzantı kullanıldı: extern, static yeniden tanımlandı

Varsayılan Microsoft uzantıları ile (/Ze), tanımlayabilirsiniz bir `extern` tanımlayıcı olarak **statik**.

## <a name="example"></a>Örnek

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

ANSI Uyumluluğu altında geçersiz tür yeniden tanımlaması ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="see-also"></a>Ayrıca Bkz.

