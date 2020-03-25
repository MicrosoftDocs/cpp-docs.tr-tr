---
title: Derleyici Uyarısı C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: a2298f5369ff941a9d5ac38838f531d6db478739
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165099"
---
# <a name="compiler-warning-c4867"></a>Derleyici Uyarısı C4867

' function ': işlev çağrısında bağımsız değişken listesi eksik; üyeye işaretçi oluşturmak için ' Call ' kullanın

Üye işlevine yönelik bir işaretçi yanlış başlatılmış.

Bu uyarı, Visual Studio 2005: Gelişmiş üye işaretçisi uygunluğu için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir.  Visual Studio 2005 ' den önce derlenen kod artık C4867 oluşturacak.

Bu uyarı her zaman bir hata olarak verilir. Bu uyarıyı devre dışı bırakmak için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın. C4867 ve MFC/ATL hakkında daha fazla bilgi için bkz. [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

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
