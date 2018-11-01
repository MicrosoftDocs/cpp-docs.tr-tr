---
title: Derleyici Hatası C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: 255647a2e603b5a71855374dba3248ffef1e025e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440436"
---
# <a name="compiler-error-c3050"></a>Derleyici Hatası C3050

'type1': başvuru sınıfı 'type1' devralamaz

`System::ValueType` bir başvuru türü için bir taban sınıf olamaz.

Aşağıdaki örnek, C3050 oluşturur:

```
// C3050.cpp
// compile with: /clr /LD
ref struct X : System::ValueType {};   // C3050
ref struct Y {};   // OK
```