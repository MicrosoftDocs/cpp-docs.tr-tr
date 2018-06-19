---
title: Hızlı Başvuru (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ba457195-26e5-43aa-b99d-24a871e550f4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 830c27d89e427e2ea36a68d891aac0ebadcf3f21
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092564"
---
# <a name="quick-reference-ccx"></a>Hızlı Başvuru (C + +/ CX)
Windows çalışma zamanı yalnızca güvenilir işletim sistemi ortamında yürütmek, yetkili İşlevler, veri türleri ve cihazlar kullanır ve Microsoft Store dağıtılan Evrensel Windows Platformu (UWP) uygulamaları destekler. C + +/ CX uygulamaları yazma Windows çalışma zamanı için basitleştirin. Bu makalede Hızlı Başvuru değildir; daha eksiksiz belgeler için bkz: [tür sistemi](../cppcx/type-system-c-cx.md) ve [çalışma zamanı platformları için bileşen uzantıları](http://go.microsoft.com/fwlink/p/?linkid=228720).  
  
 Komut satırında derlerken kullanmak **/ZW** derleyici seçeneği bir UWP uygulaması veya Windows çalışma zamanı bileşeni oluşturma. Windows çalışma zamanı meta verileri (.winmd) dosyalarında tanımlanan, Windows çalışma zamanı bildirimleri erişmeye belirtin `#using` yönergesi veya **/FU** derleyici seçeneği. Bir UWP uygulaması için bir proje oluşturduğunuzda, varsayılan olarak Visual Studio bu seçenekleri ayarlar ve tüm Windows çalışma zamanı kitaplıkları başvuruları ekler.  
  
## <a name="quick-reference"></a>Hızlı Başvuru  
  
|Kavram|Standart C++|C++/CX|Açıklamalar|  
|-------------|--------------------|------------------------------------------------------------------|-------------|  
|Temel türler|C++ temel türleri.|C + +/ CX Windows çalışma zamanı'nda tanımlanan temel türleri uygulayan temel türler.|`default` Ad alanında C + +/ CX yerleşik, temel türleri. Derleyici örtük olarak C + eşlemeleri +/ CX standart C++ türleri için temel türü.<br /><br /> `Platform` Ailesi ad alanları, temel Windows çalışma zamanı türleri uygulayan türler içerir.|  
||`bool`|`bool`|Bir 8 bit Boole değeri.|  
||`__wchar_t`|`char16`|Unicode (UTF-16) kod noktası temsil eden bir 16 bit sayısal değer.|  
||`short`<br /><br /> `unsigned short`|`int16`<br /><br /> `uint16`|Bir 16 bit işaretli tamsayıyı.<br /><br /> Bir 16 bit işaretsiz tamsayı.|  
||`int`<br /><br /> `unsigned int`|`int`<br /><br /> `uint32`|32 bit imzalı bir tamsayı.<br /><br /> Bir 32 bit işaretsiz tamsayı.|  
||`long long` - veya - `__int64`<br /><br /> `unsigned long long`|`int64`<br /><br /> `uint64`|64-bit imzalı bir tamsayı.<br /><br /> Bir 64-bit işaretsiz tamsayı.|  
||`float, double`|`float32, float64`|Bir 32 bit veya 64-bit IEEE 754 kayan noktalı sayı.|  
||`enum {}`|`enum class {}`<br /><br /> -veya-<br /><br /> `enum struct {}`|Bir 32 bit numaralandırması.|  
||(Geçerli değildir)|`Platform::Guid`|Bir 128-bit sayısal değer (GUID) `Platform` ad alanı.|  
||`std::time_get`|`Windows::Foundation::DateTime`|Bir tarih-saat yapısı.|  
||(Geçerli değildir)|`Windows::Foundation::TimeSpan`|Bir timespan yapısı.|  
||(Geçerli değildir)|`Platform::Object^`|Başvuruları sayılan temel nesne C++ görünümünde Windows çalışma zamanı tür sistemi.|  
||`std::wstring`<br /><br /> `L"..."`|`Platform::String^`|`Platform::String^` başvuruları sayılan, sabit, metin temsil Unicode karakterler dizisidir.|  
|İşaretçi|Nesne işaretçisi (`*`):<br /><br /> `std::shared_ptr`|Tanıtıcı nesnesi (`^`, "hat" denilir):<br /><br /> *T ^ tanımlayıcısı*|Tüm Windows çalışma zamanı sınıfları tanıtıcı nesnesi değiştiricisi kullanarak bildirilir. Nesne üyeleri ok kullanarak erişilebilir (`->`) sınıf üye erişimi işleci.<br /><br /> Hat değiştiricisi "otomatik olarak başvurusu olan bir Windows çalışma zamanı nesne işaretçisi sayılır." anlamına gelir. Daha hassas bir şekilde tanıtıcı nesnesi derleyici nesnenin başvuru sayısı otomatik olarak yönetmek için kodu ekleyin ve başvuru sayısı sıfır olursa nesne silin bildirir.|  
|Başvuru|Bir nesneye başvuru (`&`):<br /><br /> *T* `&` *tanımlayıcısı*|İzleme başvurusu (`%`):<br /><br /> *T* `%` *tanımlayıcısı*|Sadece Windows türleri izleme kullanılarak bildirilebilir çalışma zamanı değiştiricisi başvuru. Nesne üyeleri nokta kullanılarak erişilir (`.`) sınıf üye erişimi işleci.<br /><br /> İzleme başvurusu "otomatik olarak sayılan başvurusu olan bir Windows çalışma zamanı nesne referansı." anlamına gelir. Daha hassas bir şekilde izleme başvurusu, derleyici nesnenin başvuru sayısı otomatik olarak yönetmek için kodu ekleyin ve başvuru sayısı sıfır olursa nesne silin bildirir.|  
|Dinamik tür bildirimi|`new`|`ref new`|Windows çalışma zamanı nesne ayırır ve ardından bu nesne için bir işleyici döner.|  
|nesne ömrü Yönetimi|`delete` *Tanımlayıcı*<br /><br /> `delete[]`  *Tanımlayıcı*|(Yıkıcı çağırır.)|Yaşam süresi, başvuru sayımı tarafından belirlenir. Silme çağrısı yıkıcı çağırır ancak kendi bellek boş değil.|  
|dizi bildirimi|*T tanımlayıcısı* `[]`<br /><br /> `std::array` *Tanımlayıcı*|`Array<` *T* `^>^` *tanımlayıcısı* `(` *boyutu* `)`<br /><br /> -veya-<br /><br /> `WriteOnlyArray<` *T* `^>` *tanımlayıcısı* `(` *boyutu* `)`|Tek boyutlu değiştirilebilir veya sadece yazılabilir dizi T türü tanımlarken ^. Kendisi ayrıca tanıtıcı nesnesi değiştiricisi kullanılarak bildirilmelidir başvuruları sayılan bir nesne dizidir.<br /><br /> (Dizi bildirimleri kullanın, bir şablon üstbilgi sınıfı `Platform` ad.)|  
|Sınıf bildirimi|`class`  *Tanımlayıcı* `{}`<br /><br /> `struct`  *Tanımlayıcı* `{}`|`ref class`  *Tanımlayıcı* `{}`<br /><br /> `ref struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirlik olan bir çalışma zamanı sınıfı bildirir.<br /><br /> Varsayılan ortak erişilebilirlik olan bir çalışma zamanı sınıfı bildirir.|  
|Yapı bildirimleri|`struct`  *Tanımlayıcı* `{}`<br /><br /> (diğer bir deyişle, düz bir eski verileri (POD) yapısı)|`value class`  *Tanımlayıcı* `{}`<br /><br /> `value struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirlik sahip POD yapı bildirir.<br /><br /> Değer sınıfı Windows meta verilerde temsil edilebilir, ancak standart bir C++ sınıf olamaz.<br /><br /> Varsayılan ortak erişilebilirlik sahip POD yapı bildirir.<br /><br /> Değer yapı Windows meta verilerde temsil edilebilir, ancak standart C++ yapı olamaz.|  
|arabirim bildirimi|yalnızca saf sanal işlevleri içeren soyut sınıf.|`interface class`  *Tanımlayıcı* `{}`<br /><br /> `interface struct`  *Tanımlayıcı* `{}`|Varsayılan özel erişilebilirlik içeren bir arabirimdeki bildirir.<br /><br /> Varsayılan ortak erişilebilirlik içeren bir arabirimdeki bildirir.|  
|Temsilci|`std::function`|`public delegate` *dönüş türü* *temsilci türü tanımlayıcısı* `(` *[parametreler]* `);`|İşlev çağrısıyla çağrılabilen bir nesne bildirir.|  
|Olay|(Geçerli değildir)|`event` *temsilci türü tanımlayıcısı* *olay tanımlayıcısı* `;`<br /><br /> *temsilci türü tanımlayıcısı* *temsilci tanımlayıcı* = `ref new`*temsilci türü tanımlayıcısı*`( this`*[, parametreleri]*`);`<br /><br /> *Olay tanımlayıcısı* `+=` *temsilci tanımlayıcısı* `;`<br /><br /> -veya-<br /><br /> `EventRegistrationToken` *belirteç tanımlayıcı* = *obj*`.`*olay tanımlayıcısı*`+=`*temsilci tanımlayıcısı*`;`<br /><br /> -veya-<br /><br /> `auto` *belirteç tanımlayıcı* = *obj*. *olay tanımlayıcısı*`::add(`*temsilci tanımlayıcısı*`);`<br /><br /> *obj* `.` *olay tanımlayıcısı* `-=` *belirteci tanımlayıcısı* `;`<br /><br /> -veya-<br /><br /> *obj* `.` *olay tanımlayıcısı* `::remove(` *belirteci tanımlayıcısı* `);`|Bir olay gerçekleştiğinde, çağrılan olay işleyicileri (temsilcileri) koleksiyonunu depolayan bir olay nesnesi bildirir.<br /><br /> Bir olay işleyicisi oluşturur.<br /><br /> Olay işleyicisi ekler.<br /><br /> Olay işleyici ekleme, bir olay belirteci döndürür (*belirteci tanımlayıcısı*). Olay işleyicisi açıkça kaldırmak istiyorsanız, daha sonra kullanmak için olay belirteci kaydetmeniz gerekir.<br /><br /> Olay işleyici kaldırır.<br /><br /> Olay işleyici kaldırmak için olay işleyicisi eklendiğinde kaydettiğiniz olay belirteci belirtmeniz gerekir.|  
|Özellik|(Geçerli değildir)|`property` *T* *tanımlayıcısı*;<br /><br /> `property` *T* *tanımlayıcısı* `[` *dizini* `];`<br /><br /> `property` *T* `default[` *dizini* `];`|Sınıf veya nesne üye işlevi bir veri üyesi erişmek için kullanılan veya dizi öğe dizine sahip aynı sözdizimi kullanılarak erişilir bildirir.<br /><br /> Sınıf veya nesne üye işlevi üzerinde bir özelliği bildirir.<br /><br /> Bir dizin oluşturulmuş özellik üzerinde bir nesne üyesi işlevi bildirir.<br /><br /> Bir sınıf üyesi işlevi dizinli bir özelliği bildirir.|  
|Parametreli türler|templates|`generic <typename` *T* `> interface class` *tanımlayıcısı* `{}`<br /><br /> `generic <typename` *T* `> delegate` *[dönüş türü]* *temsilci tanımlayıcısı* `() {}`|Parametreli arabirimi sınıfı bildirir.<br /><br /> Parametreli temsilci bildirir.|  
|boş değer atanabilen değer türleri|`boost::optional<T>`|[Platform::IBox \<T >](../cppcx/platform-ibox-interface.md)|Skaler türleri ve değer yapılar bir değerine sahip olacak şekilde değişkenleri etkinleştirir `nullptr`.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)