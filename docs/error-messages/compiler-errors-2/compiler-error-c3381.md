---
title: Derleyici hatası C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: eadc9b45b4cd4f2d9b533f387dadd66be8acc963
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749574"
---
# <a name="compiler-error-c3381"></a>Derleyici hatası C3381

' Assembly ': derleme erişim belirticileri yalnızca/clr seçeneğiyle derlenen kodda kullanılabilir

Yerel türler derleme dışında görünebilir, ancak yalnızca bir **/clr** derlemesinde yerel türler için derleme erişimi belirtebilirsiniz.

Daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3381 oluşturur.

```cpp
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```
