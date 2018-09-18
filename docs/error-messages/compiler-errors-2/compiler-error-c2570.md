---
title: Derleyici Hatası C2570 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5914af21ec780167c45334829a5d6517cf3662
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052991"
---
# <a name="compiler-error-c2570"></a>Derleyici Hatası C2570

'identifier': birleşimin taban sınıfları olamaz

UNION, sınıf, yapı veya birleşim türetilir. Buna izin verilmez. Türetilmiş bir tür bir sınıf veya yapı bunun yerine bildirin.

Aşağıdaki örnek C2570 oluşturur:

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```