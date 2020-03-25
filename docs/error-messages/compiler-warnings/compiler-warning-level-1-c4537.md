---
title: Derleyici Uyarısı (düzey 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 81058f153228d3d8fbf4097c140962d0cb9677e5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186367"
---
# <a name="compiler-warning-level-1-c4537"></a>Derleyici Uyarısı (düzey 1) C4537

> '*Object*': '*operator*', udt olmayan türe uygulandı

## <a name="remarks"></a>Açıklamalar

Bir nesne (Kullanıcı tanımlı tür) beklenirken bir başvuru geçirildi. Başvuru bir nesne değil, ancak satır içi assembler kodu ayrım yapamaz. Derleyici, *nesne* bir örnek olmasına rağmen kodu oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4537 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```
