---
title: "Genel işlevler (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ebafa409680609d6e097b803be2b539ccdc7601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="generic-functions-ccli"></a>Genel İşlevler (C++/CLI)
Tür parametreleri ile bildirilmiş bir işlev buna genel bir işlevdir. Çağrıldığında, gerçek türleri tür parametreleri yerine kullanılır.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 **Açıklamalar**  
  
 Bu özellik tüm platformlar için geçerli değildir.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 Bu özellik, Windows çalışma zamanı'nda desteklenmiyor.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 Tür parametreleri ile bildirilmiş bir işlev buna genel bir işlevdir. Çağrıldığında, gerçek türleri tür parametreleri yerine kullanılır.  
  
 **Sözdizimi**  
  
```  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
 **Parametreler**  
  
 *öznitelikleri* (isteğe bağlı)  
 Ek tanımlayıcı bilgiler. Öznitelikleri özniteliklerinin ve öznitelik sınıfları hakkında daha fazla bilgi için bkz.  
  
 *değiştiriciler* (isteğe bağlı)  
 Statik gibi işlev için değiştiricisi.  `virtual`sanal yöntemler genel olmayabilir olduğundan izin verilmiyor.  
  
 *dönüş türü*  
 Yöntem tarafından döndürülen tür. Dönüş türü void ise, hiçbir değer döndürmeyen gereklidir.  
  
 *tanımlayıcı*  
 İşlev adı.  
  
 *tür parametresi tanımlayıcıları*  
 Tanımlayıcıları virgülle ayrılmış listesi.  
  
 *Resmi parametreleri* (isteğe bağlı)  
 Parametre listesi.  
  
 *tür parametresi kısıtlamaları tümceler*  
 Bu tür bağımsız değişkeni kullanılabilir türler kısıtlamalarını belirler ve belirtilen form sürer [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *işlev gövdesi*  
 Tür parametresi tanımlayıcı başvurabilir yönteminin gövdesi.  
  
 **Açıklamalar**  
  
 Genel işlevler genel tür parametresi ile bildirilen işlevlerdir. Bunlar bir sınıf veya yapı veya tek başına işlevleri yöntemlerinde olabilir. Tek bir genel bildirimde örtük olarak yalnızca genel tür parametresi için farklı bir gerçek türü değiştirme değerinde farklı işlevler ailesi bildirir.  
  
 Visual C++'da, sınıf veya yapı oluşturucuları genel tür parametreleri ile bildirilmemiş.  
  
 Çağrıldığında, genel tür parametresi geçerli bir tür değiştirilir. Gerçek tür, bir şablon işlev çağrısı için benzer bir sözdizimi kullanılarak açılı ayraç içinde açıkça belirtilebilir. Türü parametresiz çağırdıysanız, derleyici işlev çağrısında sağlanan parametrelerinden gerçek türünü türetme dener. İstenen tür bağımsız değişkeni kullanılan parametreler anlaşılamıyor, derleyici bir hata bildirir.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneği, genel bir işlev gösterir.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **Örnek**  
  
 Genel işlevler imza veya parametre sayısı, üzerinde bir işlev türü parametre sayısı bazında aşırı yüklenmiş. Ayrıca, bazı tür parametrelerinde işlevler farklı sürece genel işlevler ile aynı ada sahip genel olmayan işlevleri aşırı yüklenebilir. Örneğin, aşağıdaki işlevleri aşırı yüklenebilir:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek genel işlevi bir dizi ilk öğe bulmak için kullanır. Bunu bildirir `MyClass`, temel sınıfından devralan `MyBaseClass`. `MyClass`Genel bir işlev içeriyor `MyFunction`, başka bir genel işlevi, çağıran `MyBaseClassFunction`, taban sınıf içinde. İçinde **ana**, genel işlevi `MyFunction`, farklı tür bağımsız değişkenleri kullanılarak çağrılır.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Output**  
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)   
 [Genel Türler](../windows/generics-cpp-component-extensions.md)