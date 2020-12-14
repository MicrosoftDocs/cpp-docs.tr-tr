---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4010'
title: Derleyici Uyarısı (düzey 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 899e34e0835cce02ab5d11b6c64ae604369f93d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241592"
---
# <a name="compiler-warning-level-1-c4010"></a>Derleyici Uyarısı (düzey 1) C4010

Tek satırlı açıklama satır devamlılık karakteri içerir

//Tarafından tanıtılan tek satırlık bir açıklama, \\ satır devamlılık karakteri görevi gören bir ters eğik çizgi () içerir. Derleyici sonraki satırı bir devamlılık olarak değerlendirir ve bunu bir yorum olarak değerlendirir.

Bazı sözdizimi temelli düzenleyiciler, bir yorum olarak devamlılık karakteri izleyen çizgiyi göstermez. Bu uyarıya neden olan satırlarda söz dizimi renklendirmesini yoksay.

Aşağıdaki örnek C4010 oluşturur:

```cpp
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```
