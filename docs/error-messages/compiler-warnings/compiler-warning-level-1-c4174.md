---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4174'
title: Derleyici Uyarısı (düzey 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: 59c4450e91f6e7041fc3b3b801ca34020e7b6dc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266929"
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
