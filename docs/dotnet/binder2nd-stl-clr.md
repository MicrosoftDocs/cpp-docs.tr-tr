---
title: binder2nd (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd function [STL/CLR]
ms.assetid: f4be8722-1778-4cb9-9ec7-ad1443f6899f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b22c435952602afe96a7f310b931bda8a5bbb13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="binder2nd-stlclr"></a>binder2nd (STL/CLR)
Şablon sınıfı tek bağımsız değişkenli functor açıklar, çağrıldığında, sağlanan ilk bağımsız değişken ve saklı ikinci bağımsız değişken adında kendi saklı iki bağımsız değişken functor döndürür. Kullandığınız depolanan functor bakımından işlevi nesnesi belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Fun  
 Saklı functor türü.  
  
## <a name="member-functions"></a>Üye İşlevleri  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|delegate_type|Genel temsilci türü.|  
|first_argument_type|Functor ilk bağımsız değişken türü.|  
|result_type|Functor sonuç türü.|  
|second_argument_type|Functor ikinci bağımsız değişken türü.|  
|stored_function_type|Functor türü.|  
  
|Üye|Açıklama|  
|------------|-----------------|  
|binder2nd|Functor oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|operator()|İstenen işlev hesaplar.|  
|işleç delegate_type^()|Bir temsilci functor çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı iki bağımsız değişken functor ve ikinci bir bağımsız değişken depolayan bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlevi olarak zaman çağrıldığını böylece, sağlanan ilk bağımsız değişken ve saklı ikinci bağımsız değişkeni ile saklı functor çağırma sonucunu döndürür.  
  
 Nesne türü olan bir işlev bağımsız değişkeni geçebilen `delegate_type^` ve uygun şekilde dönüştürülür.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_binder2nd.cpp   
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
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)