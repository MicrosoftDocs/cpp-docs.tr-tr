---
title: Derleyici Hatası C2842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20967ab4cd047f62a5cf692c91fec90148b4f470
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118823"
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
