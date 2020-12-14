---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3838'
title: Derleyici hatası C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: 9ea5f250b7a881ab9be6724f84dac418eefc705e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249158"
---
# <a name="compiler-error-c3838"></a>Derleyici hatası C3838

' Type ' öğesinden açıkça devralınabilir

Belirtilen, `type` herhangi bir sınıfta temel sınıf olarak çalışamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3838 oluşturur:

```cpp
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
