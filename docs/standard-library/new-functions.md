---
title: "&lt;Yeni&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: b22177cf641fca8de8d6f6e59b5e7e25caea8b32
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltnewgt-functions"></a>&lt;Yeni&gt; işlevleri
|||  
|-|-|  
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|  
  
##  <a name="nothrow"></a>  nothrow  
 Bir bağımsız değişken olarak kullanılacak bir nesneyi sağlar `nothrow` sürümleri **yeni** ve **silmek**.  
  
```  
extern const std::nothrow_t nothrow;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne parametre türüyle eşleşecek şekilde işlevi bağımsız değişken olarak kullanılan [std::nothrow_t](../standard-library/nothrow-t-structure.md).  
  
### <a name="example"></a>Örnek  
  Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci &#91; &#93;](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.  
  
##  <a name="set_new_handler"></a>  set_new_handler  
 Ne zaman çağrılacak olan bir kullanıcı işlevi yükler `operator new` bellek ayıramadı, denemesi başarısız olur.  
  
```  
new_handler set_new_handler(new_handler Pnew) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `Pnew`  
 Yüklenecek new_handler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 ilk çağrıda ve önceki 0 `new_handler` sonraki çağrılar üzerinde.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev depoları `Pnew` statik olarak [yeni işleyicisi](../standard-library/new-typedefs.md#new_handler) sakladığı, işaretçi ardından işaretçiyi daha önce depolanan değeri döndürür. Yeni işleyici tarafından kullanılan [new işleci](../standard-library/new-operators.md#op_new)( **size_t**).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// new_set_new_handler.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
void __cdecl newhandler( )  
{  
   cout << "The new_handler is called:" << endl;  
   throw bad_alloc( );  
   return;  
}  
  
int main( )   
{  
   set_new_handler (newhandler);  
   try  
   {  
      while ( 1 )   
      {  
         new int[5000000];  
         cout << "Allocating 5000000 ints." << endl;  
      }  
   }  
   catch ( exception e )  
   {  
      cout << e.what( ) << endl;  
   }  
}  
```  
  
```Output  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
The new_handler is called:  
bad allocation  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Yeni >](../standard-library/new.md)

