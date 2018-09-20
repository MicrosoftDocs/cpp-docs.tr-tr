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
ms.openlocfilehash: 60e388e18e6d3607dac1946c3fd9a511e948afd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448382"
---
# <a name="classes-and-structs--c-component-extensions"></a>Sınıflar ve Yapılar (C++ Bileşen Uzantıları)

Bir sınıf veya yapı bildirir, *nesne yaşam süresi* otomatik olarak yönetilir. Nesnenin artık erişilebilir değil veya kapsam dışına gider, Visual C++ nesne için ayrılan bellek otomatik olarak atar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};

```

### <a name="parameters"></a>Parametreler

*class_access*<br/>
(İsteğe bağlı) Sınıfın veya yapının derleme dışından erişilebilirlik. Olası değerler **genel** ve **özel** (**özel** varsayılandır). İç içe geçmiş sınıflar veya yapılar sahip bir *class_access* tanımlayıcısı.

*Adı*<br/>
Sınıfın veya yapının adı.

*Değiştiricisi*<br/>
(İsteğe bağlı) [soyut](../windows/abstract-cpp-component-extensions.md) ve [korumalı](../windows/sealed-cpp-component-extensions.md) geçerli değiştiricilerdir.

*inherit_access*<br/>
(İsteğe bağlı) Erişilebilirliğini *taban_türü*. Yalnızca izin verilen erişilebilirlik, **genel** (**genel** varsayılandır).

*taban_türü*<br/>
(İsteğe bağlı) Bir taban türü. Ancak, bir değer türü temel tür olarak davranamaz.

Daha fazla bilgi için bu parametre Windows çalışma zamanı ve ortak dil Runtimesections dile özgü açıklamaları bakın.

### <a name="remarks"></a>Açıklamalar

Bir nesnenin varsayılan üye erişilebilirliği ile bildirilen **başvuru sınıfı** veya **değer sınıfının** olduğu **özel**. Ve bir nesnenin varsayılan üye erişilebilirliği ile bildirilen **ref struct** veya **değeri yapı** olduğu **genel**.

Bir başvuru türü başka bir başvuru türünden devralan, temel sınıfta sanal işlevler açıkça geçersiz kılınmalıdır (ile [geçersiz kılma](../windows/override-cpp-component-extensions.md)) veya gizli (ile [yeni (vtable'da yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Türetilmiş sınıf işlevleri de açık olarak işaretlenmelidir **sanal**.

Derleme zamanında bir tür olup olmadığını algılamak için bir **başvuru sınıfı** veya **ref struct**, veya bir **değer sınıfının** veya **değeri yapı**, kullanın `__is_ref_class (type)`, `__is_value_class (type)`, veya `__is_simple_value_class (type)`. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

Sınıflar ve yapı birimleri hakkında daha fazla bilgi için bkz.

- [Örnekleme sınıflar ve yapılar](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [Referans Türleri için C++ Yığın Anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [Sınıflar, yapılar ve birleşimler](../cpp/classes-and-structs-cpp.md)

- [Yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [Kullanıcı Tanımlı İşleçler (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [Kullanıcı Tanımlı Dönüşümler (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [Genel Sınıflar (C++/CLI)](../windows/generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Bkz: [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md) ve [değer sınıfları ve yapıları](https://msdn.microsoft.com/library/windows/apps/hh699861.aspx).

### <a name="parameters"></a>Parametreler

*taban_türü*<br/>
(İsteğe bağlı) Bir taban türü. A **başvuru sınıfı** veya **ref struct** sıfır veya daha fazla arabirimi ve sıfır veya bir devralabilir **ref** türleri. A **değer sınıfının** veya **değeri yapı** yalnızca sıfır veya daha fazla ara birimden devralınabilir.

Kullanarak bir nesne bildirdiğinizde **başvuru sınıfı** veya **ref struct** anahtar sözcükler, nesne tarafından erişildiğinde bir nesne için bir tanıtıcı; diğer bir deyişle, bir nesneye başvuru sayaç işaretçi. Bildirilmiş bir değişken kapsam dışına çıktığında, derleyici, temel alınan nesnede otomatik olarak siler. Nesne bir arama parametresi olarak kullanılan veya bir değişkende depolanan nesnesi için bir tanıtıcı gerçekten aktarılan veya depolanan.

Kullanarak bir nesne bildirdiğinizde **değer sınıfının** veya **değeri yapı** anahtar sözcükler, bildirilen nesnenin nesne ömrü denetlenmiyor. Herhangi diğer standart C++ sınıf veya yapı gibi nesnedir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda gösterilen söz dizimi farklılıklarını **tüm çalışma zamanları** C + belirli bir bölüm +/ CLI.

### <a name="parameters"></a>Parametreler

*taban_türü*<br/>
(İsteğe bağlı) Bir taban türü. A **başvuru sınıfı** veya **ref struct** arabirimleri ve sıfır veya bir başvuru türlerinde birden fazla yönetilen ya da sıfırdan devralabilir. A **değer sınıfının** veya **değeri yapı** yalnızca sıfır veya daha fazla yönetilen Ara birimden devralınabilir.

**Başvuru sınıfı** ve **ref struct** anahtar sözcükleri yığında ayrılacak sınıf veya yapıda olduğundan derleyici söyleyin. Nesne bir arama parametresi olarak kullanılan veya bir değişkende depolanan nesnesine bir başvuru gerçekten aktarılan veya depolanan.

**Değer sınıfının** ve **değeri yapı** anahtar sözcükler derleyiciye ayrılmış sınıf veya yapı değerini işlevlerine geçirilen veya üyeleri depolanmış.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)