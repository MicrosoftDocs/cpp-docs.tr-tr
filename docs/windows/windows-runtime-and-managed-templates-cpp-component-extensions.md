---
title: Windows çalışma zamanı ve yönetilen şablonlar (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec064bc8ea40fd4835c4f779e0120e1daa445d7e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641466"
---
# <a name="windows-runtime-and-managed-templates-c-component-extensions"></a>Windows Çalışma Zamanı ve Yönetilen Şablonlar (C++ Bileşen Uzantıları)
Şablonları, bir Windows çalışma zamanı veya ortak dil çalışma zamanı türü prototipin tanımlamanıza olanak sağlar ve ardından farklı bir şablon türü parametreleri kullanarak bu tür çeşidi örneği.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Değer veya başvuru türleri şablonları oluşturabilirsiniz.  Değer veya başvuru türleri oluşturma hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Standart C++ sınıf şablonları hakkında daha fazla bilgi için bkz: [sınıf şablonlarının](../cpp/class-templates.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 (Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/ZW`  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Aşağıdaki kod örneklerinde gösterilmektedir yönetilen türlerinden sınıf şablonları oluşturmak için bazı sınırlamalar vardır.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/clr`  
  
### <a name="examples"></a>Örnekler  
  
 Yönetilen tür şablonu parametresi olan bir genel tipi örneklemeli mümkündür, ancak bir genel tür şablonu parametresi ile yönetilen bir şablon örneği oluşturulamıyor.  Genel türler çalışma zamanında çözümlenir olmasıdır.  Daha fazla bilgi için [genel türler ve temsilciler (Visual C++)](../windows/generics-and-templates-visual-cpp.md).  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 Bir genel tür veya işlev yönetilen bir şablonda iç içe olamaz.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 C + ile başvurulan bir derlemede tanımlanan şablonları erişemiyor +/ CLI dili söz dizimi, ancak yansıma kullanabilirsiniz.  Bir şablon örneği değil, meta verilerde yayıldığını değil.  Bir şablon örneği varsa, yalnızca başvurulan üye işlevleri meta verilerde görüntülenir.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 Kısmi özelleştirme veya bir sınıf şablonunun açık özelleştirme bir sınıfın yönetilen değiştiricisi değiştirebilirsiniz.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)