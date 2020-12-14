---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3645'
title: Derleyici hatası C3645
ms.date: 11/04/2016
f1_keywords:
- C3645
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
ms.openlocfilehash: 198b22b80a4975d8bd6fab130c075621f248a93c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203776"
---
# <a name="compiler-error-c3645"></a>Derleyici hatası C3645

' function ': __clrcall yerel koda derlenen işlevlerde kullanılamaz

Bir işlevdeki bazı anahtar sözcüklerin varlığı, işlevin yerel olarak derlenmesine neden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3645 oluşturur.

```cpp
// C3645.cpp
// compile with: /clr /c
#pragma unmanaged
int __clrcall dog() {}   // C3645
```
