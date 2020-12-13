---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2860'
title: Derleyici hatası C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 27474577e31cdc046769f9fc26686d3aaa7f3e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341171"
---
# <a name="compiler-error-c2860"></a>Derleyici hatası C2860

' void ', ' (void) ' dışında bir bağımsız değişken türü olamaz

Tür **`void`** , diğer bağımsız değişkenlerle bir bağımsız değişken türü olarak kullanılamaz.

Aşağıdaki örnek C2860 oluşturur:

```cpp
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```
