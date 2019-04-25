---
title: Derleyici Hatası C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: fe6913d402c6ce4df3551c159eb56a12590799cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222537"
---
# <a name="compiler-error-c3298"></a>Derleyici Hatası C3298

'constraint_1': 'constraint_2' başvuru kısıtlaması var ve 'constraint_1' değer kısıtlaması olduğundan 'constraint_2' kısıtlama olarak kullanılamaz

Birbirini dışlayan bir kısıtlama özellikleri belirtilemez. Örneğin, bir genel tür parametresi için bir değer türünü ve bir başvuru türü kısıtlayamaz.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

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