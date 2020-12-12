---
description: 'Daha fazla bilgi edinin: Public (C++)'
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: 1fd9377647568a9f4e2079d93097ca49bd6ed9be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319449"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Syntax

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyeleri listesinden önce, **`public`** anahtar sözcüğü, bu üyelerin herhangi bir işlevden erişilebilir olduğunu belirtir. Bu, bir sonraki erişim tanımlayıcısına veya sınıfın sonuna kadar belirtilen tüm Üyeler için geçerlidir.

Temel sınıfın adından önce, **`public`** anahtar sözcüğü, temel sınıfın ortak ve korunan üyelerinin, türetilmiş sınıfın sırasıyla ortak ve korumalı Üyeler olduğunu belirtir.

Bir sınıftaki üyelerin varsayılan erişimi özeldir. Bir yapıda veya birleşimde üyelerin varsayılan erişimi geneldir.

Temel sınıfa varsayılan erişim sınıflar için özeldir ve yapılar için geneldir. Birleşimler temel sınıflara sahip olamaz.

Daha fazla bilgi için bkz. [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)içindeki [özel](../cpp/private-cpp.md), [korunan](../cpp/protected-cpp.md), [arkadaş](../cpp/friend-cpp.md)ve üye erişim tablosu.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar sözcükleri ( **`public`** , **`private`** ve **`protected`** ) derlemelerle ilgili olarak türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz. [üye Access Control](member-access-control-cpp.md).

> [!NOTE]
> [/Ln](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

## <a name="end-clr-specific"></a>END /clr Özel

## <a name="example"></a>Örnek

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
