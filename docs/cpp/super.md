---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: 778ed2d80aa926c7282073a99898a6aa355a3379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602624"
---
# <a name="super"></a>__super

**Microsoft'a özgü**

Açıkça geçersiz kılma bir işlev için bir temel sınıf uygulamasını çağırma durumunu sağlar.

## <a name="syntax"></a>Sözdizimi

```
__super::member_function();
```

## <a name="remarks"></a>Açıklamalar

Tüm erişilebilir temel sınıf yöntemleri aşırı yükleme çözünürlüğü aşamasında olarak kabul edilir ve en iyi eşleşmeyi sağlar çağrılan bir işlevdir.

**__super** yalnızca bir üye işlevinin gövdesi içinde görünebilir.

**__super** kullanarak bir kullanılamaz bildirimi. Bkz: [using bildirimi](../cpp/using-declaration.md) daha fazla bilgi için.

Sunulmasıyla birlikte [öznitelikleri](../windows/cpp-attributes-reference.md) kod ekleme, kodunuzu bilginiz, ancak adları çağırmak istediğiniz yöntemi içeren bir veya daha fazla temel sınıfları içerebilir.

## <a name="example"></a>Örnek

```cpp
// deriv_super.cpp
// compile with: /c
struct B1 {
   void mf(int) {}
};

struct B2 {
   void mf(short) {}

   void mf(char) {}
};

struct D : B1, B2 {
   void mf(short) {
      __super::mf(1);   // Calls B1::mf(int)
      __super::mf('s');   // Calls B2::mf(char)
   }
};
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)