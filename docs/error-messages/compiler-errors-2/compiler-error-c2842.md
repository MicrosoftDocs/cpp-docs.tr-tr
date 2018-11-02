---
title: Derleyici Hatası C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 2ec39768a88da049c6a31ca2a9de226e25479c99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571476"
---
# <a name="compiler-error-c2842"></a>Derleyici Hatası C2842

'class': yönetilen bir WinRT türü kendi 'operator new' tanımlayamaz veya 'operator delete'

Kendi tanımlayabilirsiniz ** new işleci veya **delete işleci** yerel yığında bellek ayırmalarını yönetmek için. Ancak, yalnızca yönetilen yığında ayrılmış olduğundan başvuru sınıfları bu işleçler tanımlayamazsınız.

Daha fazla bilgi için [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2842 oluşturur.

```
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
