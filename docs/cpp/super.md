---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: 3afc2e8049cfcca40db389bed84baa6f42dae126
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213157"
---
# `__super`

**Microsoft'a Özgü**

Geçersiz kılmamanız gereken bir işlev için temel sınıf uygulamasını çağırmamayı açıkça belirtmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
__super::member_function();
```

## <a name="remarks"></a>Açıklamalar

Tüm erişilebilir temel sınıf yöntemleri, aşırı yükleme çözümleme aşamasında değerlendirilir ve en iyi eşleşmeyi sağlayan işlev çağrılan biridir.

**`__super`** yalnızca bir üye işlevinin gövdesinde yer alabilir.

**`__super`** Using bildirimiyle birlikte kullanılamaz. Daha fazla bilgi için bkz. [bildirimi kullanma](../cpp/using-declaration.md) .

Kod eklenen [özniteliklerin](../windows/attributes/attributes-alphabetical-reference.md) tanıtılmasıyla birlikte kodunuz, bilinen adlara sahip ancak çağırmak istediğiniz yöntemleri içeren bir veya daha fazla temel sınıf içerebilir.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
