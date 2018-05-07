---
title: Vector::resize (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::resize
dev_langs:
- C++
helpviewer_keywords:
- resize member [STL/CLR]
ms.assetid: a3556fbc-67d9-463a-9ffc-cb43ee15657f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f7327b62906746ef3bb561d88f8c6ddc2134aa65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorresize-stlclr"></a>vector::resize (STL/CLR)
Öğe sayısını değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parametreler  
 new_size  
 Denetimli sırası yeni büyüklüğü.  
  
 VAL  
 Doldurma öğesinin değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri emin [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` henceforth döndürür `new_size`. Uzun denetimli dizisi yapmanız gerekiyorsa, ilk üye işlevi değer ile öğeleri ekler `value_type()`değere sahip öğeleri ikinci üye işlevi ekler yaparken `val`. Daha kısa denetimli sıra yapmak için her iki üye işlevleri etkili bir şekilde son öğe silme [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` kez. Denetimli sırası boyutu olduğundan emin olmak için kullandığınız `new_size`, kırpma ya da geçerli denetimli dizisi doldurma tarafından.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)   
 [Vector::ERASE (STL/CLR)](../dotnet/vector-erase-stl-clr.md)   
 [vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)