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
ms.openlocfilehash: 22f8dc4dfc3268930c80caece85b06b9a1a25d58
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461029"
---
# <a name="classes-and-structs--c-component-extensions"></a>Sınıflar ve Yapılar (C++ Bileşen Uzantıları)
Bir sınıf veya yapı bildirir, *nesne yaşam süresi* otomatik olarak yönetilir. Nesnenin artık erişilebilir değil veya kapsam dışına gider, Visual C++ nesne için ayrılan bellek otomatik olarak atar.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Söz dizimi**  
  
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
 Sınıfın veya yapının derleme dışından erişilebilirlik. Olası değerler **genel** ve **özel** (**özel** varsayılandır). İç içe geçmiş sınıflar veya yapılar sahip bir *class_access* tanımlayıcısı.  
  
 *Adı*  
 Sınıfın veya yapının adı.  
  
 *değiştiricisi* (isteğe bağlı)  
 [soyut](../windows/abstract-cpp-component-extensions.md) ve [korumalı](../windows/sealed-cpp-component-extensions.md) geçerli değiştiricilerdir.  
  
 *inherit_access* (isteğe bağlı)  
 Erişilebilirliğini `base_type`. Yalnızca izin verilen erişilebilirlik, **genel** (**genel** varsayılandır).  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. Ancak, bir değer türü temel tür olarak davranamaz.  
  
 Daha fazla bilgi için bu parametre Windows çalışma zamanı ve ortak dil Runtimesections dile özgü açıklamaları bakın.  
  
 **Açıklamalar**  
  
 Bir nesnenin varsayılan üye erişilebilirliği ile bildirilen **başvuru sınıfı** veya **değer sınıfının** olduğu **özel**. Ve bir nesnenin varsayılan üye erişilebilirliği ile bildirilen **ref struct** veya **değeri yapı** olduğu **genel**.  
  
 Bir başvuru türü başka bir başvuru türünden devralan, temel sınıfta sanal işlevler açıkça geçersiz kılınmalıdır (ile [geçersiz kılma](../windows/override-cpp-component-extensions.md)) veya gizli (ile [yeni (vtable'da yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Türetilmiş sınıf işlevleri de açık olarak işaretlenmelidir **sanal**.  
  
 Derleme zamanında bir tür olup olmadığını algılamak için bir **başvuru sınıfı** veya **ref struct**, veya bir **değer sınıfının** veya **değeri yapı**, kullanın `__is_ref_class (type)`, `__is_value_class (type)`, veya `__is_simple_value_class (type)`. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Sınıflar ve yapı birimleri hakkında daha fazla bilgi için bkz.  
  
-   [Örnekleme sınıflar ve yapılar](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [Referans Türleri için C++ Yığın Anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Sınıflar, yapılar ve birleşimler](../cpp/classes-and-structs-cpp.md)  
  
-   [Yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [Kullanıcı Tanımlı İşleçler (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Kullanıcı Tanımlı Dönüşümler (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Genel Sınıflar (C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 Bkz: [başvuru sınıfları ve yapıları](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) ve [değer sınıfları ve yapıları](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Parametreler**  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. A **başvuru sınıfı** veya **ref struct** sıfır veya daha fazla arabirimi ve sıfır veya bir devralabilir `ref` türleri. A **değer sınıfının** veya **değeri yapı** yalnızca sıfır veya daha fazla ara birimden devralınabilir.  
  
 Kullanarak bir nesne bildirdiğinizde **başvuru sınıfı** veya **ref struct** anahtar sözcükler, nesne tarafından erişildiğinde bir nesne için bir tanıtıcı; diğer bir deyişle, bir nesneye başvuru sayaç işaretçi. Bildirilmiş bir değişken kapsam dışına çıktığında, derleyici, temel alınan nesnede otomatik olarak siler. Nesne bir arama parametresi olarak kullanılan veya bir değişkende depolanan nesnesi için bir tanıtıcı gerçekten aktarılan veya depolanan.  
  
 Kullanarak bir nesne bildirdiğinizde **değer sınıfının** veya **değeri yapı** anahtar sözcükler, bildirilen nesnenin nesne ömrü denetlenmiyor. Herhangi diğer standart C++ sınıf veya yapı gibi nesnedir.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 Aşağıdaki tabloda gösterilen söz dizimi farklılıklarını **tüm çalışma zamanları** C + belirli bir bölüm +/ CLI.  
  
 **Parametreler**  
  
 *taban_türü* (isteğe bağlı)  
 Bir taban türü. A **başvuru sınıfı** veya **ref struct** arabirimleri ve sıfır veya bir başvuru türlerinde birden fazla yönetilen ya da sıfırdan devralabilir. A **değer sınıfının** veya **değeri yapı** yalnızca sıfır veya daha fazla yönetilen Ara birimden devralınabilir.  
  
 **Başvuru sınıfı** ve **ref struct** anahtar sözcükleri yığında ayrılacak sınıf veya yapıda olduğundan derleyici söyleyin. Nesne bir arama parametresi olarak kullanılan veya bir değişkende depolanan nesnesine bir başvuru gerçekten aktarılan veya depolanan.  
  
 **Değer sınıfının** ve **değeri yapı** anahtar sözcükler derleyiciye ayrılmış sınıf veya yapı değerini işlevlerine geçirilen veya üyeleri depolanmış.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)