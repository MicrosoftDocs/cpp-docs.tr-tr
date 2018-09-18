---
title: Derleyici Hatası C3298 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3298
dev_langs:
- C++
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06296fed3f33b56cb53cf3bc4531205638f0a204
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053698"
---
# <a name="compiler-error-c3298"></a>Derleyici Hatası C3298

'constraint_1': 'constraint_2' başvuru kısıtlaması var ve 'constraint_1' değer kısıtlaması olduğundan 'constraint_2' kısıtlama olarak kullanılamaz

Birbirini dışlayan bir kısıtlama özellikleri belirtilemez. Örneğin, bir genel tür parametresi için bir değer türünü ve bir başvuru türü kısıtlayamaz.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3298 oluşturur.

```
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```