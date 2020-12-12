---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2570'
title: Derleyici hatası C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: faebc117991262c8fff94ef75f18d6e59c884315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209028"
---
# <a name="compiler-error-c2570"></a>Derleyici hatası C2570

' tanımlayıcı ': birleşimin Taban sınıfları olamaz

Bir birleşim, bir sınıf, yapı veya birleşimden türetilir. Buna izin verilmez. Yerine türetilmiş türü bir sınıf veya yapı olarak bildirin.

Aşağıdaki örnek C2570 oluşturur:

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
