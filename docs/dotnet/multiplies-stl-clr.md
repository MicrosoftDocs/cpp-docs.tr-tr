---
title: "çarpar (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiplies
dev_langs: C++
helpviewer_keywords: multiplies function [STL/CLR]
ms.assetid: 76d23149-789a-48a1-89f8-9103df82a1df
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c816361e20dd571bb243b11870bd4e0571e2364e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multiplies-stlclr"></a>çarpar (STL/CLR)
Şablon sınıfı bir functor açıklar, ilk bağımsız değişken ikinci kez çağrıldığında, döndürür. Kullandığınız kendi bağımsız değişken türü bakımından işlevi nesnesi belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Arg>  
    ref class multiplies  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    multiplies();  
    multiplies(multiplies<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Arg  
 Bağımsız değişkenleri ve dönüş değeri türü.  
  
## <a name="member-functions"></a>Üye İşlevleri  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|delegate_type|Genel temsilci türü.|  
|first_argument_type|Functor ilk bağımsız değişken türü.|  
|result_type|Functor sonuç türü.|  
|second_argument_type|Functor ikinci bağımsız değişken türü.|  
  
|Üye|Açıklama|  
|------------|-----------------|  
|çarpar|Functor oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|operator()|İstenen işlev hesaplar.|  
|işleç delegate_type ^|Bir temsilci functor çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı iki bağımsız değişken functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlevi olarak zaman çağrıldığını böylece, ikinci kez ilk bağımsız değişkeni döndürür.  
  
 Nesne türü olan bir işlev bağımsız değişkeni geçebilen `delegate_type^` ve uygun şekilde dönüştürülür.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_multiplies.cpp   
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
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::multiplies<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
8 3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [böler (STL/CLR)](../dotnet/divides-stl-clr.md)   
 [mod (STL/CLR)](../dotnet/modulus-stl-clr.md)