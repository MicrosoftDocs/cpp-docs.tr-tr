---
title: Hızlı Başvuru (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ba457195-26e5-43aa-b99d-24a871e550f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b3ee46b2be08992fa3254edfbf2423b80dcabb1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102123"
---
# <a name="quick-reference-ccx"></a>Hızlı Başvuru (C + +/ CX)

Windows çalışma zamanı, yalnızca güvenilir işletim sistemi ortamında yürütme, yetkili İşlevler, veri türleri ve cihazlar kullanır ve Microsoft Store dağıtılan Evrensel Windows Platformu (UWP) uygulamaları destekler. C + +/ CX uygulamaların yazılmasını Windows çalışma zamanı için basitleştirin. Bu makalede hızlı bir referanstır; daha eksiksiz belgeler için bkz: [tür sistemi](../cppcx/type-system-c-cx.md).

Komut satırında oluşturduğunuzda, kullanmak **/ZW** bir UWP uygulaması veya Windows çalışma zamanı bileşeni oluşturmak için derleyici seçeneği. Windows çalışma zamanı meta veri (.winmd) dosyalarında tanımlanan, Windows çalışma zamanı bildirimleri erişmeye belirtin `#using` yönergesi veya **/FU** derleyici seçeneği. Bir UWP uygulaması için bir proje oluşturduğunuzda, varsayılan olarak Visual Studio bu seçenekler ayarlar ve tüm Windows çalışma zamanı kitaplıklarına başvurular ekler.

## <a name="quick-reference"></a>Hızlı Başvuru

|Kavram|Standart C++|C++/CX|Açıklamalar|
|-------------|--------------------|------------------------------------------------------------------|-------------|
|Temel türler|C++ temel türler.|C + +/ CX Windows çalışma zamanı'nda tanımlanan temel türleri uygulayan temel türler.|`default` Ad alanı içeren C + +/ CX yerleşik, temel türleri. Derleyici örtük olarak C + eşler +/ CX temel türler için standart C++ türler.<br /><br /> `Platform` Ailesi ad alanları temel Windows çalışma zamanı türleri uygulayan türler içerir.|
||`bool`|`bool`|Bir 8 bit Boole değeri.|
||`__wchar_t`|`char16`|Bir Unicode (UTF-16) kod noktasını temsil eden bir 16-bit sayısal değer.|
||`short`<br /><br /> `unsigned short`|`int16`<br /><br /> `uint16`|Bir 16 bitlik işaretli tamsayı.<br /><br /> Bir 16 bitlik işaretsiz tamsayı.|
||`int`<br /><br /> `unsigned int`|`int`<br /><br /> `uint32`|32-bit işaretli tamsayı.<br /><br /> 32-bit işaretsiz bir tamsayı.|
||`long long` - veya - `__int64`<br /><br /> `unsigned long long`|`int64`<br /><br /> `uint64`|64-bit imzalı bir tamsayı.<br /><br /> 64-bit işaretsiz bir tamsayı.|
||`float, double`|`float32, float64`|Bir 32 bit veya 64-bit IEEE 754 kayan noktalı sayı.|
||`enum {}`|`enum class {}`<br /><br /> veya<br /><br /> `enum struct {}`|Bir 32-bit sabit listesi.|
||(Geçerli değildir)|`Platform::Guid`|İçinde bir 128-bit sayısal değer (GUID) `Platform` ad alanı.|
||`std::time_get`|`Windows::Foundation::DateTime`|Bir tarih-saat yapısı.|
||(Geçerli değildir)|`Windows::Foundation::TimeSpan`|Bir timespan yapı.|
||(Geçerli değildir)|`Platform::Object^`|Başvuru sayılan temel nesne C++ görünümünde Windows çalışma zamanı tür sistemi.|
||`std::wstring`<br /><br /> `L"..."`|`Platform::String^`|`Platform::String^` bir başvuru sayılan, sabit, metin temsil eden Unicode karakter sırasıdır.|
|İşaretçi|Nesneye işaretçi (`*`):<br /><br /> `std::shared_ptr`|Tanıtıcı nesnesi (`^`, "hat" olarak okunur):<br /><br /> *T ^ tanımlayıcısı*|Tüm Windows çalışma zamanı sınıfları, tanıtıcı nesnesi değiştiricisini kullanarak bildirilir. Aşağı ok kullanarak bir nesnenin üyelerine erişilir (`->`) sınıfı üye erişimi işleci.<br /><br /> Hat değiştiricisi "otomatik olarak başvurusu olan bir Windows çalışma zamanı nesne işaretçisi hesaba katılır." anlamına gelir. Daha kesin tanıtıcı nesnesi derleyici nesnenin başvuru sayısının otomatik olarak yönetmek için kod ekleyin ve başvuru sayısı sıfır olursa nesneyi silmek olduğunu bildirir.|
|Başvuru|Bir nesneye başvuru (`&`):<br /><br /> *T* `&` *tanımlayıcısı*|İzleme başvurusu (`%`):<br /><br /> *T* `%` *tanımlayıcısı*|Yalnızca Windows Runtime türleri izleme kullanılarak bildirilebilir değiştiricisi başvuru. Nokta kullanarak bir nesnenin üyelerine erişilir (`.`) sınıfı üye erişimi işleci.<br /><br /> İzleme başvurusu "nesnesine bir başvuru sayılan başvuru otomatik olarak var olan bir Windows çalışma zamanı." anlamına gelir. Daha kesin bir izleme başvurusu derleyici nesnenin başvuru sayısının otomatik olarak yönetmek için kod ekleyin ve başvuru sayısı sıfır olursa nesneyi silmek olduğunu bildirir.|
|Dinamik tür bildirimi|`new`|`ref new`|Bir Windows çalışma zamanı nesnesi ayırır ve bu nesne için bir tanıtıcı döndürür.|
|Nesne ömrü Yönetimi|`delete` *tanımlayıcı*<br /><br /> `delete[]`  *tanımlayıcı*|(Yok edici çağırır.)|Yaşam süresi, başvuru sayımı tarafından belirlenir. Silme çağrısı yok Edicisi çağırır, ancak kendi bellek boş değil.|
|Dizi bildirimi|*T tanımlayıcısı* `[]`<br /><br /> `std::array` *tanımlayıcı*|`Array<` *T* `^>^` *tanımlayıcı* `(` *boyutu* `)`<br /><br /> veya<br /><br /> `WriteOnlyArray<` *T* `^>` *tanımlayıcı* `(` *boyutu* `)`|T türünde bir tek boyutlu değiştirilebilir veya salt yazılır diziyi bildirir ^. Kendisi ayrıca tanıtıcı nesnesi değiştirici kullanılarak bildirilmelidir başvuru sayılan bir nesne dizisidir.<br /><br /> (Dizi bildirimleri olan bir şablon başlığı sınıfı kullanın `Platform` ad.)|
|Sınıf bildirimi|`class`  *tanımlayıcı* `{}`<br /><br /> `struct`  *Tanımlayıcı* `{}`|`ref class`  *Tanımlayıcı* `{}`<br /><br /> `ref struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirliği olan bir çalışma zamanı sınıf bildirir.<br /><br /> Genel erişilebilirlik varsayılan bir çalışma zamanı sınıf bildirir.|
|Yapı bildirimleri|`struct`  *Tanımlayıcı* `{}`<br /><br /> (diğer bir deyişle, bir düz eski veri (POD) yapı)|`value class`  *Tanımlayıcı* `{}`<br /><br /> `value struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirlik sahip bir POD yapı bildirir.<br /><br /> Değer sınıfı Windows meta verileri temsil edilebilir, ancak standart bir C++ sınıfı olamaz.<br /><br /> Varsayılan Genel erişilebilirlik sahip bir POD yapı bildirir.<br /><br /> Değer yapısı Windows meta verileri temsil edilebilir, ancak standart bir C++ yapı olamaz.|
|Arabirim bildirimi|yalnızca saf sanal işlevler içeren, soyut sınıf.|`interface class`  *Tanımlayıcı* `{}`<br /><br /> `interface struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirlik arabirimdeki bildirir.<br /><br /> Varsayılan Genel erişilebilirlik arabirimdeki bildirir.|
|Temsilci|`std::function`|`public delegate` *dönüş türü* *temsilci türü tanımlayıcısı* `(` *[parametreler]* `);`|Bir işlev çağrısıyla çağrılabilen bir nesne bildirir.|
|Olay|(Geçerli değildir)|`event` *temsilci türü tanımlayıcısı* *olay tanımlayıcı* `;`<br /><br /> *temsilci türü tanımlayıcısı* *temsilci tanımlayıcısı* = `ref new`*temsilci türü tanımlayıcısı*`( this`*[, parametreler]*`);`<br /><br /> *Olay tanımlayıcı* `+=` *temsilci tanımlayıcısı* `;`<br /><br /> veya<br /><br /> `EventRegistrationToken` *belirteç tanımlayıcı* = *obj*`.`*olay tanımlayıcı*`+=`*temsilci tanımlayıcısı*`;`<br /><br /> veya<br /><br /> `auto` *belirteç tanımlayıcı* = *obj*. *olay tanımlayıcı*`::add(`*temsilci tanımlayıcısı*`);`<br /><br /> *obj* `.` *olay tanımlayıcı* `-=` *belirteç tanımlayıcı* `;`<br /><br /> veya<br /><br /> *obj* `.` *olay tanımlayıcı* `::remove(` *belirteç tanımlayıcı* `);`|Bir olay meydana geldiğinde çağrılan olay işleyicileri (temsilcileri) koleksiyonunu depolar bir olay nesne bildirir.<br /><br /> Bir olay işleyicisi oluşturur.<br /><br /> Bir olay işleyicisi ekler.<br /><br /> Olay işleyici ekleme, bir olay belirteç döndürür (*belirteç tanımlayıcı*). Olay işleyicisi açıkça kaldırmak istiyorsanız, daha sonra kullanmak için olay belirteci kaydetmeniz gerekir.<br /><br /> Bir olay işleyicisi kaldırır.<br /><br /> Bir olay işleyicisi kaldırmak için olay işleyicisi eklediğinizde kaydettiğiniz olay belirteç belirtmeniz gerekir.|
|Özellik|(Geçerli değildir)|`property` *T* *tanımlayıcı*;<br /><br /> `property` *T* *tanımlayıcı* `[` *dizini* `];`<br /><br /> `property` *T* `default[` *dizini* `];`|Bir sınıf veya nesne üye işlevi bir veri üyesine erişmek için kullanılan veya dizi öğesi dizine olan aynı söz dizimini kullanarak erişilir bildirir.<br /><br /> Bir sınıf veya nesne bir üye işlevi bir özelliği bildirir.<br /><br /> Dizinlenmiş bir özelliği bir nesne üye işlevini bildirir.<br /><br /> Bir sınıf üyesi işlevinde üzerinde dizinlenmiş bir özelliği bildirir.|
|Parametreli türler|templates|`generic <typename` *T* `> interface class` *tanımlayıcısı* `{}`<br /><br /> `generic <typename` *T* `> delegate` *return-type* *temsilci tanımlayıcısı* `() {}`|Bir parametreli arabirim sınıfı bildirir.<br /><br /> Parametreli bir temsilci bildirir.|
|Boş değer atanabilen değer türleri|`boost::optional<T>`|[Platform::ıbox \<T >](../cppcx/platform-ibox-interface.md)|Skaler türleri ve değer yapılar değerine sahip değişkenler sağlayan `nullptr`.|

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)