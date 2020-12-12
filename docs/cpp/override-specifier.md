---
description: 'Daha fazla bilgi edinin: geçersiz kılma belirticisi'
title: override Tanımlayıcısı
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: da29c5c37ff834513736bda02745d031fe3d92aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146009"
---
# <a name="override-specifier"></a>override Tanımlayıcısı

Bir temel sınıftaki sanal işlevi geçersiz kılan üye işlevlerini belirlemek için **override** anahtar sözcüğünü kullanabilirsiniz.

## <a name="syntax"></a>Syntax

```
function-declaration override;
```

## <a name="remarks"></a>Açıklamalar

**geçersiz kılma** bağlam duyarlıdır ve yalnızca bir üye işlev bildiriminden sonra kullanıldığında özel anlamı vardır; Aksi takdirde, ayrılmış bir anahtar sözcük değildir.

## <a name="example"></a>Örnek

Kodunuzda yanlışlıkla devralma davranışını önlemeye yardımcı olması için **geçersiz kılma** kullanın. Aşağıdaki örnek, **geçersiz kılma** kullanılmadan, türetilen sınıfın üye işlev davranışının amaçlanmadığını gösterir. Derleyici bu kod için herhangi bir hata oluşturmaz.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

**Override** kullandığınızda, derleyici sessizce yeni üye işlevleri oluşturmak yerine hatalar oluşturur.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

İşlevlerin geçersiz kılınamayacağını ve sınıfların devralınamayacağını belirtmek için [final](../cpp/final-specifier.md) anahtar sözcüğünü kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Son belirtici](../cpp/final-specifier.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
