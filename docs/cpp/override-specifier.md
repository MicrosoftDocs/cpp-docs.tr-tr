---
title: override Tanımlayıcısı
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 82837ae34ab786e607df54038493b14350574a15
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188486"
---
# <a name="override-specifier"></a>override Tanımlayıcısı

Bir temel sınıftaki sanal işlevi geçersiz kılan üye işlevlerini belirlemek için **override** anahtar sözcüğünü kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
function-declaration override;
```

## <a name="remarks"></a>Açıklamalar

**geçersiz kılma** bağlam duyarlıdır ve yalnızca bir üye işlev bildiriminden sonra kullanıldığında özel anlamı vardır; Aksi takdirde, ayrılmış bir anahtar sözcük değildir.

## <a name="example"></a>Örnek

Kodunuzda yanlışlıkla devralma davranışını önlemeye yardımcı olması için **geçersiz kılma** kullanın. Aşağıdaki örnek, **geçersiz kılma**kullanılmadan, türetilen sınıfın üye işlev davranışının amaçlanmadığını gösterir. Derleyici bu kod için herhangi bir hata oluşturmaz.

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

**Override**kullandığınızda, derleyici sessizce yeni üye işlevleri oluşturmak yerine hatalar oluşturur.

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

[final Tanımlayıcısı](../cpp/final-specifier.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
