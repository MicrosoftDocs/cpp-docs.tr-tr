---
title: "Sanal işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a1a6fd82a042ab29ad9216746dcabce9e9ed15f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="virtual-functions"></a>Sanal İşlevler
Sanal işlevi türetilmiş sınıflarda yeniden beklediğiniz bir üye işlevdir. Bir işaretçi veya temel sınıf başvurusu kullanarak bir türetilmiş sınıf nesnesi başvurduğunuzda, bu nesne için sanal bir işlevi çağırmak ve işlevi türetilen sınıfın sürümünü çalıştırın.  
  
 Sanal işlevler doğru işlev bağımsız olarak işlev çağrısı yapmak için kullanılan ifade bir nesne için çağrıldığından emin olun.  
  
 Bir temel sınıf olarak bildirilen bir işlev içerdiğini varsayalım [sanal](../cpp/virtual-cpp.md) ve aynı işlevi türetilmiş bir sınıf tanımlar. Bir işaretçi veya başvuru için temel sınıfı kullanılarak çağrılır olsa bile işlevi türetilmiş sınıfından türetilen sınıfın nesneleri için çağrılır. Aşağıdaki örnek uygulaması sağlayan bir temel sınıfı gösterir `PrintBalance` işlevi ve iki türetilmiş sınıflar  
  
```  
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
  
 Önceki kodda, çağrıları `PrintBalance` nesne dışında aynı `pAccount` işaret eder. Çünkü `PrintBalance` sanal, her nesne adında için tanımlanan işlevi sürümü. `PrintBalance` İşlevi türetilmiş sınıflarda `CheckingAccount` ve `SavingsAccount` "temel sınıfı işlevinde geçersiz kılma" `Account`.  
  
 Bir sınıf geçersiz kılma uygulaması sağlamaz bildirilmiş `PrintBalance` işlevi, temel sınıf varsayılan uygulamasından `Account` kullanılır.  
  
 Yalnızca kendi türünün aynı olduğu durumlarda işlevleri türetilmiş sınıflarda temel sınıflar içinde sanal işlevleri geçersiz kılar. Türetilmiş bir sınıf işlevinde sanal işlevi dönüş türünün yalnızca temel bir sınıfında farklı olamaz; bağımsız değişken listesi de farklı olmalıdır.  
  
 Bir işlev işaretçileri veya başvuruları kullanarak çağrılırken, aşağıdaki kurallar geçerlidir:  
  
-   Bir sanal işlev çağrısı için çağırıldığı nesnenin temel alınan türü göre çözümlenir.  
  
-   Sanal olmayan bir işlev çağrısı işaretçi veya başvuru türüne göre çözümlenir.  
  
 Aşağıdaki örnekte nasıl sanal ve sanal olmayan işlevler işaretçileri çağrıldığında davranır:  
  
```  
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
  
```  
Derived::NameOf  
Invoked by Base  
Derived::NameOf  
Invoked by Derived  
```  
  
 Olup olmamasına bakılmaksızın unutmayın `NameOf` işlev işaretçisi aracılığıyla çağrıldığında `Base` veya gösteren bir işaretçi `Derived`, işlevi için çağırır `Derived`. İşlevi için çağırır `Derived` çünkü `NameOf` bir sanal işleve ve her ikisi de `pBase` ve `pDerived` türünde bir nesneye işaret `Derived`.  
  
 Sanal işlevler yalnızca sınıf türleri nesneler için adlandırılır çünkü olarak genel veya statik işlevler bildiremezsiniz **sanal**.  
  
 **Sanal** anahtar sözcüğü, türetilen bir sınıfta geçersiz kılma bildirme işlevleri zaman kullanılabilir, ancak gerekli değildir; sanal işlevleri geçersiz kılma sanal her zaman.  
  
 Bir taban sınıf içinde sanal işlevleri kullanılarak bildirilir sürece tanımlanmalıdır *belirticisi saf*. (Saf sanal işlevler hakkında daha fazla bilgi için bkz: [soyut sınıflar](../cpp/abstract-classes-cpp.md).)  
  
 Kapsam çözümü işleci kullanılarak işlev adı açıkça niteleme tarafından sanal işlev çağrısı mekanizması gizlenebilir (`::`). Önceki örneği ilgili göz önünde bulundurun `Account` sınıfı. Çağrılacak `PrintBalance` taban sınıf içinde aşağıdaki gibi kod kullanın:  
  
```  
CheckingAccount *pChecking = new CheckingAccount( 100.00 );  
  
pChecking->Account::PrintBalance();  //  Explicit qualification.  
  
Account *pAccount = pChecking;  // Call Account::PrintBalance  
  
pAccount->Account::PrintBalance();   //  Explicit qualification.  
```  
  
 Her iki çağrıları `PrintBalance` önceki örnekte sanal işlev çağrısı mekanizması gösterme.  
  
