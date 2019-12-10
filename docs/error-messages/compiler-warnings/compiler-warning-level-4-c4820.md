---
title: Derleyici Uyarısı (düzey 4) C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: ac97a943e6a8178e930d93a097071b0e3da09773
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989056"
---
# <a name="compiler-warning-level-4-c4820"></a>Derleyici Uyarısı (düzey 4) C4820

eklenen 'member_name' oluştur değerinden sonra 'bytes' bayt dolduruluyor

Öğelerin türü ve sırası, derleyicinin bir yapının sonuna doldurma eklemesine neden oldu. Bir yapıda doldurma hakkında daha fazla bilgi için bkz. [hizalayın](../../cpp/align-cpp.md) .

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4820 oluşturur:

```cpp
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
