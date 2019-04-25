---
title: Derleyici Uyarısı (düzey 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 1948bdec5367fa7943f5a0de4338fd4ecd6c6581
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220513"
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