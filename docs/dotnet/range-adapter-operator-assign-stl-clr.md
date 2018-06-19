---
title: range_adapter::operator (STL/CLR) = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::operator=
- cliext::range_adapter::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: ac378ccc-a42c-4a90-bc27-9b416bee7fa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6e39d3dd95a1a1c1acd8df31b65d4d3afc1f0a7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161973"
---
# <a name="rangeadapteroperator-stlclr"></a>range_adapter::operator= (STL/CLR)
Saklı yineleyici çifti yerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
range_adapter<Iter>% operator=(range_adapter<Iter>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için bağdaştırıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları `right` nesnesine sonra döndürür `*this`. Saklı yineleyici çifti içinde depolanan yineleyici çiftinin bir kopya ile değiştirmek için kullandığınız `right`.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_range_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Myrange c1(d1.begin(), d1.end());   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myrange c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/bağdaştırıcısı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)