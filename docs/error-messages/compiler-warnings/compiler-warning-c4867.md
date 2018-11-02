---
title: Derleyici Uyarısı C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: 9fa9b382b42a2fb8ba72fd9744c612af5dd598d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526830"
---
# <a name="compiler-warning-c4867"></a>Derleyici Uyarısı C4867

'function': işlev çağrısı; bağımsız değişken listesi eksik bir üyeye işaretçi oluşturmak için 'çağrısı' kullanın

Üye işlevi işaretçisi hatalı olarak başlatıldı.

Bu uyarı için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: Gelişmiş işaretçi-üye uyumluluğu.  Visual C++ 2005'ten önce derlenmiş kod artık C4867 oluşturur.

Bu uyarı, her zaman hata olarak görüntülenir. Kullanım [uyarı](../../preprocessor/warning.md) pragması, bu uyarıyı devre dışı bırakmak için. C4867 ve MFC/ATL hakkında daha fazla bilgi için bkz. [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4867 oluşturur.

```
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