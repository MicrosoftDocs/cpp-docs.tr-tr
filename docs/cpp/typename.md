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
ms.workload: cplusplus
ms.openlocfilehash: a276d13172b675cc6856e726cd7139e36fa97d41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)