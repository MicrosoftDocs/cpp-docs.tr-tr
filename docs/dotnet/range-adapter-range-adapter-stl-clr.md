---
title: range_adapter::range_adapter (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::range_adapter::range_adapter
dev_langs: C++
helpviewer_keywords: range_adapter member [STL/CLR]
ms.assetid: b16af13f-3358-4e82-927d-d0d4986bcb18
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f886d05227e4b1092599899aa140cd9d2ee2f77d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rangeadapterrangeadapter-stlclr"></a>range_adapter::range_adapter (STL/CLR)
Bir bağdaştırıcı nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Sarmalamak için ilk yineleyici.  
  
 Son  
 Sarmalamak için ikinci yineleyici.  
  
 sağ  
 Kopyalamak için nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `range_adapter();`  
  
 oluşturulan varsayılan yineleyiciler saklı yineleyici çiftiyle başlatır.  
  
 Oluşturucusu:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 depolanan çifti kopyalayarak saklı yineleyici çifti başlatır `right`.  
  
 Oluşturucusu:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 depolanan çifti kopyalayarak saklı yineleyici çifti başlatır `*right`.  
  
 Oluşturucusu:  
  
 `range_adapter(Iter^ first, last);`  
  
 saklı yineleyici çifti ile başlatır `first` ve `last`.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_range_adapter_construct.cpp   
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
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/bağdaştırıcısı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [range_adapter::operator (STL/CLR) =](../dotnet/range-adapter-operator-assign-stl-clr.md)