---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4564'
title: Derleyici Uyarısı (düzey 4) C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 112d1d20d34619d7a39d20c7fcd5f21584730cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255177"
---
# <a name="compiler-warning-level-4-c4564"></a>Derleyici Uyarısı (düzey 4) C4564

' class ' sınıfının ' Method ' metodu desteklenmeyen ' Parameter ' varsayılan parametresini tanımlıyor

Derleyici, varsayılan değerlere sahip bir veya daha fazla parametre içeren bir yöntem algıladı. Parametreler çağrıldığında parametreler için varsayılan değer (ler) gözardı edilir; Bu parametrelerin değerlerini açıkça belirtin. Bu parametrelerin değerlerini açıkça belirtmezseniz, C++ derleyicisi bir hata oluşturur.

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

Ve Visual Basic ile oluşturulan. dll dosyasını kullanan aşağıdaki C++ örneği

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
