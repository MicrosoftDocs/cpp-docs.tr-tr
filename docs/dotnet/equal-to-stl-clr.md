---
title: equal_to (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::equal_to
dev_langs: C++
helpviewer_keywords: equal_to function [STL/CLR]
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 264236c68e7d6f83f569692893c378c6d8fc441a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="equalto-stlclr"></a>equal_to (STL/CLR)
Şablon sınıfı bir functor açıklar yalnızca ilk bağımsız değişken ikinci eşitse çağrıldığında, true değerini döndürür. Kullandığınız kendi bağımsız değişken türü bakımından işlevi nesnesi belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Arg  
 Bağımsız değişken türü.  
  
## <a name="member-functions"></a>Üye İşlevleri  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|delegate_type|Genel temsilci türü.|  
|first_argument_type|Functor ilk bağımsız değişken türü.|  
|result_type|Functor sonuç türü.|  
|second_argument_type|Functor ikinci bağımsız değişken türü.|  
  
|Üye|Açıklama|  
|------------|-----------------|  
|equal_to|Functor oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|operator()|İstenen işlev hesaplar.|  
|işleç delegate_type^()|Bir temsilci functor çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı iki bağımsız değişken functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlevi olarak zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinci eşit olup olmadığını true değerini döndürür.  
  
 Nesne türü olan bir işlev bağımsız değişkeni geçebilen `delegate_type^` ve uygun şekilde dönüştürülür.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)