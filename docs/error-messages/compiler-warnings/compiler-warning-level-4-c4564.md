---
title: Derleyici Uyarısı (düzey 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: f5db6bf366c86a716be33539feb0085ac03a9647
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683158"
---
# <a name="compiler-warning-level-4-c4564"></a>Derleyici Uyarısı (düzey 4) C4564

' class ' sınıfının ' Method ' metodu desteklenmeyen ' Parameter ' varsayılan parametresini tanımlıyor

Derleyici, varsayılan değerlere sahip bir veya daha fazla parametre içeren bir yöntem algıladı. Parametreler çağrıldığında parametreler için varsayılan değer (ler) gözardı edilir; Bu parametrelerin değerlerini açıkça belirtin. Bu parametreler için açıkça değer belirtmezseniz, C++ derleyici bir hata oluşturur.

Aşağıdaki. dll verildiğinde, yöntem bağımsız değişkenlerinde Varsayılan parametrelere izin veren Visual Basic oluşturuldu:

```vb
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

Ve Visual Basic ile C++ oluşturulan. dll kullanan aşağıdaki örnek,

```cpp
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