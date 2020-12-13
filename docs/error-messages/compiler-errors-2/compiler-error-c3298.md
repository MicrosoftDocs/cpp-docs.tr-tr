---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3298'
title: Derleyici hatası C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: 25b0abc98d5498e59b97f83f47bc0ba12704a328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144579"
---
# <a name="compiler-error-c3298"></a>Derleyici hatası C3298

' constraint_1 ': ' constraint_2 ' kısıtlama olarak kullanılamaz, çünkü ' constraint_2 ' başvuru kısıtlamasına sahip ve ' constraint_1 ' değer kısıtlamasına sahip

Kısıtlama için birbirini dışlayan özellikler belirtemezsiniz. Örneğin, genel bir tür parametresi hem bir değer türü hem de bir başvuru türü ile kısıtlanamaz.

Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3298 oluşturur.

```cpp
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```
