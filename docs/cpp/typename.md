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
ms.openlocfilehash: 79ba7d0bda73762d04f0dd11668eb31c275ac03f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467526"
---
# <a name="typename"></a>typename
Şablon tanımlarında, bilinmeyen bir tanımlayıcının tür olduğunu, derleyici bir ipucu sağlar. Şablon parametre listesinde, bir tür parametresi belirtmek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typename identifier;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir şablon tanımı bir adı bir şablon bağımsız değişkenine bağımlı bir tam adı ise bu anahtar sözcük kullanılmalıdır; tam ad bağımlı değilse isteğe bağlıdır. Daha fazla bilgi için [şablonlar ve ad çözümü](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** şablon bildiriminde veya tanımda herhangi bir yerinde herhangi bir türü tarafından kullanılabilir. Şablon temel sınıfın şablon bağımsız değişkeni olarak kullanılmadığı sürece temel sınıf listesinde izin verilmez.  
  
```cpp 
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename** anahtar sözcüğü de kullanılabilir yerine **sınıfı** şablon parametre listesinde. Örneğin, aşağıdaki deyimleri anlam olarak eşdeğerdir:  
  
```cpp 
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Örnek  
  
```cpp 
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Şablonları](../cpp/templates-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)