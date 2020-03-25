---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: b6f6a7e108224ab4c97893104c5d6c38d325fa42
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160833"
---
# <a name="__super"></a>__super

**Microsoft 'a özgü**

Geçersiz kılmamanız gereken bir işlev için temel sınıf uygulamasını çağırmamayı açıkça belirtmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
__super::member_function();
```

## <a name="remarks"></a>Açıklamalar

Tüm erişilebilir temel sınıf yöntemleri, aşırı yükleme çözümleme aşamasında değerlendirilir ve en iyi eşleşmeyi sağlayan işlev çağrılan biridir.

**__super** yalnızca bir üye işlevinin gövdesinde bulunabilir.

**__super** , using bildirimiyle birlikte kullanılamaz. Daha fazla bilgi için bkz. [bildirimi kullanma](../cpp/using-declaration.md) .

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
