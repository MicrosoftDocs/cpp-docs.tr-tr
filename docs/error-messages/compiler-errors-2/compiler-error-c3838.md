---
title: Derleyici hatası C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: 468fc5e8cb6b3a76880f12fe0aab14810f458a90
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741358"
---
# <a name="compiler-error-c3838"></a>Derleyici hatası C3838

' Type ' öğesinden açıkça devralınabilir

Belirtilen `type` herhangi bir sınıfta temel sınıf olarak çalışamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3838 oluşturur:

```cpp
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
