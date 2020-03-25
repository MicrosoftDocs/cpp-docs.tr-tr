---
title: Derleyici Uyarısı (düzey 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: f572886a24b8bb8f16ba504a561ae37cab3b6aaa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163461"
---
# <a name="compiler-warning-level-1-c4174"></a>Derleyici Uyarısı (düzey 1) C4174

' name ': #pragma bileşeni olarak kullanılamaz

## <a name="example"></a>Örnek

```cpp
// C4174.cpp
// compile with: /W1
#pragma component(info)  // C4174; unknown
#pragma component(browser, off)  // turn off browse info
int main()
{
}
```
