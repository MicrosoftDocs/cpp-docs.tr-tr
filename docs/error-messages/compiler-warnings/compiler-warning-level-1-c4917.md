---
title: Derleyici Uyarısı (düzey 1) C4917 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 741f847e4df8095e5e91e14dd67e36c6d161071d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046270"
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