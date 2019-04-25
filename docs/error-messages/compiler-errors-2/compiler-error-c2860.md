---
title: Derleyici Hatası C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 7d468fb2a71ce23bcd527cb02663dd5f7b7eecad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302871"
---
# <a name="compiler-error-c2860"></a>Derleyici Hatası C2860

'void', '(void)' dışında bir bağımsız değişken türü olamaz

Tür `void` diğer bağımsız değişkenleri olan bir bağımsız değişken türü olarak kullanılamaz.

Aşağıdaki örnek, C2860 oluşturur:

```
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```