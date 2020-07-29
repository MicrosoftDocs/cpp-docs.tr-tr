---
title: .NET ve UWP için Bileşen Uzantıları
ms.date: 10/12/2018
ms.topic: overview
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
ms.openlocfilehash: aa6e5d1ea7d1bc2d7ebfaf07c7c9f808b37e9804
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219774"
---
# <a name="component-extensions-for-net-and-uwp"></a>.NET ve UWP için Bileşen Uzantıları

C++ standardı, derleyici satıcılarının dile standart olmayan uzantılar sağlamasına izin verir. Microsoft, yerel C++ kodunu .NET Framework veya Evrensel Windows Platformu (UWP) üzerinde çalışan koda bağlamanıza yardımcı olacak uzantılar sağlar. .NET uzantılarına C++/CLı adı verilir ve .NET yönetilen yürütme ortamında çalıştırılan ve ortak dil çalışma zamanı (CLR) olarak adlandırılan kodu üretir. UWP uzantılarına C++/CX adı verilir ve yerel makine kodu üretir.

> [!NOTE]
> Yeni uygulamalar için C++/cxyerine C++/Wınrt kullanılması önerilir. C++/Wınrt, Windows Çalışma Zamanı API 'Leri için yeni, standart bir C++ 17 dil projeksiyonu. C++/CX ve WRL 'yi desteklemeye devam edeceğiz, ancak yeni uygulamaların C++/Wınrtrtı kullanmasını önemle öneririz. Daha fazla bilgi için bkz. [C++/Wınrt](/windows/uwp/cpp-and-winrt-apis/index).

### <a name="two-runtimes-one-set-of-extensions"></a>İki çalışma zamanı, bir dizi uzantı

