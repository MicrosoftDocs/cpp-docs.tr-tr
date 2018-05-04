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
ms.openlocfilehash: b34be19c5fe67c087579e3d1cf0643d5afd71dc5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-member-functions"></a>Üye İşlevlerine Genel Bakış
Statik ya da statik olmayan üye işlevleri. Statik üye işlevleri Hayır örtük sahip olduğundan statik üye işlevleri davranışını diğer üye işlevleri farklı **bu** bağımsız değişkeni. Statik olmayan üye işlevleri sahip bir **bu** işaretçi. Üye işlevleri, statik ya da statik olmayan, veya bir sınıf bildiriminin dışında tanımlanabilir.  
  
 Üye işlevi içinde sınıf bildirimi tanımlanırsa, bir satır içi işlev olarak kabul edilir ve sınıf adını işlevi adıyla nitelemek için gerek yoktur. Sınıf bildirimleri içinde tanımlanan işlevleri zaten satır içi işlevler kabul edilir, ancak kullanabilirsiniz **satır içi** belge kodu anahtar sözcük.  
  
 Sınıf bildirimi içinde bir işlev bildirme örneği aşağıdaki gibidir:  
  
```  
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
  
 Üye işlevin tanımı sınıf bildiriminin dışında ise, yalnızca bu açıkça olarak bildirilirse satır içi işlev işlem görür **satır içi**. Ayrıca, tanımında işlev adı kapsam çözümü işleci kullanılarak sınıfı adıyla nitelenmelidir (`::`).  
  
 Aşağıdaki örnek sınıfı önceki bildirimine aynıdır `Account`dışında `Deposit` işlevi sınıf bildiriminin dışında tanımlanır:  
  
```  
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
>  Üye işlevleri sınıf bildirimi içinde veya ayrı olarak tanımlanabilir rağmen sınıf tanımlandıktan sonra hiçbir üye işlevleri bir sınıfa eklenebilir.  
  
 Üye işlevleri içeren sınıfları birçok bildirimleri olabilir, ancak üye işlevleri yalnızca tek bir tanım bir program olması gerekir. Birden çok tanımları bağlantı zaman bir hata iletisine neden olur. Bir sınıf satır içi işlev tanımları içeriyorsa, işlev tanımları "tek bir tanım" kuralın izlemek için aynı olmalıdır.  
  
