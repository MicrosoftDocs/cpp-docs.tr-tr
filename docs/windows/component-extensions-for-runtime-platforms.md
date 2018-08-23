---
title: Çalışma zamanı platformları için bileşen uzantıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- Visual C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c939a2a96d0f8a34dbe9424ab7e07c5a60c2224
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610211"
---
# <a name="component-extensions-for-runtime-platforms"></a>Çalışma Zamanı Platformları için Bileşen Uzantıları

Visual C++ çalışma zamanı platformları karşı programlama yardımcı olmak için dil uzantıları sağlar. Kullanarak C + +/ CX, program Evrensel Windows platformu uygulamaları ve yerel kod olarak derlemek bileşenleri. C + kullanarak doğrudan Windows çalışma zamanı COM arabirimleri için programlama ile Evrensel Windows platformu uygulamaları oluşturabilirsiniz ancak +/ CX, Oluşturucular, özel durumlar ve diğer modern C++ programlama deyimlerini ile çalışabilir. Yönetilen yürütme ortamında .NET platformu, C++ programlama etkinleştirmek için C + kullanabileceğiniz +/ CLI.

### <a name="two-runtimes-one-set-of-extensions"></a>İki çalışma zamanları, bir uzantı kümesi

C + +/ CX olan bir alt kümesini C + +/ CLI. C + için ortak olan uzantıları için +/ CX ve C + +/ CLI, semantiği bağlıdır, ortak dil çalışma zamanı (CLR) veya Windows çalışma zamanını hedefleyen üzerinde. Uygulamanızı Windows çalışma zamanı üzerinde çalıştırılacak derlemeye belirtin `/ZW` derleyici seçeneği. CLR üzerinde çalıştırmak için derleme için belirtme `/clr` derleyici seçeneği. Bir proje oluşturmak için Visual Studio kullandığınızda bu anahtarları otomatik olarak ayarlanır.

C++ ile Evrensel Windows platformu uygulamaları oluşturma hakkında daha fazla bilgi için bkz. [C++ kullanan Windows Runtime için yol haritası uygulamaları](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).

