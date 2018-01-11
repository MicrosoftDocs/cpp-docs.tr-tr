---
title: List::splice (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::splice
dev_langs: C++
helpviewer_keywords: splice member [STL/CLR]
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ba4513f8ff7e6ce51a50faacbdbe08c6fca34d01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="listsplice-stlclr"></a>list::splice (STL/CLR)
Düğümler arasındaki bağlantıları restitch.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Splice aralığını başlangıcı.  
  
 Son  
 Splice aralık sonu.  
  
 sağ  
 Gelen splice kapsayıcı.  
  
 Burada  
 Önce splice kapsayıcısında yer.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye fonksiyonu tarafından denetlenen dizisi ekler `right` gösterdiği denetlenen sıradaki öğenin önce `where`. Ayrıca tüm öğeleri kaldırır `right`. (`%right` eşit değil gerekir `this`.) Tüm bir listesinin başka bir dosyaya splice için kullanın.  
  
 İkinci üye işlevi gösterdiği öğeyi kaldırır `first` tarafından denetlenen sıradaki `right` ve denetlenen sıradaki öğenin gösterdiği önce ekler `where`. (Varsa `where` `==` `first` `||` `where` `== ++first`, hiçbir değişiklik olmaz.) Bir liste için tek bir öğe başka bir dosyaya splice için kullanın.  
  
 Üçüncü üye fonksiyonu tarafından belirtilen alt aralığı ekler [`first`, `last`) tarafından denetlenen serisinden `right` gösterdiği denetlenen sıradaki öğenin önce `where`. Tarafından denetlenen serisinden özgün alt aralığı da kaldırır `right`. (IF `right` `==` `this`, aralığı [`first`, `last`) gösterdiği öğesi içermemesi `where`.) Sıfır veya daha fazla öğe bir listeden bir değişkene başka içine splice için kullanın.  
  
## <a name="example"></a>Örnek  
  
```  
// cliext_list_splice.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [List::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)   
 [list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)