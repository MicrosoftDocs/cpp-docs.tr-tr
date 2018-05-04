---
title: TypeName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6eebf038fbe3e5e18e3f2a1e8e7a2aa2554bf41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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