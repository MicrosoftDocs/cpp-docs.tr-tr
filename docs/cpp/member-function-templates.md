---
title: Üye işlev şablonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7767b833fb80926e425e14a209c3d97a778e72b5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404232"
---
# <a name="member-function-templates"></a>Üye İşlev Şablonları

Terim üye şablonu hem üye işlevi şablonlarına hem de iç içe geçmiş sınıf şablonlarına başvurur. Üye işlevi şablonları, bir sınıfı veya sınıf şablonunun üyeleri olan şablon işlevleridir.  
  
 Üye işlevleri çeşitli bağlamlarda işlev şablonları olabilir. Sınıf şablonlarının tüm işlevleri geneldir ancak bunlara üye şablonları veya üye işlevi şablonları olarak başvurulmaz. Bu üye işlevleri kendi şablon bağımsız değişkenlerini alırsa, üye işlev şablonları olarak kabul edilir.  
  
## <a name="example"></a>Örnek

 Şablon dışı veya şablon sınıflarındaki üye işlev şablonları, kendi şablon parametreleriyle işlev şablonları olarak bildirilir.  
  
```cpp
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## <a name="example"></a>Örnek

 Aşağıdaki örnekte bir şablon sınıfının üye işlevi şablonu gösterilmektedir.  
  
```cpp
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Örnek
  
```cpp
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Örnek

 Yerel sınıfların üye şablonlarına sahip olmasına izin verilmez.  
  
 Üye şablonu işlevleri sanal işlevler olamaz ve bir temel sınıf sanal işlevi olarak aynı adla bildirildiklerinde bir temel sınıftan olan sanal işlevleri geçersiz kılamaz.  
  
Aşağıdaki örnekte, şablonlu kullanıcı tanımlı dönüştürme gösterilmektedir:  
  
```cpp
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İşlev Şablonları](../cpp/function-templates.md)