---
title: Derleyici Uyarısı (düzey 1) C4218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1970dd1bd231716f59508a7cca9f82d3e13151ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074053"
---
# <a name="compiler-warning-level-1-c4218"></a>Derleyici Uyarısı (düzey 1) C4218

Standart olmayan uzantı kullanıldı: en az bir depolama sınıfı veya türü belirtmeniz gerekir

Varsayılan Microsoft Uzantıları (/Ze) ile bir türü veya depolama sınıfı belirtmeden bir değişken bildirebilir. Varsayılan türü `int`.

## <a name="example"></a>Örnek

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Bu tür bildirimleri ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).