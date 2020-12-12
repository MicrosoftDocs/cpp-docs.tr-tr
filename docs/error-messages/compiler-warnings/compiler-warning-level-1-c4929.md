---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4929'
title: Derleyici Uyarısı (düzey 1) C4929
ms.date: 11/04/2016
f1_keywords:
- C4929
helpviewer_keywords:
- C4929
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
ms.openlocfilehash: 73331759ebdf43694618140985161400ecdafb1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203555"
---
# <a name="compiler-warning-level-1-c4929"></a>Derleyici Uyarısı (düzey 1) C4929

' dosya ': tür kitaplığına bir birleşim içeriyor; ' embedded_idl ' niteleyicisi yoksayılıyor

Tür kitaplığında bir birleşim mevcut olduğundan, [#import](../../preprocessor/hash-import-directive-cpp.md) embedded_idl özniteliği tür kitaplığına uygulanamadı. Bu uyarıyı çözmek için embedded_idl kullanmayın.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşeni tanımlar.

```cpp
// C4929a.cpp
// compile with: /LD /link /TLBOUT:C4929a.tlb
#include <objbase.h>
[module(name="Test")];
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {
   [case(24)]
      float fM;
   [case(25)]
      double dMN;
   [default]
      int x;
} TD_UNION_TYPE;

[export, public] typedef struct _TDW_TYPE {
   [switch_is(sU)] TD_UNION_TYPE w;
      short sU;
} TD_TYPE;

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I {
   HRESULT f(TD_TYPE*);
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct C : I {
   HRESULT f(TD_TYPE*) { return 0; }
};
```

Aşağıdaki örnek C4929 oluşturur.

```cpp
// C4929b.cpp
// compile with: /c /W1
#import "C4929a.tlb" embedded_idl   // C4929
```
