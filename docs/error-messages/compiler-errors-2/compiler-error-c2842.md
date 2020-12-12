---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2842'
title: Derleyici hatası C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: f086c6c5fcfa451f320d96470615e4f5f4d5674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119989"
---
# <a name="compiler-error-c2842"></a>Derleyici hatası C2842

> '*Class*': yönetilen veya WinRT türü kendi ' operator New ' veya ' operator delete ' tanımlayamayabilir

## <a name="remarks"></a>Açıklamalar

Yerel yığında bellek ayırmayı yönetmek için kendi **operatörüzü New** veya **operator delete** olarak tanımlayabilirsiniz. Ancak, yalnızca yönetilen yığında ayrıldığından, başvuru sınıfları bu işleçleri tanımlayamazlar.

Daha fazla bilgi için bkz. [Kullanıcı tanımlı işleçler (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2842 oluşturur.

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
