---
title: "Çalışma zamanı platformları için bileşen uzantıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- Visual C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e32057e17614da98c78d877fe95180dd02500909
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="component-extensions-for-runtime-platforms"></a>Çalışma Zamanı Platformları için Bileşen Uzantıları
Visual C++, programın çalışma zamanı platformları karşı yardımcı olmak için dil uzantıları sağlar. Kullanarak C + +/ CX, program Evrensel Windows platformu uygulamaları ve yerel kodu derleme bileşenleri. C + kullanarak doğrudan Windows çalışma zamanı COM arabirimleri karşı programlama tarafından Evrensel Windows platformu uygulamaları oluşturabilirsiniz ancak +/ CX, Oluşturucular, özel durumlar ve diğer modern C++ deyimleri programlama ile çalışabilir. C++ programlama .NET platformu yönetilen yürütme ortamında etkinleştirmek için C + kullanabileceğiniz +/ CLI.  
  
 **İki çalışma zamanları, bir uzantı kümesinin**  
  
 C + +/ CX olan bir alt kümesini C + +/ CLI. C + için ortak olan uzantıları için +/ CX ve C + +/ CLI, semantiğini bağlıdır, ortak dil çalışma zamanı (CLR) veya Windows çalışma zamanı hedefleme üzerinde. Windows çalışma zamanı'çalıştırmak için uygulamanızı derlemeye belirtin **/ZW** derleyici seçeneği. CLR üzerinde çalışmasına derlemek için belirtmek **/CLR** derleyici seçeneği. Bir proje oluşturmak için Visual Studio kullandığınızda bu anahtarları otomatik olarak ayarlanır.  
  
 C++'da evrensel Windows platformu uygulamaları oluşturma hakkında daha fazla bilgi için bkz: [C++ kullanarak yol haritası için Windows çalışma zamanı uygulamaları](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 C + +/ CLI ISO/ANSI C++ Standart genişletir ve Ecma C + altında tanımlanan +/ CLI standart. Daha fazla bilgi için bkz: [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## <a name="data-type-keywords"></a>Veri türü anahtar sözcükler  
 Dil uzantıları dahil *toplama anahtar sözcükleri*, boşluk ile ayrılmış iki belirteçlerin oluşur anahtar sözcükleri olduğu. Birlikte kullanıldığında belirteçleri ayrı olarak kullanıldığında bir anlam ve başka bir anlama sahip olabilir. Örneğin, "ref" normal bir tanımlayıcı sözcüktür ve "sınıf" yerel sınıfı bildiren bir anahtar sözcüktür. Ancak, bu sözcükleri birleştirilir forma `ref class`, sonuçta elde edilen toplam anahtar sözcüğü olarak bilinen bir varlık bildirir bir *çalışma zamanı sınıf*.  
  
 Uzantılar da dahil *bağlama duyarlı* anahtar sözcükler. Bir anahtar olarak bağlama duyarlı ve o deyiminde yerleşimi içeren ifade türünü bağlı olarak kabul edilir. Örneğin, "özellik" belirteci tanımlayıcı olabilir veya özel türde bir ortak sınıf üyesi bildirebilirsiniz.  
  
 Aşağıdaki tabloda C++ dili uzantısında anahtar sözcükleri listeler.  
  
