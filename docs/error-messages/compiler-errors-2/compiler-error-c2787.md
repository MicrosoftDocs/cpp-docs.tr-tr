---
title: Derleyici Hatası C2787 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4096e5dbd5b885afe3dec136a111ec69a10784f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109138"
---
# <a name="compiler-error-c2787"></a>Derleyici Hatası C2787

'identifier': Bu nesneyle ilişkili hiçbir GUID olan

[__Uuidof](../../cpp/uuidof-operator.md) işleci ile bağlı bir GUID veya böyle bir kullanıcı tanımlı türde bir nesne kullanıcı tanımlı bir tür alır. Bağımsız değişken yok GUID'e sahip kullanıcı tanımlı bir tür olduğunda bu hata oluşur.

Aşağıdaki örnek, C2787 oluşturur:

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```