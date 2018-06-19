---
title: unary_negate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unary_negate
dev_langs:
- C++
helpviewer_keywords:
- unary_negate function [STL/CLR]
ms.assetid: 83bbdd86-199c-4451-9f70-72f9ade2264a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 70ce2872e3e941df11402ccde0cb7a94b132b51c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169455"
---
# <a name="unarynegate-stlclr"></a>unary_negate (STL/CLR)
Şablon sınıfı bir functor açıklar, çağrıldığında, mantıksal döndürür, depolanan tek bağımsız değişkenli functor örneği değil. Kullandığınız depolanan functor bakımından işlevi nesnesi belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Fun>  
    ref class unary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::argument_type argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    unary_negate(Fun% functor);  
    unary_negate(unary_negate<Fun>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Fun  
 Saklı functor türü.  
  
## <a name="member-functions"></a>Üye İşlevleri  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|argument_type|Functor bağımsız değişken türü.|  
|delegate_type|Genel temsilci türü.|  
|result_type|Functor sonuç türü.|  
  
|Üye|Açıklama|  
|------------|-----------------|  
|unary_negate|Functor oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|operator()|İstenen işlev hesaplar.|  
|delegate_type ^|Bir temsilci functor çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı, başka bir tek bağımsız değişkenli functor depolayan bir tek bağımsız değişkenli functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlevi olarak zaman çağrıldığını böylece, mantıksal döndürür değil depolanan functor bağımsız değişkeni ile çağrıldı.  
  
 Nesne türü olan bir işlev bağımsız değişkeni geçebilen `delegate_type^` ve uygun şekilde dönüştürülür.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_unary_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::logical_not<int> not_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::unary_negate<cliext::logical_not<int> >(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::not1(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
1 0  
1 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [not1 (STL/CLR)](../dotnet/not1-stl-clr.md)