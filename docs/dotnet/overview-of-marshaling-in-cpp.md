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
ms.openlocfilehash: 937fbdf4b3ed09344e69a8f1eb731565c36794ae
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861169"
---
# <a name="overview-of-marshaling-in-ccli"></a>İçinde hazırlama genel bakış C++/CLI

Karma modda bazen verilerinizi yerel ve yönetilen türleri sıralamanız gerekir. *Sıralama kitaplığı* hazırlamak ve basit bir şekilde veri dönüştürme yardımcı olur.  Sıralama Kitaplığı işlevler bir dizi oluşur ve `marshal_context` hazırlama gerçekleştirmek için genel türleri sınıf. Kitaplık bu üstbilgisinde tanımlanır **dahil msclr** dizin, Visual Studio sürümü için:

|Üstbilgi|Açıklama|
|---------------|-----------------|
|Marshal.h|`marshal_context` sınıf ve bağlam ücretsiz sıralama işlevleri|
|marshal_atl.h| ATL türlerini hazırlama için işlevleri|
|marshal_cppstd.h|İşlevler için standart C++ türlerini hazırlama|
|marshal_windows.h|İşlevleri için Windows türlerini hazırlama|

Varsayılan yolu **msclr** klasördür aşağıdakine benzer hangi sürümüne bağlı olarak, sahip ve yapı numarası:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Sıralama kitaplığı ile veya olmadan kullanabilirsiniz bir [; marshal_context Class](../dotnet/marshal-context-class.md). Bazı dönüştürmeler bir bağlamda gerektirir. Diğer dönüştürme kullanılarak uygulanabilir [marshal_as](../dotnet/marshal-as.md) işlevi. Aşağıdaki tabloda desteklenen geçerli dönüştürmeler, bir bağlam gerektirdikleri ve hangi sıralama dosya eklemek zorunda:

|Türünden|Yazmak için|Sıralama yöntemi|Dosya Ekle|
|---------------|-------------|--------------------|------------------|
|System::String ^|const char \*|marshal_context|Marshal.h|
|const char \*|System::String ^|marshal_as|Marshal.h|
|Char \*|System::String ^|marshal_as|Marshal.h|
|System::String ^|wchar_t const\*|marshal_context|Marshal.h|
|wchar_t const \*|System::String ^|marshal_as|Marshal.h|
|wchar_t \*|System::String ^|marshal_as|Marshal.h|
|System::IntPtr|TANITICI|marshal_as|marshal_windows.h|
|TANITICI|System::IntPtr|marshal_as|marshal_windows.h|
|System::String ^|BSTR|marshal_context|marshal_windows.h|
|BSTR|System::String ^|marshal_as|Marshal.h|
|System::String ^|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|System::String ^|marshal_as|marshal_windows.h|
|System::String ^|Std::String|marshal_as|marshal_cppstd.h|
|Std::String|System::String ^|marshal_as|marshal_cppstd.h|
|System::String ^|Std::wstring|marshal_as|marshal_cppstd.h|
|Std::wstring|System::String ^|marshal_as|marshal_cppstd.h|
|System::String ^|CStringT\<char >|marshal_as|marshal_atl.h|
|CStringT\<char >|System::String ^|marshal_as|marshal_atl.h|
|System::String ^|CStringT<wchar_t>|marshal_as|marshal_atl.h|
|CStringT<wchar_t>|System::String ^|marshal_as|marshal_atl.h|
|System::String ^|CComBSTR|marshal_as|marshal_atl.h|
|CComBSTR|System::String ^|marshal_as|marshal_atl.h|

Sıralama, yalnızca yönetilen yerel verileri türleri sıralamanız ve dönüştürme, yerel bir tür için otomatik bir yok edici yok temizleme bir bağlamı gerektirir. Hazırlama bağlamı yok edici ayrılmış yerel veri türünü yok eder. Bu nedenle, bir bağlam gerektiren dönüştürmeler yalnızca içeriği silinene kadar geçerli olacaktır. Sıralanmış tüm değerlerini kaydetmek için değerleri kendi değişkenlerine kopyalamanız gerekir.

> [!NOTE]
>  Katıştırılmış sahip değilse `NULL`dizenizi yeniden s'te, dize sonucu garanti edilmez. Katıştırılmış `NULL`s kesilecek dize açabilir ya da korunması.

Bu örnek, bir dahil etme üstbilgi bildiriminde msclr dizin içerecek şekilde gösterilmektedir:

`#include "msclr\marshal_cppstd.h"`

Sıralama Kitaplığı genişletilebilir, böylelikle kendi sıralama türlerini ekleyebilirsiniz. Hazırlama kitaplığını genişletme hakkında daha fazla bilgi için bkz. [nasıl yapılır: Hazırlama kitaplığını genişletme](../dotnet/how-to-extend-the-marshaling-library.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Support Library](../dotnet/cpp-support-library.md)<br/>
[Nasıl yapılır: Hazırlama Kitaplığını Genişletme](../dotnet/how-to-extend-the-marshaling-library.md)
