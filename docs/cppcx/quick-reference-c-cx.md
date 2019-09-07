---
title: Hızlı başvuru (C++/CX)
ms.date: 12/30/2016
ms.assetid: ba457195-26e5-43aa-b99d-24a871e550f4
ms.openlocfilehash: 2826105f7ec4a680208965fcc18a548c6ec4b795
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740914"
---
# <a name="quick-reference-ccx"></a>Hızlı başvuru (C++/CX)

Windows Çalışma Zamanı, yalnızca güvenilir bir işletim sistemi ortamında yürütülen Evrensel Windows Platformu (UWP) uygulamalarını destekler, yetkili işlevleri, veri türlerini ve cihazları kullanır ve Microsoft Store aracılığıyla dağıtılır. C++/CX Windows çalışma zamanı uygulama yazma işlemini basitleştirir. Bu makale hızlı bir başvurudur; daha kapsamlı belgeler için bkz. [System](../cppcx/type-system-c-cx.md).

Komut satırında derleme yaptığınızda, bir UWP uygulaması veya Windows Çalışma Zamanı bileşeni oluşturmak için **/ZW** derleyici seçeneğini kullanın. Windows çalışma zamanı meta veri (. winmd) dosyalarında tanımlanan Windows çalışma zamanı bildirimlerine erişmek için `#using` yönergesini veya **/Fu** derleyici seçeneğini belirtin. UWP uygulaması için bir proje oluşturduğunuzda, Visual Studio varsayılan olarak bu seçenekleri ayarlar ve tüm Windows Çalışma Zamanı kitaplıklarına başvurular ekler.

## <a name="quick-reference"></a>Hızlı başvuru

