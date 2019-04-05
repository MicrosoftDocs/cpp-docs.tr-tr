---
title: .NET ve UWP için bileşen uzantıları
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
ms.openlocfilehash: cf123e54c633539c8e5bf8204344c842a21183ef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034043"
---
# <a name="component-extensions-for-net-and-uwp"></a>.NET ve UWP için bileşen uzantıları

C++ Standart diline standart olmayan uzantı sağlamak derleyici satıcılarının izin verir. Microsoft .NET Framework veya evrensel Windows Platformu (UWP) çalışan yerel C++ kodu için kod bağlanmanıza yardımcı olması için uzantılar sağlar. .NET uzantıları çağrılır C + +/ yönetilen yürütme ortamı, ortak dil çalışma zamanı (CLR) olarak adlandırılır. NET'te yürütür CLI ve üretim kodu. UWP uzantıları çağrılır C + +/ CX ve yerel makine kodu üretir.

> [!NOTE]
> Yeni uygulamalar için C + kullanılması önerilir +/ WinRT yerine C + +/ CX. C + +/ WinRT olan yeni, standart C ++ 17 dil projeksiyon Windows Runtime API'ları için. Biz C + desteklemeye devam edecektir +/ CX ve WRL, ancak yüksek yeni uygulama C + kullanmanız +/ WinRT. Daha fazla bilgi için [C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis/index).

### <a name="two-runtimes-one-set-of-extensions"></a>İki çalışma zamanları, bir uzantı kümesi

