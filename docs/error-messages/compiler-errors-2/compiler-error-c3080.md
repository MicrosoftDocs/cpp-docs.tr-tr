---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3080'
title: Derleyici hatası C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 746e5527118c617983e96d02a584a0aa4508c64c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320160"
---
# <a name="compiler-error-c3080"></a>Derleyici hatası C3080

' finalizer_function ': Sonlandırıcı bir depolama sınıfı belirticisine sahip olamaz

Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI) içinde yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3080 oluşturur.

```cpp
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```
