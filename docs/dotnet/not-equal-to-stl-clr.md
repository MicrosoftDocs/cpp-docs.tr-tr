---
title: not_equal_to (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::not_equal_to
dev_langs:
- C++
helpviewer_keywords:
- not_equal_to function [STL/CLR]
ms.assetid: 1b66e0ca-eace-4672-8da9-ed16f8608bca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b8046b4723a6e4e725662db2cce9e3981155748b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136450"
---
# <a name="notequalto-stlclr"></a>not_equal_to (STL/CLR)
Şablon sınıfı bir functor açıklar yalnızca ilk bağımsız değişken ikinci eşit değilse çağrıldığında, true değerini döndürür. Kullandığınız kendi bağımsız değişken türü bakımından işlevi nesnesi belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Arg>  
    ref class not_equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    not_equal_to();  
    not_equal_to(not_equal_to<Arg>% right);  
  
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
|not_equal_to|Functor oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|operator()|İstenen işlev hesaplar.|  
|işleç delegate_type ^|Bir temsilci functor çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı iki bağımsız değişken functor açıklar. Üye işleci tanımlar `operator()` nesne bir işlevi olarak zaman çağrıldığını böylece, yalnızca ilk bağımsız değişken ikinci eşit değilse true değerini döndürür.  
  
 Nesne türü olan bir işlev bağımsız değişkeni geçebilen `delegate_type^` ve uygun şekilde dönüştürülür.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_not_equal_to.cpp   
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
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
0 1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)