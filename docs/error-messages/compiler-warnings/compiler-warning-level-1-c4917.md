---
title: Derleyici Uyarısı (düzey 1) C4917
ms.date: 11/04/2016
f1_keywords:
- C4917
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
ms.openlocfilehash: 97f6f0a08c8ef292d81471cb5d0d94e359466933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393499"
---
# <a name="compiler-warning-level-1-c4917"></a>Derleyici Uyarısı (düzey 1) C4917

'declarator': bir GUID yalnızca bir sınıf, arabirim veya ad alanı ile ilişkilendirilebilir.

Kullanıcı tanımlı bir yapı dışındaki [sınıfı](../../cpp/class-cpp.md), [arabirimi](../../cpp/interface.md), veya [ad alanı](../../cpp/namespaces-cpp.md) bir GUID olamaz.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

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