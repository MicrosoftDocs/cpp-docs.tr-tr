---
title: işlevsel (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38bfbe025c92aa54956a165367b367cecc6160b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="functional-stlclr"></a>işlevsel (STL/CLR)
STL/CLR üstbilgisini `<cliext/functional>` tanımlamak için şablon sınıfları ve ilgili şablonu Temsilciler ve işlevlerini sayısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <functional>  
```  
  
## <a name="declarations"></a>Bildirimler  
  
|Temsilci|Açıklama|  
|--------------|-----------------|  
|[binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)|İki bağımsız değişken temsilcisi.|  
|[binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)|İki bağımsız değişken temsilci döndürme `void`.|  
|[unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)|Tek bağımsız değişkenli temsilcisi.|  
|[unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)|Tek bağımsız değişkenli temsilci döndürme `void`.|  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)|İki bağımsız değişken functor negate functor.|  
|[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)|İlk bağımsız değişkeni için iki bağımsız değişken functor bağlamak için functor.|  
|[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)|İkinci bağımsız değişkeni için iki bağımsız değişken functor bağlamak için functor.|  
|[divides (STL/CLR)](../dotnet/divides-stl-clr.md)|Functor bölün.|  
|[equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)|Karşılaştırma functor eşit.|  
|[greater (STL/CLR)](../dotnet/greater-stl-clr.md)|Büyük karşılaştırma functor.|  
|[greater_equal (STL/CLR)](../dotnet/greater-equal-stl-clr.md)|Büyük veya eşit karşılaştırma functor.|  
|[less (STL/CLR)](../dotnet/less-stl-clr.md)|Daha az karşılaştırma functor.|  
|[less_equal (STL/CLR)](../dotnet/less-equal-stl-clr.md)|Küçük veya eşittir karşılaştırma functor.|  
|[logical_and (STL/CLR)](../dotnet/logical-and-stl-clr.md)|Mantıksal ve functor.|  
|[logical_not (STL/CLR)](../dotnet/logical-not-stl-clr.md)|Mantıksal functor değil.|  
|[logical_or (STL/CLR)](../dotnet/logical-or-stl-clr.md)|Mantıksal OR functor.|  
|[minus (STL/CLR)](../dotnet/minus-stl-clr.md)|Functor çıkarın.|  
|[modulus (STL/CLR)](../dotnet/modulus-stl-clr.md)|Modulus functor.|  
|[multiplies (STL/CLR)](../dotnet/multiplies-stl-clr.md)|Functor çarpın.|  
|[negate (STL/CLR)](../dotnet/negate-stl-clr.md)|Tasarruflarını kendi bağımsız değişkenini döndürmesine izin functor.|  
|[not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)|Eşit değildir karşılaştırma functor.|  
|[plus (STL/CLR)](../dotnet/plus-stl-clr.md)|Functor ekleyin.|  
|[unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)|Tek bağımsız değişkenli functor negate functor.|  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)|Bir bağımsız değişken ve functor binder1st oluşturur.|  
|[bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)|Bir bağımsız değişken ve functor binder2nd oluşturur.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Unary_negate bir functor için oluşturur.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Binary_negate bir functor için oluşturur.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/işlevsel >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)