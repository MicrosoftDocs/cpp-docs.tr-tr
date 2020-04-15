---
title: Üye İşlevlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: 6dec4ee53cd840c47d76ac0579daca710b0eeb68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358405"
---
# <a name="overview-of-member-functions"></a>Üye İşlevlerine Genel Bakış

Üye işlevler statik veya statik değildir. Statik üye işlevlerin davranışı diğer üye işlevlerden farklıdır, çünkü statik üye işlevlerde **bu** bağımsız değişken örtük değildir. Statik olmayan üye işlevler **bu** işaretçiye sahiptir. Statik veya statik olmayan üye işlevler sınıf bildirimiiçinde veya dışında tanımlanabilir.

Bir üye işlev sınıf bildirimi içinde tanımlanırsa, satır içi işlev olarak kabul edilir ve işlev adını sınıf adı ile nitelemenize gerek yoktur. Sınıf bildirimleri içinde tanımlanan işlevler zaten satır içi işlevler olarak kabul edilebilse de, kod belgelemek için **satır içi** anahtar sözcüğü kullanabilirsiniz.

Sınıf bildirimi içinde bir işlev bildiren bir örnek aşağıdaki gibidir:

```cpp
// overview_of_member_functions1.cpp
class Account
{
public:
    // Declare the member function Deposit within the declaration
    //  of class Account.
    double Deposit( double HowMuch )
    {
        balance += HowMuch;
        return balance;
    }
private:
    double balance;
};

int main()
{
}
```

Bir üye işlevin tanımı sınıf bildiriminin dışındaysa, yalnızca **satır dışı**olarak açıkça beyan edilirse satır içinde işlev olarak kabul edilir. Buna ek olarak, tanımdaki işlev adı kapsam çözümlemesi (`::`) kullanılarak sınıf adı ile nitelikli olmalıdır.

Aşağıdaki örnek, `Account` `Deposit` işlevin sınıf bildirimi dışında tanımlanması dışında, sınıfın önceki bildirimiyle aynıdır:

```cpp
// overview_of_member_functions2.cpp
class Account
{
public:
    // Declare the member function Deposit but do not define it.
    double Deposit( double HowMuch );
private:
    double balance;
};

inline double Account::Deposit( double HowMuch )
{
    balance += HowMuch;
    return balance;
}

int main()
{
}
```

> [!NOTE]
> Üye işlevler bir sınıf bildirimi içinde veya ayrı ayrı tanımlanabilse de, sınıf tanımlandıktan sonra sınıfa üye işlev ler eklenebilir.

Üye işlevler içeren sınıfların birçok bildirimi olabilir, ancak üye işlevlerin kendileri bir programda yalnızca bir tanım olmalıdır. Birden çok tanım, bağlantı zamanında bir hata iletisi neden olur. Bir sınıf satır içinde işlev tanımları içeriyorsa, işlev tanımları bu "tek tanım" kuralını gözlemlemek için aynı olmalıdır.
