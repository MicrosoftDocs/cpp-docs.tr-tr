---
title: Derleyici Hatası C3050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3050
dev_langs:
- C++
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06350b08875741c87ec3eaf76d6fd40744341c2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025912"
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