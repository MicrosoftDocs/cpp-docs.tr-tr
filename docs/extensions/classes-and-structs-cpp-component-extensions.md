---
title: başvuru sınıfı ve başvuru yapısı (C++/CLI ve C++/CX)
ms.date: 05/30/2019
ms.topic: reference
f1_keywords:
- ref class
- value class
- ref struct
- value struct
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
ms.openlocfilehash: dd58f32d031068785cd6020549f9eea4b2182786
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509812"
---
# <a name="ref-class-and-ref-struct--ccli-and-ccx"></a>başvuru sınıfı ve başvuru yapısı (C++/CLI ve C++/CX)

**Başvuru sınıfı** veya **başvuru yapısı** uzantıları, *nesne ömrü* otomatik olarak yönetilen bir sınıf veya yapı bildirir. Nesne artık erişilebilir olmadığında veya kapsam dışına geçtiğinde bellek serbest bırakılır.

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
Seçim Sınıf veya yapının derleme dışındaki erişilebilirliği. Olası değerler **genel** ve **özeldir** (**özel** varsayılandır). İç içe geçmiş sınıflar veya yapıların bir *class_access* belirleyicisi olamaz.

*name*<br/>
Sınıf veya yapının adı.

*icisi*<br/>
Seçim [abstract](abstract-cpp-component-extensions.md) ve [Sealed](sealed-cpp-component-extensions.md) geçerli değiştiriciler.

*inherit_access*<br/>
Seçim *Base_type*'in erişilebilirliği. İzin verilen tek erişilebilirlik **geneldir** (**genel** varsayılandır).

*base_type*<br/>
Seçim Temel tür. Ancak, bir değer türü temel tür olarak çalışamaz.

Daha fazla bilgi için, Windows Çalışma Zamanı ve ortak dil çalışma zamanı bölümlerinde bu parametrenin dile özgü açıklamalarına bakın.

### <a name="remarks"></a>Açıklamalar

**Başvuru sınıfı** veya **değer sınıfıyla** belirtilen bir nesnenin varsayılan üyesi erişilebilirliği **özeldir**. Ve **ref struct** veya **Value struct** ile belirtilen bir nesnenin varsayılan üyesi erişilebilirliği **geneldir**.

Bir başvuru türü başka bir başvuru türünden devralırsa, taban sınıftaki sanal işlevlerin açıkça geçersiz kılınabilmesi gerekir ( [geçersiz kılma](override-cpp-component-extensions.md)ile) veya gizli ( [Yeni (vtable 'da yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)). Türetilmiş sınıf işlevlerinin de açıkça **sanal**olarak işaretlenmesi gerekir.

Bir türün **başvuru sınıfı** veya **başvuru yapısı**, ya da bir **değer sınıfı** veya **değer yapısı**olup olmadığı derleme zamanında algılamak için, veya `__is_ref_class (type)` `__is_simple_value_class (type)`kullanın `__is_value_class (type)`. Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

Sınıflar ve yapılar hakkında daha fazla bilgi için bkz.

- [Sınıfları ve yapıları örnekleme](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [Referans Türleri için C++ Yığın Anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [Sınıflar, yapılar ve birleşimler](../cpp/classes-and-structs-cpp.md)

- [Nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [Kullanıcı Tanımlı İşleçler (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [Kullanıcı Tanımlı Dönüşümler (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [Genel Sınıflar (C++/CLI)](generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md) ve [değer sınıfları ve yapıları](../cppcx/value-classes-and-structs-c-cx.md).

### <a name="parameters"></a>Parametreler

*base_type*<br/>
Seçim Temel tür. Bir **başvuru sınıfı** veya **başvuru yapısı** sıfır veya daha fazla arabirimden ve sıfır veya bir **başvuru** türünden kalıtımla alabilir. **Değer sınıfı** veya **değer yapısı** yalnızca sıfır veya daha fazla arabirimden devralınabilir.

**Başvuru sınıfını** veya **ref struct** anahtar sözcüklerini kullanarak bir nesnesi bildirdiğinizde, nesnesine nesnesine bir tanıtıcı erişilir; diğer bir deyişle, nesneye yönelik bir başvuru sayacı işaretçisi. Belirtilen değişken kapsam dışına geçtiğinde, derleyici temel nesneyi otomatik olarak siler. Nesne, çağrıda bir parametre olarak kullanıldığında veya bir değişkende depolanıyorsa, nesne tanıtıcısı aslında geçirilir veya depolanır.

**Değer sınıfını** veya **Value struct** anahtar sözcüklerini kullanarak bir nesnesi bildirdiğinizde, belirtilen nesnenin nesne ömrü denetimli değildir. Nesnesi diğer standart C++ sınıf veya yapı gibi.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda,/Clia 'ya C++özgü tüm çalışma **zamanları** bölümünde gösterilen sözdizimindeki farklılıklar listelenmiştir.

### <a name="parameters"></a>Parametreler

*base_type*<br/>
Seçim Temel tür. Bir **başvuru sınıfı** veya **başvuru yapısı** , sıfır veya daha fazla yönetilen arabirimden ve sıfır ya da bir başvuru türünden devralınabilir. **Değer sınıfı** veya **değer yapısı** yalnızca sıfır veya daha fazla yönetilen arabirimden devralınabilir.

**Ref sınıfı** ve **ref struct** anahtar sözcükleri derleyiciye sınıf veya yapının yığına ayrılacağını söyler. Nesne, çağrıda bir parametre olarak kullanıldığında veya bir değişkende depolanıyorsa, nesne başvurusu aslında geçirilir veya depolanır.

**Değer sınıfı** ve **değer yapısı** anahtar sözcükleri derleyiciye ayrılan sınıf veya yapının değerinin işlevlere geçtiğini veya üyelerde depolandığını söyler.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)