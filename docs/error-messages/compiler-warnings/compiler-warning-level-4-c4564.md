---
title: Derleyici Uyarısı (düzey 4) C4564 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8d392251c8168490d7841ad590731b5a08e7f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031840"
---
# <a name="compiler-warning-level-4-c4564"></a>Derleyici Uyarısı (düzey 4) C4564

desteklenmeyen varsayılan parametre 'parametresi' yöntemi 'class' sınıfının ' yöntemi' tanımlar

Derleyicinin varsayılan değeri olan bir veya daha fazla parametrelere sahip bir yöntemi algılandı. Yöntem çağrıldığında parametreler için varsayılan değerleri göz ardı edilir; açıkça bu parametreler için değerler belirtin. C++ derleyicisi, açıkça bu parametreleri için değer belirtmezseniz, bir hata oluşturur.

Visual Basic ile oluşturulan aşağıdaki .dll yöntem bağımsız değişkenlerine göre varsayılan parametreleri sağlayan:

```
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

Ve Visual Basic ile oluşturulan .dll dosyasını kullanan aşağıdaki C++ örneği

```
// C4564.cpp
// compile with: /clr /W4 /WX
#using <C4564.dll>

int main() {
   TestClass ^ myx = gcnew TestClass();   // C4564
   myx->MyMethod(9);
   // try the following line instead, to avoid an error
   // myx->MyMethod(9, 1);
}
```