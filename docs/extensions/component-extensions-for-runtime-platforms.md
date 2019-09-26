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
ms.openlocfilehash: 1e47a138fece021cf015884222d8cf5c766655fd
ms.sourcegitcommit: 7750e4c291d56221c8893120c56a1fe6c9af60d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274677"
---
# <a name="component-extensions-for-net-and-uwp"></a>.NET ve UWP için Bileşen Uzantıları

Standart C++ , derleyici satıcılarının dile standart olmayan uzantılar sağlamasına izin verir. Microsoft, .NET Framework veya Evrensel Windows Platformu (UWP) C++ üzerinde çalışan koda yerel kod bağlamanıza yardımcı olacak uzantılar sağlar. .NET uzantıları/CLI olarak adlandırılır C++ve .NET yönetilen yürütme ortamında çalıştırılan ve ortak dil çalışma zamanı (CLR) olarak adlandırılan kodu üretir. UWP uzantılarına/CX adı verilir C++ve yerel makine kodu üretir.

> [!NOTE]
> Yeni uygulamalar için C++ C++/Cxyerine/Wınrt kullanmanızı öneririz. C++/Wınrt, Windows Çalışma Zamanı API 'Leri için yeni, standart bir C++ 17 dil projeksiyonu. /CX ve WRL 'yi C++desteklemeye devam edeceğiz, ancak yeni uygulamaların/Winrtı kullanmasını C++önemle tavsiye ederiz. Daha fazla bilgi için bkz [ C++./wınrt](/windows/uwp/cpp-and-winrt-apis/index).

### <a name="two-runtimes-one-set-of-extensions"></a>İki çalışma zamanı, bir dizi uzantı