|Kavram|Standart C++|C++/CX|Açıklamalar|
|-------------|--------------------|------------------------------------------------------------------|-------------|
|Temel türler|C++temel türler.|C++Windows Çalışma Zamanı tanımlanan temel türleri uygulayan/CX temel türleri.|Ad alanı/CX yerleşik, temel türler içerir C++ `default` Derleyici,/CX temel C++türlerini standart C++ türlere dolaylı olarak eşler.<br /><br /> Ad `Platform` alanı ailesi, temel Windows çalışma zamanı türlerini uygulayan türler içerir.|
||`bool`|`bool`|8 bit Boolean değeri.|
||`__wchar_t`|`char16`|Unicode (UTF-16) kod noktasını temsil eden 16 bit sayısal sayısal bir değer.|
||`short`<br /><br /> `unsigned short`|`int16`<br /><br /> `uint16`|16 bit işaretli tamsayı.<br /><br /> 16 bitlik işaretsiz tamsayı.|
||`int`<br /><br /> `unsigned int`|`int`<br /><br /> `uint32`|32 bitlik işaretli tamsayı.<br /><br /> 32 bitlik işaretsiz tamsayı.|
||`long long`veya`__int64`<br /><br /> `unsigned long long`|`int64`<br /><br /> `uint64`|64 bitlik işaretli tamsayı.<br /><br /> 64 bitlik işaretsiz tamsayı.|
||`float, double`|`float32, float64`|32 bit veya 64 bit IEEE 754 kayan noktalı sayı.|
||`enum {}`|`enum class {}`<br /><br /> -veya-<br /><br /> `enum struct {}`|32 bitlik bir numaralandırma.|
||(Uygulanmaz)|`Platform::Guid`|`Platform` Ad alanında 128 bitlik sayısal olmayan bir değer (bir GUID).|
||`std::time_get`|`Windows::Foundation::DateTime`|Bir tarih-saat yapısı.|
||(Uygulanmaz)|`Windows::Foundation::TimeSpan`|Bir TimeSpan yapısı.|
||(Uygulanmaz)|`Platform::Object^`|Windows Çalışma Zamanı türü sisteminin C++ görünümündeki başvuru sayılı temel nesne.|
||`std::wstring`<br /><br /> `L"..."`|`Platform::String^`|`Platform::String^`, metin temsil eden, başvuru sayılı, sabit ve Unicode karakterlerinden oluşan bir dizidir.|
|Çağrısı|Nesne işaretçisi (`*`):<br /><br /> `std::shared_ptr`|-Object (`^`, "hat") öğesini işle:<br /><br /> *T ^ tanımlayıcı*|Tüm Windows Çalışma Zamanı sınıfları, tanıtıcıdan nesneye değiştirici kullanılarak belirtilir. Nesnenin üyelerine, ok (`->`) sınıfı-üye-erişim işleci kullanılarak erişilir.<br /><br /> Hat değiştiricisi, "otomatik olarak başvuruda bulunan bir Windows Çalışma Zamanı nesnesine işaretçi" anlamına gelir. Daha kesin olarak,-Object, derleyicinin nesnenin başvuru sayısını otomatik olarak yönetmesi için kod eklemesi gerektiğini bildirir ve başvuru sayısı sıfır olursa nesneyi siler.|
|Başvuru|Bir nesneye (`&`) başvuru:<br /><br /> *T* tanımlayıcı`&`|İzleme başvurusu (`%`):<br /><br /> *T* tanımlayıcı`%`|Yalnızca Windows Çalışma Zamanı türler izleme başvuru değiştiricisi kullanılarak bildirilebilecek. Nesnesinin üyelerine, nokta (`.`) sınıfı-üye-erişim işleci kullanılarak erişilir.<br /><br /> İzleme başvurusu, "otomatik olarak başvuru sayılan bir Windows Çalışma Zamanı nesnesine başvuru" anlamına gelir. Daha kesin olarak, bir izleme başvurusu derleyicinin nesnenin başvuru sayısını otomatik olarak yönetmesi için kod eklemesi gerektiğini bildirir ve başvuru sayısı sıfır olursa nesneyi siler.|
|Dinamik tür bildirimi|`new`|`ref new`|Windows Çalışma Zamanı nesnesini ayırır ve sonra bu nesneye bir tanıtıcı döndürür.|
|Nesne ömrü yönetimi|`delete`*tanımlayıcı*<br /><br /> `delete[]`  *Tanımlayıcısını*|(Yıkıcıyı çağırır.)|Ömür, başvuru sayımına göre belirlenir. Delete çağrısı yıkıcıyı çağırır ancak kendisi belleği serbest vermez.|
|Dizi bildirimi|*T tanımlayıcı*`[]`<br /><br /> `std::array`*tanımlayıcı*|`Array<`*T* `^>^` *tanımlayıcı* boyutu `(``)`<br /><br /> -veya-<br /><br /> `WriteOnlyArray<`*T* `^>` *tanımlayıcı* boyutu `(`  `)`|T ^ türünde tek boyutlu değiştirilebilir veya salt yazılır dizi bildirir. Dizinin kendisi de, tanıtıcı-nesne değiştiricisi kullanılarak bildirilmelidir olması gereken bir başvuru sayılı nesnedir.<br /><br /> (Dizi bildirimleri, `Platform` ad alanındaki bir şablon üst bilgi sınıfını kullanır.)|
|Sınıf bildirimi|`class`  *tanımlayıcı*`{}`<br /><br /> `struct`  *Tanımlayıcı* `{}`|`ref class`  *Tanımlayıcı* `{}`<br /><br /> `ref struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirliği olan bir çalışma zamanı sınıfı bildirir.<br /><br /> Varsayılan genel erişilebilirliği olan bir çalışma zamanı sınıfı bildirir.|
|Yapı bildirimi|`struct`  *Tanımlayıcı* `{}`<br /><br /> (yani, düz bir eski veri yapısı (POD))|`value class`  *Tanımlayıcı* `{}`<br /><br /> `value struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirliği olan POD yapısını bildirir.<br /><br /> Değer sınıfı Windows meta verilerinde temsil edilebilir, ancak standart C++ bir sınıf olamaz.<br /><br /> Varsayılan genel erişilebilirliği olan POD yapısını bildirir.<br /><br /> Değer yapısı Windows meta verilerinde temsil edilebilir, ancak standart C++ bir struct olamaz.|
|Arabirim bildirimi|Yalnızca saf sanal işlevler içeren soyut sınıf.|`interface class`  *Tanımlayıcı* `{}`<br /><br /> `interface struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirliği olan bir arabirim bildirir.<br /><br /> Varsayılan genel erişilebilirliği olan bir arabirim bildirir.|
|Temsilci|`std::function`|`public delegate`*dönüş türü* *temsilci türü tanımlayıcı* *[parametreler]* `(``);`|İşlev çağrısı gibi çağrılabilecek bir nesne bildirir.|
|Olay|(Uygulanmaz)|`event`*temsilci türü tanımlayıcı* *olay tanımlayıcısı*`;`<br /><br /> *temsilci türü tanımlayıcı* *temsilci-tanımlayıcı*  = Delegate-Type-Identifier`( this`[, Parameters] `ref new``);`<br /><br /> *olay tanımlayıcısı* *temsilci-tanımlayıcı* `+=``;`<br /><br /> -veya-<br /><br /> `EventRegistrationToken`*belirteç tanımlayıcısı*objolaytanımlayıcı`+=`*temsilci-* tanımlayıcı  = `.``;`<br /><br /> -veya-<br /><br /> `auto`*belirteç tanımlayıcısı*  =  *obj*. *olay tanımlayıcısı* *temsilci-tanımlayıcı* `::add(``);`<br /><br /> *obj* Olay tanımlayıcı *belirteci-tanımlayıcı* `.` `-=``;`<br /><br /> -veya-<br /><br /> *obj* Olay tanımlayıcı *belirteci-tanımlayıcı* `.` `::remove(``);`|Bir olay gerçekleştiğinde çağrılan olay işleyicilerinin (Temsilciler) koleksiyonunu depolayan bir olay nesnesi bildirir.<br /><br /> Bir olay işleyicisi oluşturur.<br /><br /> Bir olay işleyicisi ekler.<br /><br /> Olay işleyicisi ekleme bir olay belirteci (*belirteç tanımlayıcısı*) döndürür. Olay işleyicisini açıkça kaldırmak istiyorsanız, daha sonra kullanmak üzere olay belirtecini kaydetmeniz gerekir.<br /><br /> Bir olay işleyicisini kaldırır.<br /><br /> Bir olay işleyicisini kaldırmak için, olay işleyicisi eklendiğinde kaydettiğiniz olay belirtecini belirtmeniz gerekir.|
|Özellik|(Uygulanmaz)|`property`*T* *tanımlayıcı*;<br /><br /> `property`*T* *tanımlayıcı* dizini`[``];`<br /><br /> `property`*T* dizini`default[``];`|Bir sınıf veya nesne üye işlevine, bir veri üyesine veya dizinli dizi öğesine erişmek için kullanılan söz dizimini kullanarak erişildiğini bildirir.<br /><br /> Bir sınıf veya nesne üye işlevinde bir özellik bildirir.<br /><br /> Bir nesne üye işlevinde dizinli bir özellik bildirir.<br /><br /> Bir sınıf üyesi işlevinde dizinli bir özellik bildirir.|
|Parametreli türler|templates|`generic <typename`*T* tanımlayıcı`> interface class``{}`<br /><br /> `generic <typename` T`> delegate` *[Return-Type]* *temsilci-tanımlayıcı*`() {}`|Parametreli bir arabirim sınıfı bildirir.<br /><br /> Parametreli bir temsilci bildirir.|
|Null yapılabilir değer türleri|`boost::optional<T>`|[Platform:: Ibox \<T >](../cppcx/platform-ibox-interface.md)|Skaler türdeki ve değer yapıların değişkenlerinin değerine `nullptr`sahip olmasını sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
