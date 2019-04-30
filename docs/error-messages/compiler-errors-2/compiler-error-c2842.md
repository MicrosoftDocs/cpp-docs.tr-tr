---
title: Derleyici Hatası C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 99b2c86d1e914c9425c2664d4e858bba6cb99486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382950"
---
# <a name="compiler-error-c2842"></a>Derleyici Hatası C2842

> '*sınıfı*': yönetilen bir WinRT türü kendi 'operator new' tanımlayamaz veya 'operator delete'

## <a name="remarks"></a>Açıklamalar

Kendi tanımlayabilirsiniz **new işleci** veya **delete işleci** yerel yığında bellek ayırmalarını yönetmek için. Ancak, yalnızca yönetilen yığında ayrılmış olduğundan başvuru sınıfları bu işleçler tanımlayamazsınız.

Daha fazla bilgi için [kullanıcı tanımlı işleçler (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2842 oluşturur.

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
