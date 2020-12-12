---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3050'
title: Derleyici hatası C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: 354efe0ba8445042571d76cfeeb41e98fae96256
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269672"
---
# <a name="compiler-error-c3050"></a>Derleyici hatası C3050

' type1 ': bir başvuru sınıfı ' type1 ' öğesinden devralınabilir

`System::ValueType` bir başvuru türü için taban sınıf olamaz.

Aşağıdaki örnek C3050 oluşturur:

```cpp
// C3050.cpp
// compile with: /clr /LD
ref struct X : System::ValueType {};   // C3050
ref struct Y {};   // OK
```
