---
title: Üye işlevlerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 409f896e7b2c345d1558700f86182d06793f543d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016435"
---
# <a name="overview-of-member-functions"></a>Üye İşlevlerine Genel Bakış

Statik veya statik olmayan üye işlevleri. Statik üye işlevleri Hayır örtük sahip diğer üye işlevleri statik üye işlevleri davranışını farklıdır **bu** bağımsız değişken. Statik olmayan üye işlevleri bir **bu** işaretçi. Üye işlevleri, statik veya statik olmayan, içinde ya da sınıf bildirimi dışında tanımlanabilir.

Üye işlevi bir sınıf bildirimi içinde tanımlanmış olması durumunda, satır içi işlev kabul edilir ve sınıf adını işlevi adıyla nitelemeniz gerek yoktur. Sınıf bildirimi içinde tanımlanmış işlevler zaten satır içi işlevleri kabul edilir olsa da, kullanabileceğiniz **satır içi** belge koda anahtar sözcüğü.

Bir sınıf bildirimi içinde bir işlevi bildirmek, bir örnek aşağıda verilmiştir:

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

Sınıf bildirimi dışında bir üye işlevin tanımı ise yalnızca onu açıkça olarak bildirilirse, satır içi işlev kabul edilir **satır içi**. Ayrıca, tanımında işlev adı kapsam çözümleme işlecini kullanarak, bir sınıf adı ile nitelenmelidir (`::`).

Aşağıdaki örnek, önceki sınıfının bildirimi için aynıdır `Account`dışında `Deposit` işlevleri sınıf bildirimi dışında tanımlanır:

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
>  Üye işlevleri sınıf bildirimi içinde veya ayrı ayrı tanımlanabiliyor olsa da, sınıf tanımlandıktan sonra hiçbir üye işlevi bir sınıfa eklenebilir.

Üye işlevleri içeren sınıflar birçok bildirimleri olabilir, ancak üye işlevleri bir programa sadece bir tanım olmalıdır. Birden çok tanım bağlantı zamanında bir hata iletisine neden olur. İşlev tanımları, satır içi işlev tanımları bir sınıf içeriyorsa, bu "bir tanımı" kuralı gözlemlemek için aynı olmalıdır.