---
title: Yönetilen sınıf türü bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- classes [C++], managed
- class keyword [C++], CLR
- __value keyword
- value types, declaring
- value keyword [C++]
- managed classes
- interface class keyword
- ref keyword [C++]
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c9e9aba6d2a0485a94385be5b8712d7552261ff1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="declaration-of-a-managed-class-type"></a>Yönetilen Sınıf Türü Bildirimi
Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirilen başvuru sınıf türü bildirme yolu.  
  
 Yönetilen Uzantılar'başvuru sınıf türü ile başlayan `__gc` anahtar sözcüğü. Yeni sözdiziminde `__gc` anahtar sözcüğü iki boşluklu anahtar biri tarafından değiştirilir: `ref class` veya `ref struct`. Seçimi `struct` veya `class` ortak gösterir (için `struct`) veya özel (için `class`) varsayılan erişim düzeyi üyeleri olarak bildirilen türün gövdesinin ilk etiketlenmemiş bölümünde.  
  
 Benzer şekilde, Yönetilen Uzantılar'değer sınıf türünün başında `__value` anahtar sözcüğü. Yeni sözdiziminde `__value` anahtar sözcüğü iki boşluklu anahtar biri tarafından değiştirilir: `value class` veya `value struct`.  
  
 Yönetilen Uzantılar, bir arabirim türü anahtar sözcüğü ile belirtilen `__interface`. Yeni sözdiziminde bu ile değiştirilir `interface class`.  
  
 Örneğin, aşağıdaki sınıf bildirimlerinde Yönetilen Uzantılar:  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 Yeni sözdizimi altında bu eşdeğer gibi bildirilir:  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## <a name="specifying-the-class-as-abstract"></a>Sınıfı Özet olarak belirtme  
 Yönetilen Uzantılar altında anahtar sözcüğü put `__abstract` önce `class` anahtar sözcüğü (önce veya sonra `__gc`) sınıf eksik olduğunu ve sınıfın nesnelerini programında oluşturulan belirtmek için:  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 Belirttiğiniz yeni sözdizimi altında `abstract` sınıfı adı ve sınıf gövdesi, temel sınıf türetme listesinden ya da noktalı önce aşağıdaki bağlamsal anahtar sözcüğü.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 Elbette, semantik anlamı değişmeden kalır.  
  
## <a name="specifying-the-class-as-sealed"></a>Sınıfı kapalı olarak belirtme  
 Yönetilen Uzantılar altında anahtar sözcüğü put `__sealed` önce `class` anahtar sözcüğü (önce veya sonra `__gc`) sınıfın nesnelerini kaynağından devralındı olamaz belirtmek için:  
  
```  
public __gc __sealed class String {};  
```  
  
 Belirttiğiniz yeni sözdizimi altında `sealed` sınıfı adı ve sınıf gövdesi, temel sınıf türetme listesinden ya da noktalı önce aşağıdaki bağlamsal anahtar sözcüğü.  
  
 Bir sınıf türetin hem getirmediyseniz. Örneğin, `String` sınıfı örtük olarak türetilir `Object`. Statik çözünürlüğünü destekleyen bir sınıf mühürleme yararı olduğu (diğer bir deyişle, derleme zamanında) korumalı başvuru sınıf nesnesi üzerinden tüm sanal işlev çağrısı. Bunun nedeni, `sealed` belirticisi garanti `String` izleme işleyicisi çağrılan sanal yöntemi geçersiz kılma örneği sağlayabilir sonradan türetilmiş bir sınıf başvuramaz. Yeni sözdiziminde kapalı bir sınıf örneği şöyledir:  
  
```  
public ref class String sealed {};  
```  
  
 Bir ayrıca hem soyut bir sınıf belirtebilir ve korumalı - bu statik sınıf gösteren bir özel durumdur. Bu CLR belgelerinde şu şekilde tanımlanır:  
  
 "Bir tür hem de `abstract` ve `sealed` yalnızca statik üyeleri olan ve ne gören bazı dillerde bir ad alanı çağırın."  
  
 Örneğin, Yönetilen Uzantılar'sözdizimini kullanarak bir Özet korumalı sınıf bildirimi şöyledir:  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 ve yeni sözdizimine çevrilmiş bu bildirimi aşağıda verilmiştir:  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## <a name="clr-inheritance-specifying-the-base-class"></a>CLR devralması: taban sınıfını belirleme  
 CLR nesne modeli altında yalnızca genel tek devralma desteklenir. Ancak, bir temel sınıf olarak özel türetme belirten bir erişim anahtar sözcüğü olmadan ISO-C++ varsayılan yorumu Yönetilen Uzantılar korunur. Bu her CLR kalıtım bildiriminin sağlamak zorunlu kılıyordu `public` varsayılan yorumu geçersiz kılmak için anahtar sözcüğü.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 Yeni sözdizimi tanımı'nda, bir erişim anahtar sözcüğü yokluğu CLR devralma tanımında ortak türetmeyi gösterir. Bu nedenle, `public` erişim anahtar sözcüğü isteğe bağlı şimdi. Bu Yönetilen Uzantılar herhangi bir değişikliği C++ kodunu gerektirmez, ancak eksiksiz olması için bu değişikliği burada listeleyin.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Özet](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)