---
title: Soyut Sınıflar (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- classes [C++], abstract
- base classes [C++], abstract classes [C++]
- abstract classes [C++]
- derived classes [C++], abstract classes [C++]
ms.assetid: f0c5975b-39de-4d68-9640-6ce57f4632e6
ms.openlocfilehash: 2ea9d3765f65434cb738c2b7c53f9499bba24545
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181700"
---
# <a name="abstract-classes-c"></a>Soyut Sınıflar (C++)

Soyut sınıflar, daha belirli sınıfların türetilebilecek genel kavramların ifadeleri olarak davranır. Soyut sınıf türünde bir nesne oluşturamazsınız; Ancak, soyut sınıf türleri için işaretçiler ve başvurular kullanabilirsiniz.

En az bir saf sanal işlev içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilmiş sınıflar, saf sanal işlevi uygulamalıdır ya da soyut sınıflardır.

[Sanal işlevlerde](../cpp/virtual-functions.md)sunulan örneği göz önünde bulundurun. `Account` sınıfı amacı genel işlevselliği sağlamaktır, ancak `Account` türündeki nesnelerin yararlı olması çok genel bir seçenektir. Bu nedenle, `Account` soyut bir sınıf için iyi bir adaydır:

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

Bu bildirim ile öncekiyle arasındaki tek fark, `PrintBalance` saf belirticiyle (`= 0`) bildirildiği bir değer.

## <a name="restrictions-on-abstract-classes"></a>Soyut sınıflarda kısıtlamalar

Soyut sınıflar şunlar için kullanılamaz:

- Değişkenler veya üye verileri

- Bağımsız değişken türleri

- İşlev dönüş türleri

- Açık dönüştürme türleri

Başka bir kısıtlama da soyut bir sınıfa yönelik bir oluşturucu doğrudan veya dolaylı olarak saf bir sanal işlevi çağırıyorsa, sonucun tanımsız olmasıdır. Bununla birlikte, soyut sınıflara yönelik oluşturucular ve yıkıcılar diğer üye işlevlerini çağırabilir.

Saf sanal işlevler soyut sınıflar için tanımlanabilir, ancak doğrudan yalnızca şu sözdizimi kullanılarak çağrılabilir:

*soyut-sınıf-adı*::*işlev-adı*()

Bu, temel sınıf yıkıcıları her zaman bir nesne yıkılırken çağrıldığı için temel sınıfları saf sanal yıkıcılar içeren sınıf hiyerarşilerinin tasarlanmasına yardımcı olur. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// Declare an abstract base class with a pure virtual destructor.
// deriv_RestrictionsonUsingAbstractClasses.cpp
class base {
public:
    base() {}
    virtual ~base()=0;
};

// Provide a definition for destructor.
base::~base() {}

class derived:public base {
public:
    derived() {}
    ~derived(){}
};

int main() {
    derived *pDerived = new derived;
    delete pDerived;
}
```

`pDerived` tarafından işaret edilen nesne silindiğinde, `derived` sınıfına yönelik yıkıcı ve ardından `base` sınıfına yönelik yıkıcı çağrılır. Saf sanal işleve yönelik boş uygulama, işlev için en azından bazı uygulamaların var olmasını sağlar.

> [!NOTE]
> Yukarıdaki örnekte, `base::~base` saf sanal işlevi `derived::~derived` öğesinden örtük olarak çağrılır. Saf sanal işlevler, tam üye işlevi adı kullanılarak örtük bir şekilde çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
