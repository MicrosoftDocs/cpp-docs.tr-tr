---
title: C++'da Sıralamaya Genel Bakış
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 0c7bf18fa823c6301a79c3f989efa73c9e8f628a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372006"
---
# <a name="overview-of-marshaling-in-ccli"></a>C++/CLI'de Mareşallik'e Genel Bakış

Karışık modda, bazen verilerinizi yerel ve yönetilen türler arasında denetlemeniz gerekir. *Mareşallik kitaplığı,* verileri basit bir şekilde dönüştürmenize ve dönüştürmenize yardımcı olur.  Mareşal kitaplığı bir dizi işlev `marshal_context` ve ortak türler için mareşalleme gerçekleştiren bir sınıf oluşur. Kitaplık, Visual Studio baskınızın **dahil/msclr** dizininde bu başlıklarda tanımlanır:

|Üst bilgi|Açıklama|
|---------------|-----------------|
|mareşal.h|`marshal_context`sınıf ve bağlamsız mareşalleme fonksiyonları|
|marshal_atl.h| ATL türlerini mareşalleme işlevleri|
|marshal_cppstd.h|Standart C++ türlerini mareşalleme işlevleri|
|marshal_windows.h|Windows türlerini mareşalleme işlevleri|

**msclr** klasörü için varsayılan yol, sahip olduğunuz sürüm ve yapı numarasına bağlı olarak buna benzer bir yoldur:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Marshal_context [Sınıfı](../dotnet/marshal-context-class.md)olan veya olmayan mareşallik kitaplığını kullanabilirsiniz. Bazı dönüşümler bir bağlam gerektirir. Diğer dönüşümler [marshal_as](../dotnet/marshal-as.md) işlevi kullanılarak uygulanabilir. Aşağıdaki tablo, desteklenen geçerli dönüşümleri, bir bağlam gerektireyip gerektirmediklerini ve hangi mareşal dosyasını eklemeniz gerektiğini listeler:

|Türünden|Yazmak için|Mareşal yöntemi|Dosya ekleme|
|---------------|-------------|--------------------|------------------|
|Sistem::String^|const char\*|Marshal_context|mareşal.h|
|const char\*|Sistem::String^|marshal_as|mareşal.h|
|Char\*|Sistem::String^|marshal_as|mareşal.h|
|Sistem::String^|const wchar_t\*|Marshal_context|mareşal.h|
|const wchar_t\*|Sistem::String^|marshal_as|mareşal.h|
|Wchar_t\*|Sistem::String^|marshal_as|mareşal.h|
|Sistem::IntPtr|Işlemek|marshal_as|marshal_windows.h|
|Işlemek|Sistem::IntPtr|marshal_as|marshal_windows.h|
|Sistem::String^|Bstr|Marshal_context|marshal_windows.h|
|Bstr|Sistem::String^|marshal_as|mareşal.h|
|Sistem::String^|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|Sistem::String^|marshal_as|marshal_windows.h|
|Sistem::String^|std::dize|marshal_as|marshal_cppstd.h|
|std::dize|Sistem::String^|marshal_as|marshal_cppstd.h|
|Sistem::String^|std::wstring|marshal_as|marshal_cppstd.h|
|std::wstring|Sistem::String^|marshal_as|marshal_cppstd.h|
|Sistem::String^|CStringT\<char>|marshal_as|marshal_atl.h|
|CStringT\<char>|Sistem::String^|marshal_as|marshal_atl.h|
|Sistem::String^|CStringT<wchar_t>|marshal_as|marshal_atl.h|
|CStringT<wchar_t>|Sistem::String^|marshal_as|marshal_atl.h|
|Sistem::String^|Ccombstr|marshal_as|marshal_atl.h|
|Ccombstr|Sistem::String^|marshal_as|marshal_atl.h|

Mareşallik, yalnızca yönetilen yerel veri türlerinden yerel veri türlerine ve dönüştürdüğünüz yerel türde otomatik temizleme için bir yıkıcı olmadığında bir bağlam gerektirir. Mareşal bağlamı, ayrılan yerel veri türünü yok eder. Bu nedenle, bağlam gerektiren dönüşümler yalnızca bağlam silinene kadar geçerli olacaktır. Marshaled değerlerini kaydetmek için değerleri kendi değişkenlerinize kopyalamanız gerekir.

> [!NOTE]
> Dizenize `NULL`s katıştırtıysanız, dizeyi mareşallemenin sonucu garanti edilmez. Katıştılı `NULL`s dize kesilmiş veya korunmuş olabilir neden olabilir.

Bu örnek, msclr dizininin bir üstbilgi bildirimine nasıl dahil edilebildiğini gösterir:

`#include "msclr\marshal_cppstd.h"`

Mareşallik kitaplığı genişletilebilir, böylece kendi mareşallik türlerinizi ekleyebilirsiniz. Mareşal kitaplığını genişletme hakkında daha fazla bilgi için [bkz.](../dotnet/how-to-extend-the-marshaling-library.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Support Library](../dotnet/cpp-support-library.md)<br/>
[Nasıl yapılır: Sıralama Kitaplığını Genişletme](../dotnet/how-to-extend-the-marshaling-library.md)
