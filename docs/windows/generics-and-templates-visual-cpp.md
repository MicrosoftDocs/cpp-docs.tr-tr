---
title: "Genel türler ve temsilciler (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 307cc39e64a6fd91f3f5f96da634e47d3e9a9030
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="generics-and-templates-visual-c"></a>Genel Türler ve Temsilciler (Visual C++)
Genel türler ve temsilciler parametreli türleri için destek sağlayan iki dil özellikleridir. Ancak, bunlar farklı ve farklı kullanır. Bu konu, çok sayıda fark genel bir bakış sağlar.  
  
 Daha fazla bilgi için bkz: [Windows çalışma zamanı ve yönetilen şablonlar](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
## <a name="comparing-templates-and-generics"></a>Şablonlar ve genel türler karşılaştırma  
 Genel türler ve C++ şablonları arasındaki farklar'yi tıklatın:  
  
-   Genel türler türleri için çalışma zamanında geçen kadar geneldir. Çalışma zamanında hala parametreli türler olmadıkları şekilde şablonları derleme zamanında özelleştirilmiş  
  
-   Ortak dil çalışma zamanı, özellikle MSIL genel türler destekler. Genel türler hakkında çalışma zamanı bildiği için belirli türleri genel türleri için genel bir tür içeren bir derlemenin başvururken yerine kullanılabilecek. Şablonlar, buna karşılık, derleme zamanında sıradan türlerine çözümlemek ve sonuçta elde edilen türleri diğer derlemelerde özelleştirilmesi değil.  
  
-   Genel türler özelleştirilmiş iki farklı derlemelerde aynı türüne sahip bağımsız değişkenler aynı türüdür. Bağımsız değişkenler çalışma zamanı tarafından farklı olarak düşünülür aynı türde iki farklı derlemelerde şablonları özelleştirilmiş.  
  
-   Genel türler (Bu değer türü başına benzersiz bir uygulamasına sahipseniz değer türleri için doğru değil) tüm başvuru türü bağımsız değişkenleri için kullanılan yürütülebilir kod tek bir parçası olarak üretilir. JIT derleme genel türler hakkında bilir ve tür bağımsız değişkenleri kullanılan başvuru veya değer türleri için kod iyileştirebilir. Şablonlar her özelleştirmesi için ayrı bir çalışma zamanı kodu oluşturur.  
  
-   Genel türler izin verme tür olmayan şablon parametreleri gibi `template <int i> C {}`. Şablonları bunları sağlar.  
  
-   Genel türler açık uzmanlık (diğer bir deyişle, özel bir uygulamasını belirli bir tür için bir şablon) izin vermez. Şablonları yapın.  
  
-   Genel türler kısmi uzmanlığı (müşteri uygulaması için bir alt türü bağımsız değişkenleri) izin vermez. Şablonları yapın.  
  
-   Genel türler genel türü için temel sınıf olarak kullanılacak tür parametresi izin vermez. Şablonları yapın.  
  
-   Şablonları şablonu şablon parametreleri destekler (örneğin `template<template<class T> class X> class MyClass`), ancak genel türler yapın.  
  
## <a name="combining-templates-and-generics"></a>Birleştirme şablonları ve genel türler  
  
-   Genel türler temel fark, şablonları ve genel türler birleştirmek uygulamaları oluşturmaya yönelik etkilere sahiptir. Örneğin, diğer diller için o şablon genel olarak kullanıma sunmak için genel bir sarmalayıcı oluşturmak istediğiniz bir şablon sınıfı olduğunu varsayalım. Genel Al şablon bu tür parametresi derleme zamanında olması gerektiğinden, bunu daha sonra şablonu rağmen geçirir tür parametresi olamaz, ancak genel tür parametresi çalışma zamanına kadar çözmek olmaz. Çalışma zamanında oluşturulabilir rasgele genel türler için derleme zamanında şablonları genişletmek için hiçbir şekilde olduğundan şablon genel içinde iç içe ya da çalışmaz.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, şablonları ve genel türler birlikte kullanarak basit bir örnek gösterilmektedir. Bu örnekte, Şablon sınıfı genel tür parametresi üzerinden geçirir. Ters mümkün değildir.  
  
 Bu deyim bir Visual C++ derleme için yerel olan şablon kodu ile var olan bir genel API oluşturmak istediğinizde ya da şablonlarının değil supporte belirli özelliklerden yararlanmak için genel tür için fazladan bir parametrelemeyi katmanı eklemeniz gerektiğinde kullanılabilir genel türler d.  
  
### <a name="code"></a>Kod  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
F  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](../windows/generics-cpp-component-extensions.md)