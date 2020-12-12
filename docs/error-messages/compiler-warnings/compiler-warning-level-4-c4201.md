---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4201'
title: Derleyici Uyarısı (düzey 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: 739e09750f8f051ee0fd380fbb25858e620c70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206727"
---
# <a name="compiler-warning-level-4-c4201"></a>Derleyici Uyarısı (düzey 4) C4201

Standart olmayan uzantı kullanıldı: adsız struct/Union

Microsoft uzantıları (/Ze) altında, başka bir yapının veya birleşimin üyesi olarak bildirimci olmadan bir yapı belirtebilirsiniz. Bu yapılar, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bir hata oluşturur.

## <a name="example"></a>Örnek

```cpp
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```
