---
description: 'Daha fazla bilgi edinin: soyut sınıflar (C++)'
title: Soyut sınıflar (C++)
ms.date: 02/18/2021
helpviewer_keywords:
- classes [C++], abstract
- base classes [C++], abstract classes [C++]
- abstract classes [C++]
- derived classes [C++], abstract classes [C++]
ms.openlocfilehash: 8a20e988cb0c0a134fd2ebb83382d81c838bcf23
ms.sourcegitcommit: 5efc34c2b98d4d0d3e41aec38b213f062c19d078
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2021
ms.locfileid: "101844500"
---
# <a name="abstract-classes-c"></a>Soyut sınıflar (C++)

Soyut sınıflar, daha belirli sınıfların türetilebilecek genel kavramların ifadeleri olarak davranır. Soyut sınıf türünde bir nesne oluşturamazsınız. Ancak, soyut sınıf türleri için işaretçiler ve başvurular kullanabilirsiniz.

En az bir saf sanal üye işlevi bildirerek soyut bir sınıf oluşturursunuz. Bu, saf tanımlayıcı () sözdizimi kullanılarak belirtilen bir sanal işlevdir `= 0` . Soyut sınıftan türetilmiş sınıflar, saf sanal işlevi uygulamalıdır ya da soyut sınıflardır.

[Sanal işlevlerde](../cpp/virtual-functions.md)sunulan örneği göz önünde bulundurun. Sınıfının amacı `Account` genel işlevselliği sağlamaktır, ancak türündeki nesnelerin `Account` yararlı olması çok genel olabilir. Bu `Account` , soyut bir sınıf için iyi bir aday olan anlamına gelir:

```cpp
// deriv_AbstractClasses.cpp
// compile with: /LD
class Account {
public:
   Account( double d );   // Constructor.
   virtual double GetBalance();   // Obtain balance.
   virtual void PrintBalance() = 0;   // Pure virtual function.
private:
    double _balance;
};
```

Bu bildirim ile Previous arasındaki tek fark, `PrintBalance` saf belirtici () ile bildirilmiştir `= 0` .

## <a name="restrictions-on-abstract-classes"></a>Soyut sınıflarda kısıtlamalar

Soyut sınıflar için kullanılamaz:

- Değişkenler veya üye verileri

- Bağımsız değişken türleri

- İşlev dönüş türleri

- Açık dönüştürme türleri

Bir soyut sınıf için Oluşturucu doğrudan veya dolaylı olarak saf bir sanal işlevi çağırırsa, sonuç tanımsızdır. Bununla birlikte, soyut sınıflara yönelik oluşturucular ve yıkıcılar diğer üye işlevlerini çağırabilir.

## <a name="defined-pure-virtual-functions"></a>Tanımlı saf sanal işlevler

Soyut sınıflarda saf sanal işlevler *tanımlanabilir* veya bir uygulamaya sahip olabilir. Yalnızca tam sözdizimini kullanarak bu işlevleri çağırabilirsiniz:

*soyut-sınıf-adı*::*işlev-adı*()

Tanımlı saf sanal işlevler, temel sınıfları saf sanal yıkıcıları içeren sınıf hiyerarşileri tasarladığınızda yararlıdır. Bunun nedeni, temel sınıf yıkıcıları her zaman nesne yok etme sırasında çağrılır. Aşağıdaki örneği inceleyin:

```cpp
// deriv_RestrictionsOnUsingAbstractClasses.cpp
// Declare an abstract base class with a pure virtual destructor.
// It's the simplest possible abstract class.
class base
{
public:
    base() {}
    virtual ~base() = 0 {}; // pure virtual, and defined!
};

class derived : public base
{
public:
    derived() {}
    ~derived() {}
};

int main()
{
    derived aDerived; // destructor called when it goes out of scope
}
```

Örnek, satır içi tanımını gösterir `~base()` , ancak kullanarak sınıfı dışında da tanımlayabilirsiniz `base::~base() {}` .

Nesne `aDerived` kapsam dışına geçtiğinde, sınıfının yıkıcısı `derived` çağırılır. Derleyici, yıkıcı sonrasında sınıf için yıkıcıyı örtük olarak çağırmak için kod üretir `base` `derived` . Saf sanal işlev için boş uygulama, `~base` işlev için en az bir uygulamanın mevcut olmasını sağlar. Bu olmadan, bağlayıcı örtük çağrı için çözülmemiş bir dış sembol hatası oluşturur.

> [!NOTE]
> Yukarıdaki örnekte, `base::~base` saf sanal işlevi `derived::~derived` öğesinden örtük olarak çağrılır. Saf sanal işlevleri açıkça tam bir üye işlevi adı kullanarak çağırmak da mümkündür. Bu tür işlevlerin bir uygulamaya sahip olması veya çağrının bağlantı sırasında bir hatayla sonuçlamasıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
