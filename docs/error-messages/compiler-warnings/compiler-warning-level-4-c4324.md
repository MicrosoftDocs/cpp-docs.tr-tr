---
title: Derleyici Uyarısı (düzey 4) C4324 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4324
dev_langs:
- C++
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2499aa7c674e3bd1bece14c39b09f9863d6bb783
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064795"
---
# <a name="compiler-warning-level-4-c4324"></a>Derleyici Uyarısı (düzey 4) C4324

'struct_name': __declspec(align()) nedeniyle yapının sonu dolduruldu

Belirttiğiniz için doldurma bir yapının sonuna eklenen bir [__declspec(align)](../../cpp/align-cpp.md) değeri.

Örneğin, aşağıdaki kod C4324 oluşturur:

```
// C4324.cpp
// compile with: /W4
struct __declspec(align(32)) A
{
   char a;
};   // C4324

int main()
{
}
```