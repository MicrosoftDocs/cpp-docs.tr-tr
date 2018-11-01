---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: 24cc4dd3cd7e0c893664339e7ad83383839b0b11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600378"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Sözdizimi

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyeleri listesi önce geldiği zaman **genel** anahtar sözcüğü, bu üyeler herhangi bir işlevden erişilebilir olduğunu belirtir. Bu, sonraki erişim belirticisi veya sınıf sonuna kadar bildirilen tüm üyeleri için geçerlidir.

Bir temel sınıfın adından önce zaman **genel** anahtar sözcüğü, temel sınıfın genel ve korumalı üyelerinin genel olduğunu belirtir ve korumalı üyeler, sırasıyla türetilmiş sınıf.

Bir sınıf içinde üyelerin varsayılan erişimi özeldir. Bir yapı veya birleşim üyelerin varsayılan erişimi geneldir.

Özel sınıfları ve yapıları için ortak bir taban sınıfın varsayılan erişim. Birleşimlerin temel sınıfları olamaz.

Daha fazla bilgi için [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md), [arkadaş](../cpp/friend-cpp.md)ve üye erişimi tablosu [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) .

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar sözcükleri (**genel**, **özel**, ve **korumalı**) türler ve Derlemelerle yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [üye erişim denetimi](member-access-control-cpp.md).

> [!NOTE]
>  İle derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)