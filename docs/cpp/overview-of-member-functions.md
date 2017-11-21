---
title: "Üye işlevlerine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cfc355a58ae87bcb32d7abd72f1ff5cb6e980a6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
