---
title: TypeName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: typename_cpp
dev_langs: C++
helpviewer_keywords: typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b2f10c9815a78655857893becbfb9119e70dd378
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="typename"></a>typename
Şablon tanımlarında bilinmeyen bir tanımlayıcı türü olduğunu derleyici bir ipucu sağlar. Şablon parametresi listelerinde tür parametresi belirtmek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon tanımında bir adı bir şablon bağımsız değişken bağımlı olduğu bir tam ad ise bu anahtar sözcük kullanılması gerekir; tam adı bağımlı değilse isteğe bağlıdır. Daha fazla bilgi için bkz: [şablonlar ve ad çözümü](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** bir şablon bildirimindeki veya tanımı yerindeki herhangi bir türü tarafından kullanılabilir. Şablon temel sınıfın şablon bağımsız değişkeni olarak kullanılmadığı sürece temel sınıf listesinde izin verilmez.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename** anahtar sözcüğü de kullanılabilir yerine **sınıfı** şablonu parametresinde listeler. Örneğin, aşağıdaki deyimleri anlam olarak eşdeğerdir:  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Örnek  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şablonları](../cpp/templates-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)