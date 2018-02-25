---
title: "İşlev nesneleri C++ Standart Kitaplığı'nda | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f426145418dab9c393e3e587939fa3e0fb5488d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="function-objects-in-the-c-standard-library"></a>C++ Standart Kitaplığı'nda işlev nesneleri
A *işlev nesnesi*, veya *functor*, operator() uygulayan herhangi bir tür. Bu işleç olarak adlandırılır *çağırma işleci* veya bazen *uygulama işleci*. C++ Standart Kitaplığı, öncelikle sıralama ölçütü kapsayıcıları ve algoritmaları olarak işlev nesneleri kullanır.  
  
 İşlev nesneleri bir düz işlev çağrısı iki ana avantaj sağlar. İlk işlev nesnesi durumu içerebilir ' dir. , Bir işlev nesnesi bir türü ve bu nedenle bir şablon parametresi kullanılabilir saniyedir.  
  
## <a name="creating-a-function-object"></a>İşlev nesnesi oluşturma  
 İşlev nesnesi oluşturmak için bir tür oluşturun ve operator(), aşağıdaki gibi uygulayın:  
  
```
class Functor  
{  
public:  
    int operator()(int a, int b)  
    {  
        return a < b;  
    }  
};  
```

 Son satırının `main` işlevi gösterir nasıl işlev nesnesi çağırın. Bu çağrı bir işlevi çağrısı gibi görünüyor, ancak gerçekte operator() Functor türü çağırma. İşlev nesnesi ve bir işlev çağırma arasındaki bu benzerlik terim işlev nesnesi nasıl ortaya çıktığını ' dir.  
  
## <a name="function-objects-and-containers"></a>İşlev nesneleri ve kapsayıcıları  
 C++ Standart Kitaplığı birkaç işlevi nesneleri içeren [ \<işlevsel >](../standard-library/functional.md) üstbilgi dosyası. Bir bu işlev nesneleri kapsayıcıları için bir sıralama ölçütü olarak kullanılır. Örneğin, `set` kapsayıcı gibi bildirilen:  
  
```  
template <class Key,  
    class Traits=less<Key>,  
    class Allocator=allocator<Key>>  
class set  
```  
  
 İkinci şablon bağımsız değişken işlev nesnesidir `less`. Bu işlev nesnesi döndüren `true` geçirilen ilk parametre, daha az ise ikinci parametre geçirildi. Bazı kapsayıcıları öğeleri sıralama olduğundan, kapsayıcı iki öğe karşılaştırılması bir yola ihtiyaç duyar ve bu işlev nesnesi kullanılarak gerçekleştirilir. Kendi işlev nesnesi oluşturma ve kapsayıcı için şablon listesinde belirterek sıralama ölçütü kapsayıcıları için tanımlayabilirsiniz.  
  
## <a name="function-objects-and-algorithms"></a>İşlev nesneleri ve algoritmaları  
 Başka bir işlev nesneleri algoritmaları kullanılır. Örneğin, `remove_if` algoritması gibi bildirilen:  
  
```  
template <class ForwardIterator, class Predicate>  
ForwardIterator remove_if(
    ForwardIterator first,  
    ForwardIterator last,  
    Predicate pred);
```  
  
 Son bağımsız değişkeni `remove_if` bir Boole değeri döndürür bir işlev nesnesidir (bir *koşulu*). İşlev nesnesi sonuç ise `true`, öğe yineleyiciler tarafından erişilen kapsayıcı kaldırılır sonra `first` ve `last`. Bildirilen işlevi nesnelerden herhangi birini kullanabilirsiniz [ \<işlevsel >](../standard-library/functional.md) bağımsız değişkeni için üstbilgi `pred` veya kendi oluşturabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

