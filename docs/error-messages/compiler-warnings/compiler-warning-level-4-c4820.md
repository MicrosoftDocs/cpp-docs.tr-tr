---
title: Derleyici Uyarısı (düzey 4) C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: adf8b365bc39acc1ce729e89260f8385ecb6c048
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280405"
---
# <a name="compiler-warning-level-4-c4820"></a>Derleyici Uyarısı (düzey 4) C4820

eklenen 'member_name' oluştur değerinden sonra 'bytes' bayt dolduruluyor

Öğelerin sırasını ve türünü doldurma bir yapının sonuna eklemek derleyicinin neden oldu. Bkz: [hizalama](../../cpp/align-cpp.md) doldurma bir yapı içinde hakkında daha fazla bilgi için.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4820 oluşturur:

```
// C4820.cpp
// compile with: /W4 /c
#pragma warning(default : 4820)

// Delete the following 4 lines to resolve.
__declspec(align(2)) struct MyStruct {
   char a;
   int i;   // C4820
};

// OK
#pragma pack(1)
__declspec(align(1)) struct MyStruct2 {
   char a;
   int i;
};
```