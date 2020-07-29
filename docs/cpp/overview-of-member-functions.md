---
title: Üye İşlevlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: 81fc3ae7a732171c6bddff9f584976dd747372b4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233671"
---
# <a name="overview-of-member-functions"></a>Üye İşlevlerine Genel Bakış

Üye işlevleri statik veya statik olarak statiktir. Statik üye işlevlerinin örtük bir bağımsız değişkeni olmadığından, statik üye işlevlerinin davranışı diğer üye işlevlerinden farklıdır **`this`** . Statik olmayan üye işlevlerinin bir **`this`** işaretçisi vardır. Statik veya statik olmayan üye işlevleri, sınıf bildiriminin içinde veya dışında tanımlanabilir.

Bir üye işlevi bir sınıf bildiriminde tanımlanmışsa, bir satır içi işlev olarak değerlendirilir ve işlev adını sınıf adıyla nitelemeniz gerekmez. Sınıf bildirimlerinin içinde tanımlanan işlevler zaten satır içi işlev olarak kabul edilse de, **`inline`** kodu belgelemek için anahtar sözcüğünü kullanabilirsiniz.

Bir sınıf bildirimi içindeki bir işlevi bildirme örneği aşağıdadır:

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

Bir üye işlevin tanımı sınıf bildiriminin dışındaysa, yalnızca açıkça olarak bildirilirse, satır içi işlev olarak değerlendirilir **`inline`** . Ayrıca, tanımdaki işlev adı, kapsam çözümleme işleci () kullanılarak sınıf adı ile nitelenmelidir `::` .

Aşağıdaki örnek `Account` , `Deposit` işlevin sınıf bildiriminin dışında tanımlanması dışında, sınıfının önceki bildirimiyle aynıdır:

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
> Üye işlevleri bir sınıf bildiriminde ya da ayrı ayrı tanımlanabilse de, sınıf tanımlandıktan sonra bir sınıfa hiçbir üye işlev eklenemez.

Üye işlevlerini içeren sınıflar birçok bildirime sahip olabilir, ancak üye işlevleri bir programda yalnızca bir tanıma sahip olmalıdır. Bağlantı zamanında birden çok tanım hata iletisine neden olur. Bir sınıf satır içi işlev tanımları içeriyorsa, bu "bir tanım" kuralını gözlemlemek için işlev tanımlarının aynı olması gerekir.
