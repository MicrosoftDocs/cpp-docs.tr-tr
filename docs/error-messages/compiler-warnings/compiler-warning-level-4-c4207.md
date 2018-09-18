---
title: Derleyici Uyarısı (düzey 4) C4207 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4207
dev_langs:
- C++
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5aa7f364eb8f60d680dde4c252b9c84e258cda0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068838"
---
# <a name="compiler-warning-level-4-c4207"></a>Derleyici Uyarısı (düzey 4) C4207

Standart olmayan uzantı kullanıldı: uzatılmış Başlatıcı biçimi

Boyutsuz bir dizi Microsoft Uzatmaları (/Ze) ile başlatabilir `char` kullanarak küme ayraçları içinde bir dize.

## <a name="example"></a>Örnek

```
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

Bu tür başlatmalar ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).