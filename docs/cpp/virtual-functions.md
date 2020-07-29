---
title: Sanal İşlevler
ms.date: 09/10/2019
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
ms.openlocfilehash: 4296d66af8f8bb9aed4946d6dc57871f447108d2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231045"
---
# <a name="virtual-functions"></a>Sanal İşlevler

Sanal işlev, türetilmiş sınıflarda yeniden tanımlanmasını düşündüğünüz bir üye işlevdir. Türetilmiş bir sınıf nesnesine bir işaretçi veya temel sınıfa yönelik bir başvuru kullanarak başvurduğunuzda, bu nesne için bir sanal işlev çağırabilir ve işlevin türetilmiş sınıfının sürümünü çalıştırabilirsiniz.

Sanal işlevler, işlev çağrısını yapmak için kullanılan ifadeye bakılmaksızın bir nesne için doğru işlevin çağrıldığından emin olur.

Bir temel sınıfın [sanal](../cpp/virtual-cpp.md) olarak bildirildiği bir işlev içerdiğini ve türetilmiş bir sınıfın aynı işlevi tanımladığını varsayalım. Türetilmiş sınıftan işlev, bir işaretçi veya temel sınıfa başvuru kullanılarak çağrılsa bile türetilmiş sınıfın nesneleri için çağrılır. Aşağıdaki örnekte, `PrintBalance` işlevinin ve iki türetilmiş sınıfın bir uygulamasını sağlayan bir temel sınıf gösterilmektedir

```cpp
// deriv_VirtualFunctions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Account {
public:
   Account( double d ) { _balance = d; }
   virtual ~Account() {}
   virtual double GetBalance() { return _balance; }
   virtual void PrintBalance() { cerr << "Error. Balance not available for base type." << endl; }
private:
    double _balance;
};

class CheckingAccount : public Account {
public:
   CheckingAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Checking account balance: " << GetBalance() << endl; }
};

class SavingsAccount : public Account {
public:
   SavingsAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Savings account balance: " << GetBalance(); }
};

int main() {
   // Create objects of type CheckingAccount and SavingsAccount.
   CheckingAccount checking( 100.00 );
   SavingsAccount  savings( 1000.00 );

   // Call PrintBalance using a pointer to Account.
   Account *pAccount = &checking;
   pAccount->PrintBalance();

   // Call PrintBalance using a pointer to Account.
   pAccount = &savings;
   pAccount->PrintBalance();
}
```

Önceki kodda, öğesine yapılan çağrılar `PrintBalance` , nesne işaret noktaları hariç, ile aynıdır `pAccount` . `PrintBalance`Sanal olduğundan, her bir nesne için tanımlanan işlevin sürümü çağrılır. `PrintBalance`Türetilmiş sınıflardaki işlev `CheckingAccount` ve `SavingsAccount` temel sınıftaki işlevi "geçersiz kıl" `Account` .

Bir sınıf, işlevin geçersiz kılan bir uygulamasını sağlamayan bildirilirse `PrintBalance` , temel sınıftan varsayılan uygulama `Account` kullanılır.

Türetilmiş sınıflardaki işlevler, yalnızca türleri aynı olduğunda, taban sınıflardaki sanal işlevleri geçersiz kılar. Türetilmiş sınıftaki bir işlev, yalnızca dönüş türündeki bir taban sınıftaki sanal işlevden farklı olamaz; bağımsız değişken listesi de farklı olmalıdır.

Bir işlevi işaretçiler veya başvurular kullanarak çağırırken aşağıdaki kurallar geçerlidir:

- Bir sanal işleve yapılan çağrı, çağrıldığı nesnenin temel türüne göre çözümlenir.

- Sanal olmayan bir işleve yapılan çağrı, işaretçi veya başvuru türüne göre çözümlenir.

Aşağıdaki örnek, işaretçilerle çağrıldığında sanal ve sanal olmayan işlevlerin nasıl davranacağını gösterir:

```cpp
// deriv_VirtualFunctions2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base {
public:
   virtual void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Base::NameOf() {
   cout << "Base::NameOf\n";
}

void Base::InvokingClass() {
   cout << "Invoked by Base\n";
}

class Derived : public Base {
public:
   void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Derived::NameOf() {
   cout << "Derived::NameOf\n";
}

void Derived::InvokingClass() {
   cout << "Invoked by Derived\n";
}

int main() {
   // Declare an object of type Derived.
   Derived aDerived;

   // Declare two pointers, one of type Derived * and the other
   //  of type Base *, and initialize them to point to aDerived.
   Derived *pDerived = &aDerived;
   Base    *pBase    = &aDerived;

   // Call the functions.
   pBase->NameOf();           // Call virtual function.
   pBase->InvokingClass();    // Call nonvirtual function.
   pDerived->NameOf();        // Call virtual function.
   pDerived->InvokingClass(); // Call nonvirtual function.
}
```

```Output
Derived::NameOf
Invoked by Base
Derived::NameOf
Invoked by Derived
```

`NameOf`İşlevin işaretçisi veya işaretçisi aracılığıyla çağrılıp çağrılmasından bağımsız olarak `Base` `Derived` , işlevini çağırır `Derived` . İçin işlevini çağırır `Derived` çünkü `NameOf` bir sanal işlevdir ve her ikisi de `pBase` `pDerived` türünde bir nesneye işaret edilir `Derived` .

Sanal işlevler yalnızca sınıf türündeki nesneler için çağrıldığından, genel veya statik işlevleri olarak bildiremezsiniz **`virtual`** .

**`virtual`** Anahtar sözcüğü, türetilmiş bir sınıfta geçersiz kılma işlevleri bildirirken kullanılabilir, ancak bu gerekli değildir; sanal işlevlerin geçersiz kılmaları her zaman sanal olur.

Bir temel sınıftaki sanal işlevler, *saf belirtici*kullanılarak bildirilemediği müddetçe tanımlanmalıdır. (Saf sanal işlevler hakkında daha fazla bilgi için bkz. [soyut sınıflar](../cpp/abstract-classes-cpp.md).)

Sanal işlev çağrı mekanizması, kapsam çözümleme işleci () kullanılarak işlev adını açıkça niteleyerek gizlenebilir `::` . Sınıfını içeren önceki örneği göz önünde bulundurun `Account` . `PrintBalance`Taban sınıfında çağırmak için, aşağıdaki gibi bir kod kullanın:

```cpp
CheckingAccount *pChecking = new CheckingAccount( 100.00 );

pChecking->Account::PrintBalance();  //  Explicit qualification.

Account *pAccount = pChecking;  // Call Account::PrintBalance

pAccount->Account::PrintBalance();   //  Explicit qualification.
```

`PrintBalance`Yukarıdaki örnekte ' de yapılan çağrılar, sanal işlev çağırma mekanizmasını bastırır.