C + +/ CLI, ISO/ANSI C++ standard genişletir ve Ecma C + altında tanımlanan +/ CLI standart. Daha fazla bilgi için [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

C + +/ CX uzantıları olan bir alt kümesini C + +/ CLI. Uzantı sözdizimini çoğu durumda aynı olsa da olup belirttiğiniz üzerinde oluşturulan kodu bağlıdır `/ZW` hedef UWP, derleyici seçeneği veya `/clr` hedeflenecek .NET seçeneği. Bir proje oluşturmak için Visual Studio kullandığınızda bu anahtarları otomatik olarak ayarlanır.

## <a name="data-type-keywords"></a>Veri türü anahtar sözcükleri

Dil uzantıları dahil *toplama anahtar sözcükleri*, boşluk tarafından ayrılmış iki belirteçlerin oluşur. Birlikte kullanıldıklarında belirteçleri ayrı olarak kullanıldığında bir anlamı ve başka bir anlama sahip olabilir. Örneğin, "başvuru" normal bir tanımlayıcı olup ve "class" yerel bir sınıfı bildirir bir anahtar sözcüktür. Ancak, bu sözcükler birleştirilir forma **başvuru sınıfı**, sonuçta elde edilen toplam anahtar sözcüğü olarak bilinen bir varlık bildirir bir *çalışma zamanı sınıf*.

Uzantıları de *bağlama duyarlı* anahtar sözcükleri. Bir anahtar sözcüğü, bağlama duyarlı olarak ve o ifadedeki yerleşimi içeren ifade türünü bağlı olarak kabul edilir. Örneğin, bir tanımlayıcı "özelliği" belirteci olabilir ya da ortak sınıf üyesine özel bir tür bildirebilirsiniz.

Aşağıdaki tabloda, C++ dil uzantısı anahtar sözcükleri listeler.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**başvuru sınıfı**<br /><br /> **ref struct**|Hayır|Bir sınıfı bildirir.|[Sınıflar ve Yapılar](classes-and-structs-cpp-component-extensions.md)|
|**Değer sınıfı**<br /><br /> **değer yapısı**|Hayır|Değer sınıfı bildirir.|[Sınıflar ve Yapılar](classes-and-structs-cpp-component-extensions.md)|
|**arabirim sınıfı**<br /><br /> **Arabirim yapı birimi**|Hayır|Bir arabirim bildirir.|[arabirim sınıfı](interface-class-cpp-component-extensions.md)|
|**enum sınıfı**<br /><br /> **Numaralandırma yapı birimi**|Hayır|Bir sabit listesi bildirir.|[enum sınıfı](enum-class-cpp-component-extensions.md)|
|**özellik**|Evet|Bir özelliği bildirir.|[özellik](property-cpp-component-extensions.md)|
|**temsilci**|Evet|Bir temsilci bildirir.|[delegate (C + +/ CLI ve C + +/ CX)](delegate-cpp-component-extensions.md)|
|**olay**|Evet|Bir olayı bildirir.|[olay](event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Geçersiz Kılma Tanımlayıcıları

Geçersiz kılma davranışını türetme nitelemek için aşağıdaki anahtar sözcükler kullanabilirsiniz. Ancak **yeni** anahtar sözcüğü C++'ın bir uzantısı değil, çünkü başka bir bağlamda kullanılabilir burada listelenir. Bazı tanımlayıcıları da yerel programlama için geçerlidir. Daha fazla bilgi için [nasıl yapılır: Yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**abstract**|Evet|İşlevler veya sınıflar abstract olduğunu gösterir.|[abstract](abstract-cpp-component-extensions.md)|
|**new**|Hayır|Bir işlevi geçersiz kılma bir temel sınıf sürümü olmadığını gösterir.|[yeni (vtable'de yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|Evet|Bir yöntemi geçersiz kılma bir temel sınıf sürümü olması gerektiğini gösterir.|[override](override-cpp-component-extensions.md)|
|**korumalı**|Evet|Sınıflar temel sınıf olarak kullanılmasını engeller.|[korumalı](sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>Genel türler için anahtar sözcükler

Aşağıdaki anahtar sözcükler, genel türleri desteklemek için eklendi. Daha fazla bilgi için [genel türler](generics-cpp-component-extensions.md).

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|
|-------------|-----------------------|-------------|
|**genel**|Hayır|Genel bir tür bildirir.|
|**Burada**|Evet|Bir genel tür parametresine uygulanan kısıtlamaları belirtir.|

## <a name="miscellaneous-keywords"></a>Çeşitli anahtar sözcükleri

Aşağıdaki anahtar sözcükler için C++ uzantısı eklenip eklenmediğini.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**finally**|Evet|Varsayılan özel durum handlings davranış gösterir.|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|
|**for each, in**|Hayır|Bir koleksiyonun öğeleri sıralar.|[for each, in](../dotnet/for-each-in.md)|
|**gcnew**|Hayır|Atık olarak toplanmış yığındaki türler ayırır. Kullanım yerine **yeni** ve **Sil**.|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**Yeni başvuru**|Evet|Bir Windows çalışma zamanı türü ayırır. Kullanım yerine **yeni** ve **Sil**.|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|Evet|Bir üyesi yalnızca bildirimi veya statik oluşturucuda başlatılabilir olduğunu gösterir.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**değişmez değer**|Evet|Sabit bir değişken oluşturur.|[değişmez değer](literal-cpp-component-extensions.md)|
|**nullptr**|Hayır|Tanıtıcı veya işaretçi bir nesne göstermiyor gösterir.|[nullptr](nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>Şablon yapıları

Aşağıdaki dil yapıları olarak anahtar sözcükler yerine şablon olarak uygulanır. Belirtirseniz `/ZW` derleyici seçeneği, bunlar tanımlanır `lang` ad alanı. Belirtirseniz `/clr` derleyici seçeneği, bunlar tanımlanır `cli` ad alanı.

|Anahtar sözcüğü|Amaç|Başvuru|
|-------------|-------------|---------------|
|**dizi**|Bir diziyi bildirir.|[Diziler](arrays-cpp-component-extensions.md)|
|**interior_ptr anahtar**|(Yalnızca CLR) Bir başvuru türü verilerinde işaret eder.|[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)|
|**pin_ptr**|(Yalnızca CLR) Çöp toplama sistemin geçici olarak engellemek için CLR başvuru türleri işaret eder.|[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)|
|**safe_cast**|Belirler ve bir çalışma zamanı türü için en iyi atama yöntemini yürütür.|[safe_cast](safe-cast-cpp-component-extensions.md)|
|**typeid**|(Yalnızca CLR) Alır bir <xref:System.Type?displayProperty=fullName> belirtilen türün veya nesneyi tanımlayan nesne.|[typeid](typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>Bildirimciler

Aşağıdaki tür bildirimcileri ömrü ve ayrılmış nesne silme işlemlerini otomatik olarak yönetmek için çalışma zamanı isteyin.

|İşleç|Amaç|Başvuru|
|--------------|-------------|---------------|
|`^`|Bir nesne için bir tanıtıcı bildirir; diğer bir deyişle, artık kullanılabilir olduğunda otomatik olarak silinen bir Windows çalışma zamanı veya CLR nesnesine bir işaretçi.|[İşlenecek Nesne İşleci (^)](handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|İzleme başvurusu bildirir; diğer bir deyişle, artık kullanılabilir olduğunda otomatik olarak silinen bir Windows çalışma zamanı veya CLR nesnesine bir başvuru.|[İzleme Başvurusu İşleci](tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>Ek yapıları ve ilgili konular

Bu bölümde ek programlama yapıları ve CLR ile ilgili konuları listeler.

|Konu|Açıklama|
|-----------|-----------------|
|[__tanımlayıcı (C++/CLI)](identifier-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Tanımlayıcı olarak anahtar sözcük kullanımını etkinleştirir.|
|[Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Değişken sayıda bağımsız değişken için bir işlev sağlar.|
|[C++ Yerel Türlerinin .NET Framework Eşdeğerleri (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ tamsayı türleri yerine kullanılan CLR türlerini listeler.|
|[AppDomain](../cpp/appdomain.md) **__declspec** değiştiricisi|**__declspec** statik ve genel değişkenleri uygulama etki alanı mevcut taahhütlerin değiştiricisi.|
|[/clr ile C Türü Atamalar (C++/CLI)](c-style-casts-with-clr-cpp-cli.md)|C türü atamalar yorumlanma şeklini tanımlar.|
|[__clrcall](../cpp/clrcall.md) çağırma kuralı|CLR uyumlu çağırma kuralını belirtir.|
|`__cplusplus_cli`|[Önceden Tanımlı Makrolar](../preprocessor/predefined-macros.md)|
|[Özel Öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kendi CLR öznitelikleri tanımlanacağını açıklar.|
|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|Özel durum işleme genel bir bakış sağlar.|
|[Açık Geçersiz Kılmalar](explicit-overrides-cpp-component-extensions.md)|Üye işlevleri rastgele üyeleri nasıl kılabilirsiniz gösterir.|
|[Arkadaş Derlemeler (C++)](../dotnet/friend-assemblies-cpp.md)|İstemci bütünleştirilmiş kod derleme bileşeninin tüm türlerin nasıl erişebileceğinizi açıklanır.|
|[Kutulama](boxing-cpp-component-extensions.md)|Değerleri Kutulu türlerden oluşur koşullar gösterir.|
|[Tür Özellikleri için Derleyici Desteği](compiler-support-for-type-traits-cpp-component-extensions.md)|Derleme zamanında tür özelliklerini nasıl ele alınmaktadır.|
|[yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmaları|Yönetilen ve yönetilmeyen işlevleri gösterir aynı modülünde birlikte bulunabilir.|
|[işlem](../cpp/process.md) **__declspec** değiştiricisi|**__declspec** statik ve genel değişkenler her işlem mevcut taahhütlerin değiştiricisi.|
|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Çalışma zamanı türü bilgileri CLR sürümünü gösterir.|
|[Dize](string-cpp-component-extensions.md)|Dize sabit değerleri için derleyici dönüştürülmesi açıklanmaktadır <xref:System.String>.|
|[Tür İletme (C++/CLI)](type-forwarding-cpp-cli.md)|İstemci kodunun derlenmesi gerekmez. böylece başka bir derleme için bir Kargo derlemedeki bir türe hareketini sağlar.|
|[Kullanıcı Tanımlı Öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kullanıcı tanımlı öznitelikler gösterir.|
|[#using Yönergesi](../preprocessor/hash-using-directive-cpp.md)|Dış derlemeler içeri aktarır.|
|[XML Belgeleri](../build/reference/xml-documentation-visual-cpp.md)|Kullanarak XML-tabanlı kod belgelerinde açıklanır  [ /doc (işlem belgeleri açıklamaları) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|

## <a name="see-also"></a>Ayrıca bkz.

[.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)