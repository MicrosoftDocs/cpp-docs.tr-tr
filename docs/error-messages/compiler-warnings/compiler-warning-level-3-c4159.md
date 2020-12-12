---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4159'
title: Derleyici Uyarısı (düzey 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 153bd7ee7bc634ab10e0e6eb872a8f055e6470e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326469"
---
# <a name="compiler-warning-level-3-c4159"></a>Derleyici Uyarısı (düzey 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (pop,...): daha önce itilmiş '*Identifier*' tanımlayıcısına sahip

## <a name="remarks"></a>Açıklamalar

Kaynak kodunuz, bir pragma için tanımlayıcı olmadan bir ve ardından bir **pop** yönergesi içeren bir **Push** yönergesi içerir. Sonuç olarak, *tanımlayıcı* oluşur ve daha sonraki *tanımlayıcı* kullanımları beklenmedik davranışa neden olabilir.

## <a name="example"></a>Örnek

Bu uyarıyı önlemek için, **pop** yönergesinde bir tanımlayıcı verin. Örnek:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```