C++/CLı, ISO/ANSI C++ standardını genişletir ve ecma C++/CLı standardına göre tanımlanır. Daha fazla bilgi için bkz. [C++/CLI ile .NET programlama (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

C++/CX uzantıları, C++/CLI'NIN bir alt kümesidir. Uzantı söz dizimi çoğu durumda özdeş olsa da, oluşturulan kod, `/ZW` UWP 'yi hedeflemek için derleyici seçeneğini belirtmenize veya `/clr` .net 'i hedeflemek için kullanabileceğiniz bir seçeneğe bağlıdır. Bu anahtarlar, bir proje oluşturmak için Visual Studio kullandığınızda otomatik olarak ayarlanır.

## <a name="data-type-keywords"></a>Veri türü anahtar sözcükleri

Dil uzantıları, boşluk ile ayrılmış iki belirteçden oluşan *toplama anahtar sözcüklerini*içerir. Belirteçlerin ayrı olarak kullanıldıkları bir anlamı olabilir ve birlikte kullanıldıkları bir anlamı vardır. Örneğin, "ref" sözcüğü sıradan bir tanımlayıcıdır ve "Class" sözcüğü, yerel bir sınıfı bildiren bir anahtar sözcüktür. Ancak, bu sözcükler form **başvuru sınıfında**birleştirildiğinde, elde edilen toplama anahtar sözcüğü, *çalışma zamanı sınıfı*olarak bilinen bir varlık bildirir.

Uzantılar ayrıca *bağlama duyarlı* anahtar sözcükler içerir. Anahtar sözcüğü, kendisini içeren deyimin türüne ve bu deyimdeki yerleşimine göre bağlama duyarlı olarak değerlendirilir. Örneğin, belirteç "özelliği" bir tanımlayıcı olabilir veya özel bir ortak sınıf üyesi türü bildirebilir.

Aşağıdaki tabloda, C++ dil uzantısında anahtar sözcükler listelenmektedir.

|Sözcükle|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**başvuru sınıfı**<br /><br /> **ref yapısı**|Hayır|Bir sınıf bildirir.|[Sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md)|
|**değer sınıfı**<br /><br /> **value yapısı**|Hayır|Değer sınıfını bildirir.|[Sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md)|
|**arabirim sınıfı**<br /><br /> **arabirim yapısı**|Hayır|Bir arabirim bildirir.|[arabirim sınıfı](interface-class-cpp-component-extensions.md)|
|**sabit listesi sınıfı**<br /><br /> **Enum yapısı**|Hayır|Bir sabit listesi bildirir.|[sabit listesi sınıfı](enum-class-cpp-component-extensions.md)|
|**`property`**|Yes|Bir özellik bildirir.|[özelliði](property-cpp-component-extensions.md)|
|**ğini**|Yes|Bir temsilci bildirir.|[delegate (C++/CLI ve C++/CX)](delegate-cpp-component-extensions.md)|
|**olay**|Yes|Bir olayı bildirir.|[olay](event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Geçersiz Kılma Tanımlayıcıları

Türetme için geçersiz kılma davranışını nitelemek için aşağıdaki anahtar sözcükleri kullanabilirsiniz. **`new`** Anahtar sözcüğü C++ uzantısı olmasa da, ek bir bağlamda kullanılabilmesi için burada listelenir. Bazı tanımlayıcılar yerel programlama için de geçerlidir. Daha fazla bilgi için bkz. [nasıl yapılır: yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme (C++/CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

|Sözcükle|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**Soyut**|Yes|İşlevlerin veya sınıfların soyut olduğunu gösterir.|[Soyut](abstract-cpp-component-extensions.md)|
|**`new`**|Hayır|Bir işlevin temel sınıf sürümünün geçersiz kılınmadığını gösterir.|[yeni (vtable'de yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|Yes|Bir yöntemin temel sınıf sürümünün geçersiz kılınması olması gerektiğini belirtir.|[override](override-cpp-component-extensions.md)|
|**sealed**|Yes|Sınıfların temel sınıf olarak kullanılmasını önler.|[sealed](sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>Genel türler için anahtar sözcükler

Aşağıdaki anahtar sözcükler genel türleri desteklemek için eklenmiştir. Daha fazla bilgi için bkz. [Genel türler](generics-cpp-component-extensions.md).

|Sözcükle|Bağlama duyarlı|Amaç|
|-------------|-----------------------|-------------|
|**yorlar**|Hayır|Genel bir tür bildirir.|
|**olmadığı**|Yes|Genel tür parametresine uygulanan kısıtlamaları belirtir.|

## <a name="miscellaneous-keywords"></a>Çeşitli anahtar sözcükler

Aşağıdaki anahtar sözcükler C++ uzantılarına eklenmiştir.

|Sözcükle|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**finally**|Yes|Varsayılan özel durum handller davranışını gösterir.|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|
|**for each, in**|Hayır|Bir koleksiyonun öğelerini numaralandırır.|[for each, in](../dotnet/for-each-in.md)|
|**gcnew**|Hayır|Atık toplanan yığında türleri ayırır. Ve yerine kullanın **`new`** **`delete`** .|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**Yeni başvuru**|Yes|Windows Çalışma Zamanı türünü ayırır. Ve yerine kullanın **`new`** **`delete`** .|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|Yes|Üyenin yalnızca bildirimde veya statik oluşturucuda başlatılabileceğini belirtir.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**ayarını**|Yes|Değişmez değer değişkeni oluşturur.|[ayarını](literal-cpp-component-extensions.md)|
|**`nullptr`**|Hayır|Bir tanıtıcı veya işaretçinin bir nesneyi işaret içermediğini belirtir.|[nullptr](nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>Şablon yapıları

Aşağıdaki dil yapıları, anahtar sözcükler yerine şablon olarak uygulanır. `/ZW`Derleyici seçeneğini belirtirseniz, bunlar `lang` ad alanında tanımlanır. `/clr`Derleyici seçeneğini belirtirseniz, bunlar `cli` ad alanında tanımlanır.

|Sözcükle|Amaç|Başvuru|
|-------------|-------------|---------------|
|**array**|Bir dizi bildirir.|[Diziler](arrays-cpp-component-extensions.md)|
|**interior_ptr**|(Yalnızca CLR) Başvuru türündeki verileri gösterir.|[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)|
|**pin_ptr**|(Yalnızca CLR) Çöp toplama sisteminin geçici olarak görüntülenmesini sağlamak için CLR başvuru türlerini işaret eder.|[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)|
|**safe_cast**|Çalışma zamanı türü için en iyi atama yöntemini belirler ve yürütür.|[safe_cast](safe-cast-cpp-component-extensions.md)|
|**`typeid`**|(Yalnızca CLR) <xref:System.Type?displayProperty=fullName>Verilen türü veya nesneyi açıklayan bir nesne alır.|[typeid](typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>Bildirimciler

Aşağıdaki tür Bildirimciler, çalışma zamanına ayrılan nesnelerin ömrünü ve silinmesini otomatik olarak yönetmesini ister.

|İşleç|Amaç|Başvuru|
|--------------|-------------|---------------|
|`^`|Bir nesneye yönelik bir tanıtıcı bildirir; diğer bir deyişle, artık kullanılabilir olmadığında otomatik olarak silinen Windows Çalışma Zamanı veya CLR nesnesine yönelik bir işaretçidir.|[Object Işlecine işle (^)](handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|Bir izleme başvurusu bildirir; diğer bir deyişle, artık kullanılabilir olmadığında otomatik olarak silinen Windows Çalışma Zamanı veya CLR nesnesine bir başvurudur.|[İzleme başvurusu Işleci](tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>Ek yapılar ve Ilgili konular

Bu bölümde, ek programlama yapıları ve CLR ile ilgili konular listelenmektedir.

|Konu|Açıklama|
|-----------|-----------------|
|[__tanımlayıcı (C++/CLI)](identifier-cpp-cli.md)|(Windows Çalışma Zamanı ve CLR) Anahtar sözcüklerin tanımlayıcı olarak kullanılmasına izin vermez.|
|[Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows Çalışma Zamanı ve CLR) Bir işlevin değişken sayıda bağımsız değişken almasını sağlar.|
|[C++ Yerel Türlerinin .NET Framework Eşdeğerleri (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ integral türlerinin yerine kullanılan CLR türlerini listeler.|
|[AppDomain](../cpp/appdomain.md) **`__declspec`** icisi|**`__declspec`** statik ve genel değişkenlerin AppDomain başına mevcut olduğunu belirten değiştirici.|
|[/Clr ile C stili atamalar (C++/CLı)](c-style-casts-with-clr-cpp-cli.md)|C stili, nasıl yorumlandığını açıklar.|
|çağırma kuralı [__clrcall](../cpp/clrcall.md)|CLR uyumlu çağırma kuralını gösterir.|
|`__cplusplus_cli`|[Önceden Tanımlı Makrolar](../preprocessor/predefined-macros.md)|
|[Özel öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kendi CLR öznitelerinizi nasıl tanımlayacağınızı açıklar.|
|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|Özel durum işlemeye genel bir bakış sağlar.|
|[Açık geçersiz kılmalar](explicit-overrides-cpp-component-extensions.md)|Üye işlevlerin rastgele üyeleri nasıl geçersiz kılabileceğinizi gösterir.|
|[Arkadaş derlemeler (C++)](../dotnet/friend-assemblies-cpp.md)|Bir istemci derlemesinin bir derleme bileşenindeki tüm türlere nasıl erişebileceğinizi açıklar.|
|[Kutulama](boxing-cpp-component-extensions.md)|Değer türlerinin kutulanmış olduğu koşulları gösterir.|
|[Tür nitelikleri için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md)|Derleme zamanında türlerin özelliklerinin nasıl algılanacağını açıklar.|
|[yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmalar|Yönetilen ve yönetilmeyen işlevlerin aynı modülde nasıl ortak bulunabildiğini gösterir.|
|[işlem](../cpp/process.md) **`__declspec`** icisi|**`__declspec`** statik ve genel değişkenlerin işlem başına mevcut olduğunu belirten değiştirici.|
|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Çalışma zamanı tür bilgilerinin CLR sürümünü gösterir.|
|[Dize](string-cpp-component-extensions.md)|Dize sabit değerlerinin derleyicinin dönüştürülmesini açıklar <xref:System.String> .|
|[Tür İletme (C++/CLI)](type-forwarding-cpp-cli.md)|İstemci kodunun yeniden derlenmesi zorunda olmaması için, bir sevkiyat derlemesinde bir türün başka bir derlemeye taşınmasını sağlar.|
|[Kullanıcı tanımlı öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kullanıcı tanımlı öznitelikleri gösterir.|
|[#using yönergesi](../preprocessor/hash-using-directive-cpp.md)|Dış derlemeleri içeri aktarır.|
|[XML belgeleri](../build/reference/xml-documentation-visual-cpp.md)|[/Doc (Işlem belgeleri açıklamaları)](../build/reference/doc-process-documentation-comments-c-cpp.md) kullanılarak XML tabanlı kod belgelerini açıklar (C/C++)|

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
