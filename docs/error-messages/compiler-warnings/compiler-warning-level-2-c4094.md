---
title: Derleyici Uyarısı (Düzey 2) C4094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9317cbc31ef8bddb14da11af1087a148fd3188
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078718"
---
# <a name="compiler-warning-level-2-c4094"></a>Derleyici Uyarısı (Düzey 2) C4094

Etiketlenmemiş 'belirteci' hiçbir simge bildirimi yapmadı

Derleyici bir etiketlenmemiş yapı, birlik veya kullanarak boş bir bildirim algıladı. Bildirim yok sayılır.

## <a name="example"></a>Örnek

```
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Bu durum, ANSI Uyumluluğu altında bir hata oluşturur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).