C++/CLı, ISO/ANSI C++ standardını genişletir ve ECMA C++/CLI standart altında tanımlanmıştır. Daha fazla bilgi için bkz. [/CLI ( C++görsel C++) ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

/CX C++uzantıları,/cli'in C++bir alt kümesidir. Uzantı söz dizimi çoğu durumda özdeş olsa da, oluşturulan kod, UWP 'yi hedeflemek için `/ZW` derleyici seçeneğini belirtmenize `/clr` veya .net 'i hedeflemek için kullanabileceğiniz bir seçeneğe bağlıdır. Bu anahtarlar, bir proje oluşturmak için Visual Studio kullandığınızda otomatik olarak ayarlanır.

## <a name="data-type-keywords"></a>Veri türü anahtar sözcükleri

Dil uzantıları, boşluk ile ayrılmış iki belirteçden oluşan *toplama anahtar sözcüklerini*içerir. Belirteçlerin ayrı olarak kullanıldıkları bir anlamı olabilir ve birlikte kullanıldıkları bir anlamı vardır. Örneğin, "ref" sözcüğü sıradan bir tanımlayıcıdır ve "Class" sözcüğü, yerel bir sınıfı bildiren bir anahtar sözcüktür. Ancak, bu sözcükler form **başvuru sınıfında**birleştirildiğinde, elde edilen toplama anahtar sözcüğü, *çalışma zamanı sınıfı*olarak bilinen bir varlık bildirir.

Uzantılar ayrıca *bağlama duyarlı* anahtar sözcükler içerir. Anahtar sözcüğü, kendisini içeren deyimin türüne ve bu deyimdeki yerleşimine göre bağlama duyarlı olarak değerlendirilir. Örneğin, belirteç "özelliği" bir tanımlayıcı olabilir veya özel bir ortak sınıf üyesi türü bildirebilir.

Aşağıdaki tabloda C++ dil uzantısında anahtar sözcükler listelenmektedir.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**başvuru sınıfı**<br /><br /> **ref yapısı**|Hayır|Bir sınıf bildirir.|[Sınıflar ve Yapılar](classes-and-structs-cpp-component-extensions.md)|
|**değer sınıfı**<br /><br /> **value yapısı**|Hayır|Değer sınıfını bildirir.|[Sınıflar ve Yapılar](classes-and-structs-cpp-component-extensions.md)|
|**arabirim sınıfı**<br /><br /> **arabirim yapısı**|Hayır|Bir arabirim bildirir.|[arabirim sınıfı](interface-class-cpp-component-extensions.md)|
|**sabit listesi sınıfı**<br /><br /> **Enum yapısı**|Hayır|Bir sabit listesi bildirir.|[sabit listesi sınıfı](enum-class-cpp-component-extensions.md)|
|**property**|Evet|Bir özellik bildirir.|[property](property-cpp-component-extensions.md)|
|**delegate**|Evet|Bir temsilci bildirir.|[delegate (C++/CLI ve C++/CX)](delegate-cpp-component-extensions.md)|
|**event**|Evet|Bir olayı bildirir.|[event](event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Geçersiz Kılma Tanımlayıcıları

Türetme için geçersiz kılma davranışını nitelemek için aşağıdaki anahtar sözcükleri kullanabilirsiniz. **Yeni** anahtar sözcüğü bir uzantısı olmasa da C++, ek bir bağlamda kullanılabilmesi için burada listelenir. Bazı tanımlayıcılar yerel programlama için de geçerlidir. Daha fazla bilgi için [nasıl yapılır: Yerel derlemelerde (C++/CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)geçersiz kılma belirticileri bildirin.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**abstract**|Evet|İşlevlerin veya sınıfların soyut olduğunu gösterir.|[abstract](abstract-cpp-component-extensions.md)|
|**new**|Hayır|Bir işlevin temel sınıf sürümünün geçersiz kılınmadığını gösterir.|[yeni (vtable'de yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|Evet|Bir yöntemin temel sınıf sürümünün geçersiz kılınması olması gerektiğini belirtir.|[override](override-cpp-component-extensions.md)|
|**sealed**|Evet|Sınıfların temel sınıf olarak kullanılmasını önler.|[sealed](sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>Genel türler için anahtar sözcükler

Aşağıdaki anahtar sözcükler genel türleri desteklemek için eklenmiştir. Daha fazla bilgi için bkz. [Genel türler](generics-cpp-component-extensions.md).

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|
|-------------|-----------------------|-------------|
|**yorlar**|Hayır|Genel bir tür bildirir.|
|**olmadığı**|Evet|Genel tür parametresine uygulanan kısıtlamaları belirtir.|

## <a name="miscellaneous-keywords"></a>Çeşitli anahtar sözcükler

C++ Uzantılara aşağıdaki anahtar sözcükler eklenmiştir.

|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|
|-------------|-----------------------|-------------|---------------|
|**finally**|Evet|Varsayılan özel durum handller davranışını gösterir.|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|
|**for each, in**|Hayır|Bir koleksiyonun öğelerini numaralandırır.|[for each, in](../dotnet/for-each-in.md)|
|**gcnew**|Hayır|Atık toplanan yığında türleri ayırır. **New** ve **Delete**yerine kullanın.|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**Yeni başvuru**|Evet|Windows Çalışma Zamanı türünü ayırır. **New** ve **Delete**yerine kullanın.|[yeni başvuru, gcnew](ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|Evet|Üyenin yalnızca bildirimde veya statik oluşturucuda başlatılabileceğini belirtir.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**değişmez değer**|Evet|Değişmez değer değişkeni oluşturur.|[değişmez değer](literal-cpp-component-extensions.md)|
|**nullptr**|Hayır|Bir tanıtıcı veya işaretçinin bir nesneyi işaret içermediğini belirtir.|[nullptr](nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>Şablon yapıları

Aşağıdaki dil yapıları, anahtar sözcükler yerine şablon olarak uygulanır. `/ZW` Derleyici seçeneğini belirtirseniz, bunlar `lang` ad alanında tanımlanır. `/clr` Derleyici seçeneğini belirtirseniz, bunlar `cli` ad alanında tanımlanır.

|Anahtar sözcüğü|Amaç|Başvuru|
|-------------|-------------|---------------|
|**array**|Bir dizi bildirir.|[Diziler](arrays-cpp-component-extensions.md)|
|**interior_ptr**|(Yalnızca CLR) Başvuru türündeki verileri gösterir.|[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)|
|**pin_ptr**|(Yalnızca CLR) Çöp toplama sisteminin geçici olarak görüntülenmesini sağlamak için CLR başvuru türlerini işaret eder.|[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)|
|**safe_cast**|Çalışma zamanı türü için en iyi atama yöntemini belirler ve yürütür.|[safe_cast](safe-cast-cpp-component-extensions.md)|
|**typeid**|(Yalnızca CLR) Verilen türü <xref:System.Type?displayProperty=fullName> veya nesneyi açıklayan bir nesne alır.|[typeid](typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>Bildirimciler

Aşağıdaki tür Bildirimciler, çalışma zamanına ayrılan nesnelerin ömrünü ve silinmesini otomatik olarak yönetmesini ister.

|İşleç|Amaç|Başvuru|
|--------------|-------------|---------------|
|`^`|Bir nesneye yönelik bir tanıtıcı bildirir; diğer bir deyişle, artık kullanılabilir olmadığında otomatik olarak silinen Windows Çalışma Zamanı veya CLR nesnesine yönelik bir işaretçidir.|[İşlenecek Nesne İşleci (^)](handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|Bir izleme başvurusu bildirir; diğer bir deyişle, artık kullanılabilir olmadığında otomatik olarak silinen Windows Çalışma Zamanı veya CLR nesnesine bir başvurudur.|[İzleme Başvurusu İşleci](tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>Ek yapılar ve Ilgili konular

Bu bölümde, ek programlama yapıları ve CLR ile ilgili konular listelenmektedir.

|Konu|Açıklama|
|-----------|-----------------|
|[__tanımlayıcı (C++/CLI)](identifier-cpp-cli.md)|(Windows Çalışma Zamanı ve CLR) Anahtar sözcüklerin tanımlayıcı olarak kullanılmasına izin vermez.|
|[Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows Çalışma Zamanı ve CLR) Bir işlevin değişken sayıda bağımsız değişken almasını sağlar.|
|[C++ Yerel Türlerinin .NET Framework Eşdeğerleri (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ İntegral türlerinin yerıne kullanılan CLR türlerini listeler.|
|[AppDomain](../cpp/appdomain.md) **__declspec** değiştiricisi|statik ve genel değişkenlerin AppDomain başına mevcut olduğunu gösteren **__declspec** değiştiricisi.|
|[/Clr (C++/CLI) Ile C stili atamalar](c-style-casts-with-clr-cpp-cli.md)|C stili, nasıl yorumlandığını açıklar.|
|[__clrcall](../cpp/clrcall.md) çağrı kuralı|CLR uyumlu çağırma kuralını gösterir.|
|`__cplusplus_cli`|[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)|
|[Özel Öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kendi CLR öznitelerinizi nasıl tanımlayacağınızı açıklar.|
|[Özel Durum İşleme](exception-handling-cpp-component-extensions.md)|Özel durum işlemeye genel bir bakış sağlar.|
|[Açık Geçersiz Kılmalar](explicit-overrides-cpp-component-extensions.md)|Üye işlevlerin rastgele üyeleri nasıl geçersiz kılabileceğinizi gösterir.|
|[Arkadaş Derlemeler (C++)](../dotnet/friend-assemblies-cpp.md)|Bir istemci derlemesinin bir derleme bileşenindeki tüm türlere nasıl erişebileceğinizi açıklar.|
|[Kutulama](boxing-cpp-component-extensions.md)|Değer türlerinin kutulanmış olduğu koşulları gösterir.|
|[Tür Özellikleri için Derleyici Desteği](compiler-support-for-type-traits-cpp-component-extensions.md)|Derleme zamanında türlerin özelliklerinin nasıl algılanacağını açıklar.|
|[yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmalar|Yönetilen ve yönetilmeyen işlevlerin aynı modülde nasıl ortak bulunabildiğini gösterir.|
|[işlem](../cpp/process.md) **__declspec** değiştiricisi|statik ve genel değişkenlerin işlem başına mevcut olduğunu gösteren **__declspec** değiştiricisi.|
|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Çalışma zamanı tür bilgilerinin CLR sürümünü gösterir.|
|[Dize](string-cpp-component-extensions.md)|Dize sabit <xref:System.String>değerlerinin derleyicinin dönüştürülmesini açıklar.|
|[Tür İletme (C++/CLI)](type-forwarding-cpp-cli.md)|İstemci kodunun yeniden derlenmesi zorunda olmaması için, bir sevkiyat derlemesinde bir türün başka bir derlemeye taşınmasını sağlar.|
|[Kullanıcı Tanımlı Öznitelikler](user-defined-attributes-cpp-component-extensions.md)|Kullanıcı tanımlı öznitelikleri gösterir.|
|[#using yönergesi](../preprocessor/hash-using-directive-cpp.md)|Dış derlemeleri içeri aktarır.|
|[XML Belgeleri](../build/reference/xml-documentation-visual-cpp.md)|[/Doc (Işlem belgeleri açıklamaları)C++](../build/reference/doc-process-documentation-comments-c-cpp.md) kullanılarak XML tabanlı kod belgelerini açıklar (C/)|

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)