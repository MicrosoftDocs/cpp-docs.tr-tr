---
title: Derleyici Uyarısı (düzey 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 20d6010cb83107946c00f2f7b00cda771b2e70b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199023"
---
# <a name="compiler-warning-level-3-c4159"></a>Derleyici Uyarısı (düzey 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (pop,...): daha önce itilmiş '*Identifier*' tanımlayıcısına sahip

## <a name="remarks"></a>Açıklamalar

Kaynak kodunuz, bir pragma için tanımlayıcı olmadan bir ve ardından bir **pop** yönergesi içeren bir **Push** yönergesi içerir. Sonuç olarak, *tanımlayıcı* oluşur ve daha sonraki *tanımlayıcı* kullanımları beklenmedik davranışa neden olabilir.

## <a name="example"></a>Örnek

Bu uyarıyı önlemek için, **pop** yönergesinde bir tanımlayıcı verin. Örneğin:

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
