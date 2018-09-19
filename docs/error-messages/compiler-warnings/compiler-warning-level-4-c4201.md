---
title: Derleyici Uyarısı (düzey 4) C4201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4201
dev_langs:
- C++
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 702ce23333e29548e9bfe092c15ae60c5652168e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096944"
---
# <a name="compiler-warning-level-4-c4201"></a>Derleyici Uyarısı (düzey 4) C4201

Standart olmayan uzantı kullanıldı: Adsız yapı/birleşim

Microsoft Uzatmaları (/Ze) altında bir bildirimcide olmadan bir yapının başka bir yapı veya birleşim üyesi olarak belirtebilirsiniz. Bu yapılar, ANSI Uyumluluğu altında bir hata oluştur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Örnek

```
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