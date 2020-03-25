---
title: Derleyici Uyarısı (düzey 1) C4917
ms.date: 11/04/2016
f1_keywords:
- C4917
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
ms.openlocfilehash: c7a2d72b429f762e476286093c7f273a9a546cb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174680"
---
# <a name="compiler-warning-level-1-c4917"></a>Derleyici Uyarısı (düzey 1) C4917

' bildirimci ': bir GUID yalnızca bir sınıf, arabirim veya ad alanıyla ilişkilendirilebilir

[Class](../../cpp/class-cpp.md), [Interface](../../cpp/interface.md)veya [Namespace](../../cpp/namespaces-cpp.md) dışında Kullanıcı tanımlı bir yapının GUID 'i olamaz.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki kod örneği C4917 oluşturur:

```cpp
// C4917.cpp
// compile with: /W1
#pragma warning(default : 4917)
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S
{
} s;   // C4917, don't put uuid on a struct

int main()
{
}
```
