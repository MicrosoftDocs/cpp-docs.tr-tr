---
title: Derleyici Uyarısı C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: e093d262bc26cf0acfbb181d621fffc1aa391ee9
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626598"
---
# <a name="compiler-warning-c4867"></a>Derleyici Uyarısı C4867

' function ': işlev çağrısında bağımsız değişken listesi eksik; üyeye işaretçi oluşturmak için ' Call ' kullanın

Üye işlevine yönelik bir işaretçi yanlış başlatılmış.

Bu uyarı, Visual Studio 2005: Gelişmiş üye işaretçisi uygunluğu için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir.  Visual Studio 2005 ' den önce derlenen kod artık C4867 oluşturacak.

Bu uyarı her zaman bir hata olarak verilir. Bu uyarıyı devre dışı bırakmak için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın. C4867 ve MFC/ATL hakkında daha fazla bilgi için bkz. [_Atl_enable_ptm_warning](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4867 oluşturur.

```cpp
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```