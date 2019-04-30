---
title: Sanal İşlevler
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
ms.openlocfilehash: 07dfd8a602dca93c89a078b2eb69e04cf9d4a7a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393850"
---
# <a name="virtual-functions"></a>Sanal İşlevler

Bir sanal işlev türetilmiş sınıflarda tanımlanmasını beklediğiniz bir üye işlevidir. Bir türetilmiş sınıf nesnesine bir işaretçi veya başvuru temel sınıfına kullanarak başvurduğunuzda, bu nesne için bir sanal işlev çağrısı ve işlevin türetilmiş sınıfın sürümünü yürütün.

Sanal işlevler işlev çağrısını yapmak için kullanılan ifade bağımsız olarak bir nesne için doğru işlevi çağrılır emin olun.

Bir temel sınıf olarak bildirilen bir işlevi içerdiğini varsayın [sanal](../cpp/virtual-cpp.md) ve aynı işlevi türetilmiş bir sınıf tanımlar. Bir işaretçi veya başvuru temel sınıfına kullanarak çağrılırsa bile işlevi türetilmiş sınıftan türetilen sınıfın nesneleri için çağrılır. Aşağıdaki örnek uygulaması sağlayan bir temel sınıf gösterir `PrintBalance` işlevi ve iki türetilmiş sınıflar

```cpp
// deriv_VirtualFunctions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Account {
public:
   Account( double d ) { _balance = d; }
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
   CheckingAccount *pChecking = new CheckingAccount( 100.00 ) ;
   SavingsAccount  *pSavings  = new SavingsAccount( 1000.00 );

   // Call PrintBalance using a pointer to Account.
   Account *pAccount = pChecking;
   pAccount->PrintBalance();

   // Call PrintBalance using a pointer to Account.
   pAccount = pSavings;
   pAccount->PrintBalance();
}
```

Önceki kodda, çağrıları `PrintBalance` nesnesinin aynı `pAccount` işaret eder. Çünkü `PrintBalance` sanal, her nesne adı için tanımlanan işlev sürümü. `PrintBalance` İşlevi türetilmiş sınıflarda `CheckingAccount` ve `SavingsAccount` "taban sınıf işlevinde geçersiz kılmayı" `Account`.

Geçersiz kılma uygulaması sağlamaz bir sınıf olarak tanımlanıp tanımlanmadığını `PrintBalance` işlevi, varsayılan uygulama temel sınıftan `Account` kullanılır.

Yalnızca kendi türünün aynı olduğu durumlarda işlevleri türetilmiş sınıflarda temel sınıflardaki sanal işlevleri geçersiz kılar. Türetilen bir sınıfta bir işlev bir sanal işlev dönüş türü yalnızca temel sınıfındaki farklı olamaz; bağımsız değişken listesi de farklı olmalıdır.

İşaretçiler veya başvurular kullanarak bir işlev çağrılırken, aşağıdaki kurallar geçerlidir:

- Bir sanal işlev çağrısı için çağırıldığı nesnenin temel türüne göre çözümlenir.

- Sanal olmayan bir işlev çağrısı, işaretçi veya başvuru türüne göre çözümlenir.

Aşağıdaki örnekte nasıl sanal ve sanal olmayan işlevleri işaretçileri çağrıldığında davranır:

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

### <a name="output"></a>Çıkış

```Output
Derived::NameOf
Invoked by Base
Derived::NameOf
Invoked by Derived
```

Olup olmamasına bakılmaksızın unutmayın `NameOf` işaretçi üzerinden işlevin çağrıldığı `Base` veya işaretçi `Derived`, işlevi için çağrı `Derived`. İşlevi için çağrı `Derived` çünkü `NameOf` sanal bir işlev ve her ikisi de `pBase` ve `pDerived` türündeki bir nesneye işaret `Derived`.

Sanal işlevler yalnızca sınıf türü nesneler için çağrılmadığından, genel veya statik işlevler olarak bildiremezsiniz **sanal**.

**Sanal** anahtar sözcüğü kullanılabilir olduğunda, türetilen bir sınıfta geçersiz kılma bildirme çalışır ancak gerekli değildir; sanal işlevleri geçersiz kılmalarına sanal her zaman.

Bir temel sınıf sanal işlevler kullanılarak bildirilirler sürece tanımlanmalıdır *saf tanımlayıcı*. (Saf sanal işlevler hakkında daha fazla bilgi için bkz: [soyut sınıflar](../cpp/abstract-classes-cpp.md).)

Sanal işlev çağrısı mekanizması, kapsam çözümleme işleci kullanarak işlevi adı açıkça uygun tarafından gizlenebilir (`::`). Önceki örnekte ilgili göz önünde bulundurun `Account` sınıfı. Çağrılacak `PrintBalance` taban sınıfında, aşağıdaki gibi bir kod kullanın:

```cpp
CheckingAccount *pChecking = new CheckingAccount( 100.00 );

pChecking->Account::PrintBalance();  //  Explicit qualification.

Account *pAccount = pChecking;  // Call Account::PrintBalance

pAccount->Account::PrintBalance();   //  Explicit qualification.
```

Her iki çağrıları `PrintBalance` önceki örnekte, sanal işlev çağrısı mekanizması gösterme.