|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|  
|-------------|-----------------------|-------------|---------------|  
|`ref class`<br /><br /> `ref struct`|Hayır|Bir sınıf bildirir.|[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Hayır|Değer sınıfı bildirir.|[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Hayır|Arabirim bildirir.|[arabirim sınıfı](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Hayır|Numaralandırma bildirir.|[Enum sınıfı](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Evet|Bir özelliği bildirir.|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Evet|Bir temsilci bildirir.|[temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Evet|Bir olayı bildirir.|[event](../windows/event-cpp-component-extensions.md)|  
  
## <a name="override-specifiers"></a>Geçersiz Kılma Tanımlayıcıları  
 Geçersiz kılma davranışını türetme nitelemek için aşağıdaki anahtar sözcükler kullanabilirsiniz. Ancak `new` anahtar sözcüğü C++ uzantısı değil, çünkü ek bir bağlamda kullanılabilir burada listelenir. Bazı tanımlayıcıları da yerel programlama için geçerlidir. Daha fazla bilgi için bkz: [nasıl yapılır: yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|  
|-------------|-----------------------|-------------|---------------|  
|`abstract`|Evet|İşlevleri veya sınıflarının soyut olduğunu gösterir.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Hayır|Bir işlevi geçersiz kılma bir temel sınıf sürümü olmadığını gösterir.|[Yeni (vtable'de yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Evet|Bir geçersiz kılma bir temel sınıf sürümünün bir yöntemi olması gerektiğini gösterir.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Evet|Sınıflar temel sınıf olarak kullanılan engeller.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## <a name="keywords-for-generics"></a>Genel türler için anahtar sözcükleri  
 Aşağıdaki anahtar sözcükler, genel türlerini desteklemek için eklenmiştir. Daha fazla bilgi için bkz: [genel türler](../windows/generics-cpp-component-extensions.md).  
  
|Anahtar sözcüğü|Bağlama duyarlı|Amaç|  
|-------------|-----------------------|-------------|  
|`generic`|Hayır|Genel bir tür bildirir.|  
|`where`|Evet|Genel tür parametresi uygulanır kısıtlamaları belirtir.|  
  
## <a name="miscellaneous-keywords"></a>Çeşitli anahtar sözcükleri  
 Aşağıdaki anahtar sözcükler C++ uzantıları eklenmiştir.  
  
|Anahtar sözcüğü|Bağlama duyarlı|Amaç|Başvuru|  
|-------------|-----------------------|-------------|---------------|  
|`finally`|Evet|Varsayılan özel durum handlings davranış gösterir.|[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Hayır|Bir koleksiyonun öğelerini numaralandırır.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|Hayır|Çöp toplanan yığın türlerinde ayırır. Yerine kullanmak `new` ve `delete`.|[Yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Evet|Windows çalışma zamanı türü ayırır. Yerine kullanmak `new` ve `delete`.|[Yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Evet|Üye yalnızca bildirim veya statik Oluşturucu başlatılabilir olduğunu gösterir.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Evet|Değişmez değer bir değişken oluşturur.|[değişmez değer](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Hayır|Bir tanıtıcı veya işaretçi bir nesnede göstermiyor gösterir.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## <a name="template-constructs"></a>Şablon yapıları  
 Aşağıdaki dil yapıları olarak anahtar sözcükler yerine şablonları olarak uygulanır. Belirtirseniz **/ZW** derleyici seçeneği, bunlar tanımlanmış `lang` ad alanı. Belirtirseniz **/CLR** derleyici seçeneği, bunlar tanımlanmış `cli` ad alanı.  
  
|Anahtar sözcüğü|Amaç|Başvuru|  
|-------------|-------------|---------------|  
|`array`|Bir dizi bildirir.|[Diziler](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|(Yalnızca CLR) Bir başvuru veri noktalarına yazın.|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|(Yalnızca CLR) Çöp toplama sistem geçici olarak engellemek için CLR başvuru türleri noktalarına.|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|Belirler ve bir çalışma zamanı türü için en iyi atama yöntemini yürütür.|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|(Yalnızca CLR) Alır bir <xref:System.Type?displayProperty=fullName> verilen türü veya nesne tanımlayan nesne.|[TypeId](../windows/typeid-cpp-component-extensions.md)|  
  
## <a name="declarators"></a>Bildirimciler  
 Aşağıdaki türü Bildirimciler yaşam süresi ve ayrılmış nesne silme işlemlerini otomatik olarak yönetmek için çalışma zamanı isteyin.  
  
|İşleç|Amaç|Başvuru|  
|--------------|-------------|---------------|  
|`^`|Bir nesne için bir tanıtıcı bildirir; diğer bir deyişle, artık kullanılabilir olduğunda, otomatik olarak silinir Windows çalışma zamanı veya CLR nesnesine bir işaretçi.|[Nesne işleci (^) işleme](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|İzleme başvurusu bildirir; diğer bir deyişle, artık kullanılabilir olduğunda otomatik olarak silinir bir Windows çalışma zamanı veya CLR nesnesi bir başvuru.|[İzleme başvurusu işleci](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## <a name="additional-constructs-and-related-topics"></a>Ek yapıları ve ilgili konular  
 Bu bölümde ek programlama yapılarını ve CLR ilgilidir konuları listelenmiştir.  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[__tanımlayıcı (C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Anahtar sözcükler kullanımını tanımlayıcıları etkinleştirir.|  
|[Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows çalışma zamanı ve CLR) Değişken sayıda bağımsız değişken yapılacak bir işlev sağlar.|  
|[C++ Yerel Türlerinin .NET Framework Eşdeğerleri (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ tam sayı türleri yerine kullanılan CLR türlerini listeler.|  
|[AppDomain](../cpp/appdomain.md) `__declspec` değiştiricisi|`__declspec`Statik ve genel değişkenler appdomain mevcut olması zorunlu tutulmuştur değiştiricisi.|  
|[/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|C türü atamalar nasıl yorumlanması gerektiğini açıklar.|  
|[__clrcall](../cpp/clrcall.md) çağırma|CLR uyumlu çağırma gösterir.|  
|`__cplusplus_cli`|[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)|  
|[Özel öznitelikler](../windows/custom-attributes-cpp.md)|Kendi CLR öznitelikleri tanımlamak açıklar.|  
|[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)|Özel durum işleme genel bir bakış sağlar.|  
|[Açık geçersiz kılmalar](../windows/explicit-overrides-cpp-component-extensions.md)|Üye işlevleri rasgele üyeleri nasıl kılabilirsiniz gösterir.|  
|[Arkadaş Derlemeler (C++)](../dotnet/friend-assemblies-cpp.md)|Bir istemci derleme bir derleme bileşeninin içindeki tüm türler nasıl erişebileceğiniz açıklanır.|  
|[Kutulama](../windows/boxing-cpp-component-extensions.md)|Hangi değerlerin türleri Kutulu koşulları gösterir.|  
|[Tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Derleme zamanında türleri özelliklerini algılamak nasıl açıklanır.|  
|[yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) pragmaları|Yönetilen ve yönetilmeyen işlevleri gösterir aynı modülünde birlikte bulunabilir.|  
|[işlem](../cpp/process.md) `__declspec` değiştiricisi|`__declspec`Statik ve genel değişkenler her işlem mevcut olması zorunlu tutulmuştur değiştiricisi.|  
|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Çalışma zamanı türü bilgileri CLR sürümü gösterir.|  
|[Dize](../windows/string-cpp-component-extensions.md)|Dize değişmez değerleri derleyici dönüştürülmesi açıklanmaktadır <xref:System.String>.|  
|[Tür İletme (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|Böylece istemci kodunun derlenmesi yok türü başka bir derleme sevkiyat derlemede hareketini sağlar.|  
|[Kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md)|Kullanıcı tanımlı öznitelikleri gösterir.|  
|[#using yönergesi](../preprocessor/hash-using-directive-cpp.md)|Dış derlemeler alır.|  
|[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)|XML tabanlı kodu belgelerine kullanarak açıklar  [ /doc (işlem belgesi açıklamaları) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)