C + +/ CLI, ISO/ANSI C++ standard genişletir ve Ecma C + altında tanımlanan +/ CLI standart. Daha fazla bilgi için [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

## <a name="data-type-keywords"></a>Veri türü anahtar sözcükleri

Dil uzantıları dahil *toplama anahtar sözcükleri*, boşluk tarafından ayrılmış iki belirteçleri oluşan anahtar sözcükleri olan. Birlikte kullanıldıklarında belirteçleri ayrı olarak kullanıldığında bir anlamı ve başka bir anlama sahip olabilir. Örneğin, "başvuru" normal bir tanımlayıcı olup ve "class" yerel bir sınıfı bildirir bir anahtar sözcüktür. Ancak, bu sözcükler birleştirilir forma **başvuru sınıfı**, sonuçta elde edilen toplam anahtar sözcüğü olarak bilinen bir varlık bildirir bir *çalışma zamanı sınıf*.

Uzantıları de *bağlama duyarlı* anahtar sözcükleri. Bir anahtar sözcüğü, bağlama duyarlı olarak ve o ifadedeki yerleşimi içeren ifade türünü bağlı olarak kabul edilir. Örneğin, bir tanımlayıcı "özelliği" belirteci olabilir ya da ortak sınıf üyesine özel bir tür bildirebilirsiniz.

Aşağıdaki tabloda, C++ dil uzantısı anahtar sözcükleri listeler.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**başvuru sınıfı**<br /><br /> **ref struct**|Hayır|Bir sınıfı bildirir.|[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)|
|**Değer sınıfı**<br /><br /> **değer yapısı**|Hayır|Değer sınıfı bildirir.|[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)|
|**arabirim sınıfı**<br /><br /> **Arabirim yapı birimi**|Hayır|Bir arabirim bildirir.|[arabirim sınıfı](../windows/interface-class-cpp-component-extensions.md)|
|**sabit listesi sınıfı**<br /><br /> **Numaralandırma yapı birimi**|Hayır|Bir sabit listesi bildirir.|[sabit listesi sınıfı](../windows/enum-class-cpp-component-extensions.md)|
|**property**|Evet|Bir özelliği bildirir.|[property](../windows/property-cpp-component-extensions.md)|
|**delegate**|Evet|Bir temsilci bildirir.|[temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)|
|**event**|Evet|Bir olayı bildirir.|[event](../windows/event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Geçersiz Kılma Tanımlayıcıları

Geçersiz kılma davranışını türetme nitelemek için aşağıdaki anahtar sözcükler kullanabilirsiniz. Ancak **yeni** anahtar sözcüğü C++'ın bir uzantısı değil, çünkü başka bir bağlamda kullanılabilir burada listelenir. Bazı tanımlayıcıları da yerel programlama için geçerlidir. Daha fazla bilgi için [nasıl yapılır: yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**abstract**|Evet|İşlevler veya sınıflar abstract olduğunu gösterir.|[abstract](../windows/abstract-cpp-component-extensions.md)|
|**new**|Hayır|Bir işlevi geçersiz kılma bir temel sınıf sürümü olmadığını gösterir.|[Yeni (vtable'da yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|Evet|Bir yöntemi geçersiz kılma bir temel sınıf sürümü olması gerektiğini gösterir.|[override](../windows/override-cpp-component-extensions.md)|
|**sealed**|Evet|Sınıflar temel sınıf olarak kullanılmasını engeller.|[sealed](../windows/sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>Genel türler için anahtar sözcükler

Aşağıdaki anahtar sözcükler, genel türleri desteklemek için eklendi. Daha fazla bilgi için [genel türler](../windows/generics-cpp-component-extensions.md).

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|
|-------------|-----------------------|-------------|
|**Genel**|Hayır|Genel bir tür bildirir.|
|**Burada**|Evet|Bir genel tür parametresine uygulanan kısıtlamaları belirtir.|

## <a name="miscellaneous-keywords"></a>Çeşitli anahtar sözcükleri

Aşağıdaki anahtar sözcükler için C++ uzantısı eklenip eklenmediğini.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**finally**|Evet|Varsayılan özel durum handlings davranış gösterir.|[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)|
|**for each, in**|Hayır|Bir koleksiyonun öğeleri sıralar.|[for each, in](../dotnet/for-each-in.md)|
|**gcnew**|Hayır|Atık olarak toplanmış yığındaki türler ayırır. Kullanım yerine **yeni** ve **Sil**.|[Yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**Yeni başvuru**|Evet|Bir Windows çalışma zamanı türü ayırır. Kullanım yerine **yeni** ve **Sil**.|[Yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|Evet|Bir üyesi yalnızca bildirimi veya statik oluşturucuda başlatılabilir olduğunu gösterir.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**değişmez değer**|Evet|Sabit bir değişken oluşturur.|[değişmez değer](../windows/literal-cpp-component-extensions.md)|
|**nullptr**|Hayır|Tanıtıcı veya işaretçi bir nesne göstermiyor gösterir.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>Şablon yapıları

Aşağıdaki dil yapıları olarak anahtar sözcükler yerine şablon olarak uygulanır. Belirtirseniz `/ZW` derleyici seçeneği, bunlar tanımlanır `lang` ad alanı. Belirtirseniz `/clr` derleyici seçeneği, bunlar tanımlanır `cli` ad alanı.

|Anahtar sözcüğü|Amaç|Başvuru|
|-------------|-------------|---------------|
|**Dizi**|Bir diziyi bildirir.|[Diziler](../windows/arrays-cpp-component-extensions.md)|
|**interior_ptr anahtar**|(Yalnızca CLR) Bir başvuru türü verilerinde işaret eder.|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|
|**pin_ptr**|(Yalnızca CLR) Çöp toplama sistemin geçici olarak engellemek için CLR başvuru türleri işaret eder.|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|
|**safe_cast**|Belirler ve bir çalışma zamanı türü için en iyi atama yöntemini yürütür.|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|
|**typeid**|(Yalnızca CLR) Alır bir <xref:System.Type?displayProperty=fullName> belirtilen türün veya nesneyi tanımlayan nesne.|[typeid](../windows/typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>Bildirimciler

Aşağıdaki tür bildirimcileri ömrü ve ayrılmış nesne silme işlemlerini otomatik olarak yönetmek için çalışma zamanı isteyin.

|İşleç|Amaç|Başvuru|
|--------------|-------------|---------------|
|`^`|Bir nesne için bir tanıtıcı bildirir; diğer bir deyişle, artık kullanılabilir olduğunda otomatik olarak silinen bir Windows çalışma zamanı veya CLR nesnesine bir işaretçi.|[İşlenecek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|İzleme başvurusu bildirir; diğer bir deyişle, artık kullanılabilir olduğunda otomatik olarak silinen bir Windows çalışma zamanı veya CLR nesnesine bir başvuru.|[İzleme başvurusu işleci](../windows/tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>Ek yapıları ve ilgili konular

Bu bölümde ek programlama yapıları ve CLR ile ilgili konuları listeler.

|Konu|Açıklama|
|-----------|-----------------|
|[__tanımlayıcı (C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Tanımlayıcı olarak anahtar sözcük kullanımını etkinleştirir.|
|[Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Değişken sayıda bağımsız değişken için bir işlev sağlar.|
|[C++ Yerel Türlerinin .NET Framework Eşdeğerleri (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ tamsayı türleri yerine kullanılan CLR türlerini listeler.|
|[AppDomain](../cpp/appdomain.md) **__declspec** değiştiricisi|**__declspec** statik ve genel değişkenleri uygulama etki alanı mevcut taahhütlerin değiştiricisi.|
|[/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|C türü atamalar yorumlanma şeklini tanımlar.|
|[__clrcall](../cpp/clrcall.md) çağırma kuralı|CLR uyumlu çağırma kuralını belirtir.|
|`__cplusplus_cli`|[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)|
|[Özel öznitelikler](../windows/custom-attributes-cpp.md)|Kendi CLR öznitelikleri tanımlanacağını açıklar.|
|[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)|Özel durum işleme genel bir bakış sağlar.|
|[Açık Geçersiz Kılmalar](../windows/explicit-overrides-cpp-component-extensions.md)|Üye işlevleri rastgele üyeleri nasıl kılabilirsiniz gösterir.|
|[Arkadaş Derlemeler (C++)](../dotnet/friend-assemblies-cpp.md)|İstemci bütünleştirilmiş kod derleme bileşeninin tüm türlerin nasıl erişebileceğinizi açıklanır.|
|[Kutulama](../windows/boxing-cpp-component-extensions.md)|Değerleri Kutulu türlerden oluşur koşullar gösterir.|
|[Tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Derleme zamanında tür özelliklerini nasıl ele alınmaktadır.|
|[yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmaları|Yönetilen ve yönetilmeyen işlevleri gösterir aynı modülünde birlikte bulunabilir.|
|[işlem](../cpp/process.md) **__declspec** değiştiricisi|**__declspec** statik ve genel değişkenler her işlem mevcut taahhütlerin değiştiricisi.|
|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Çalışma zamanı türü bilgileri CLR sürümünü gösterir.|
|[dize](../windows/string-cpp-component-extensions.md)|Dize sabit değerleri için derleyici dönüştürülmesi açıklanmaktadır <xref:System.String>.|
|[Tür İletme (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|İstemci kodunun derlenmesi gerekmez. böylece başka bir derleme için bir Kargo derlemedeki bir türe hareketini sağlar.|
|[Kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md)|Kullanıcı tanımlı öznitelikler gösterir.|
|[#using yönergesi](../preprocessor/hash-using-directive-cpp.md)|Dış derlemeler içeri aktarır.|
|[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)|Kullanarak XML-tabanlı kod belgelerinde açıklanır  [ /doc (işlem belgeleri açıklamaları) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)