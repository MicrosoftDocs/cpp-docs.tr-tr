---
title: Derleyici hatası C3381
description: Microsoft C++ derleyici hatası C3381, nedenleri ve nasıl çözümlenir.
ms.date: 09/28/2020
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: 48a6c81f9506c532333b5353b8b194d17c91043f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510151"
---
# <a name="compiler-error-c3381"></a>Derleyici hatası C3381

> '*tanımlayıcı*': derleme erişim belirticileri yalnızca/clr seçeneğiyle derlenen kodda kullanılabilir

Bir tür, yalnızca kullanılarak derlenen kodda izin verilen bir erişim belirticisi kullanılarak bildirildi veya tanımlanmıştır **`/clr`** .

## <a name="remarks"></a>Açıklamalar

Bu hata, **`public`** **`protected`** **`private`** **`:`** veya içindeki bir erişim belirticisinden sonra yanlış bir, veya anahtar sözcüğünün veya eksik bir iki nokta () olabilir **`class`** **`struct`** .

C++/CLı ' da yerel türler bir derlemenin dışında görünebilir, ancak derleme içindeki yerel türler için yalnızca derleme erişimi belirtebilirsiniz **`/clr`** . Daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [ `/clr` (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3381 oluşturur. Bu çözümü onarmak için önce **`public`** tanımdan belirteci kaldırın ya da `class A` seçeneğini kullanarak derleyin **`/clr`** . Ardından, için erişimi belirttikten sonra bir iki nokta üst üste ekleyin **`private`** `class B {} b;` . Bunun nedeni, iç içe bir sınıfın bildiriminin bir parçası olarak bir derleme erişim belirticisi olamaz.

```cpp
// C3381.cpp
// compile with: /c
public class A {   // C3381
    private class B {} b;   // C3381
};
```
