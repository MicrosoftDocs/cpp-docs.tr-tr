---
title: Derleyici Uyarısı (düzey 1) C4224 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4224
dev_langs:
- C++
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49ad5937d310166dd3ca7f41e6881d98f396535f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025666"
---
# <a name="compiler-warning-level-1-c4224"></a>Derleyici Uyarısı (düzey 1) C4224

Standart olmayan uzantı kullanıldı: 'identifier' biçimsel parametre türü olarak önceden tanımlandı

Tanımlayıcı olarak daha önce kullanılmış bir `typedef`. Bu uyarı altında ANSI uyumluluğu neden olur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Örnek

```
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```