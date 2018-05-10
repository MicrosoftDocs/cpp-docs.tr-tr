---
title: Sınıflar ve yapılar (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9863786e5e017b69217f984e3aa6d1db597e74d3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="classes-and-structs--c-component-extensions"></a>Sınıflar ve Yapılar (C++ Bileşen Uzantıları)
Sınıfta veya yapı bildirir, *nesne ömrü* otomatik olarak yönetilir. Nesne artık erişilebilir değil veya kapsam dışında olduğunda Visual C++ nesnesine ayrılan bellek otomatik olarak atar.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Sözdizimi**  
  
```  
  
      class_access  
      ref class  
      name  
      modifier :  inherit_accessbase_type {};  
class_accessref structnamemodifier :  inherit_accessbase_type {};  
class_accessvalue classnamemodifier :  inherit_accessbase_type {};  
class_accessvalue structnamemodifier :  inherit_accessbase_type {};  
  
```  
  
 **Parametreler**  
  
 *class_access* (isteğe bağlı)  
 Sınıf veya yapı derleme dışına erişilebilirliğini. Olası değerler şunlardır: **ortak** ve `private` (`private` varsayılandır). İç içe geçmiş sınıflar ya da yapının olamaz bir *class_access* tanımlayıcısı.  
  
 *Adı*  
 Sınıf veya yapı adı.  
  
 *Değiştirici* (isteğe bağlı)  
 [soyut](../windows/abstract-cpp-component-extensions.md) ve [korumalı](../windows/sealed-cpp-component-extensions.md) geçerli değiştiricileri şunlardır.  
  
 *inherit_access* (isteğe bağlı)  
 Erişilebilirliğini `base_type`. İzin verilen tek erişilebilirlik olan `public` (`public` varsayılandır).  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. Ancak, bir değer türü temel tür olarak davranamaz.  
  
 Daha fazla bilgi için bu parametre Windows çalışma zamanı ve ortak dil Runtimesections dile özgü açıklamalarını bakın.  
  
 **Açıklamalar**  
  
 Bir nesnenin varsayılan üye erişilebilirlik ile bildirilen **ref sınıfı** veya **değer sınıfının** olan `private`. Ve nesnenin varsayılan üye erişilebilirlik ile bildirilen **ref yapısı** veya **değer yapısı** olan `public`.  
  
 Bir başvuru türü başka bir başvuru türünden devralan, taban sınıf içinde sanal işlevleri açıkça kılınmalıdır (ile [geçersiz kılma](../windows/override-cpp-component-extensions.md)) veya gizli (ile [yeni (vtable'de yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Türetilmiş sınıf işlevleri de açıkça olarak işaretlenmelidir `virtual`.  
  
 Derleme zamanında bir tür olup olmadığını algılamak için bir `ref class` veya `ref struct`, veya bir `value class` veya `value struct`, kullanın `__is_ref_class (type)`, `__is_value_class (type)`, veya `__is_simple_value_class (type)`. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Sınıflar ve yapılar hakkında daha fazla bilgi için bkz:  
  
-   [Örnek oluşturma sınıflar ve yapılar](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
 
  
-   [Referans Türleri için C++ Yığın Anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Sınıflar, yapılar ve birleşimleri](../cpp/classes-and-structs-cpp.md)  
  
-   [Yok ediciler ve sonlandırıcılar nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [Kullanıcı Tanımlı İşleçler (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Kullanıcı Tanımlı Dönüşümler (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Genel Sınıflar (C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 Bkz: [Ref sınıflar ve yapılar](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) ve [değer sınıflar ve yapılar](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Parametreler**  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. A `ref class` veya `ref struct` sıfır veya daha fazla arabirimleri ve sıfır veya bir devralabilirsiniz `ref` türleri. A `value class` veya `value struct` yalnızca sıfır veya daha fazla arabirimlerinden devralabilirsiniz.  
  
 Ne zaman bildirdiğiniz nesneyi kullanarak `ref class` veya `ref struct` anahtar sözcükler, nesne tarafından erişildiğinde bir nesne için bir tanıtıcı; diğer bir deyişle, nesne için bir başvuru sayaç işaretçi. Bildirilen değişken kapsam dışına çıktığında derleyici nesnesini otomatik olarak siler. Nesne çağrıda bir parametre olarak kullanılan veya bir değişkende depolanan nesnesi için bir tanıtıcı gerçekte geçirilen veya depolanır.  
  
 Ne zaman bildirdiğiniz nesneyi kullanarak `value class` veya `value struct` anahtar sözcükler, bildirilen nesnesinin nesne ömrü değil denetimlidir. Nesne herhangi diğer standart C++ sınıfta veya yapı gibi değil.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 Aşağıdaki tabloda gösterilen söz dizimi farkları listeler **tüm çalışma zamanları** C + belirli bölüm +/ CLI.  
  
 **Parametreler**  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. A `ref class` veya `ref struct` sıfırdan devralabilirsiniz veya daha fazla yönetilen arabirimleri ve sıfır veya bir başvuru türleri. A `value class` veya `value struct` yalnızca sıfır veya daha fazla yönetilen arabirimlerinden devralabilirsiniz.  
  
 `ref class` Ve `ref struct` anahtar sözcükler, sınıf veya yapı ve yığında ayrılan derleyici söyleyin. Nesne çağrıda bir parametre olarak kullanılan veya bir değişkende depolanan nesneye bir başvurusu gerçekte geçirilen veya depolanır.  
  
 `value class` Ve `value struct` anahtar sözcükler, ayrılmış sınıf veya yapı değeri, işlevlere geçirilen veya üyeleri depolanan derleyici söyler.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)