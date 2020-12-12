---
description: "Daha fazla bilgi edinin: C++/CLı ' da sıralamaya genel bakış"
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
ms.openlocfilehash: 35294a204d338087a609746e6ae2e5e07ea07b59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255541"
---
# <a name="overview-of-marshaling-in-ccli"></a>C++/CLı ' da sıralamaya genel bakış

Karma modda bazen verilerinizi yerel ve yönetilen türler arasında sıramalısınız. *Sıralama kitaplığı* , verileri basit bir şekilde sıralemenize ve dönüştürmenize yardımcı olur.  Sıralama kitaplığı bir işlevler kümesinden ve `marshal_context` ortak türler için sıralama gerçekleştiren bir sınıftan oluşur. Kitaplığı, Visual Studio sürümünüz için **Include/msclr** dizininde bulunan bu üst bilgilerde tanımlanmıştır:

|Üst bilgi|Açıklama|
|---------------|-----------------|
|Marshal. h|`marshal_context` sınıf ve bağlam içermeyen sıralama işlevleri|
|marshal_atl. h| ATL türlerini hazırlama işlevleri|
|marshal_cppstd. h|Standart C++ türlerini hazırlama işlevleri|
|marshal_windows. h|Windows türlerini hazırlama işlevleri|

**Msclr** klasörü için varsayılan yol, sahip olduğunuz sürüme ve yapı numarasına bağlı olarak buna benzer bir şeydir:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Sıralama kitaplığını bir [Marshal_context sınıfı](../dotnet/marshal-context-class.md)ile veya olmadan kullanabilirsiniz. Bazı dönüşümler bağlam gerektirir. Diğer dönüşümler [marshal_as](../dotnet/marshal-as.md) işlevi kullanılarak uygulanabilir. Aşağıdaki tabloda, desteklenen geçerli dönüşümler ve bağlam gerekip gerekmediğini ve dahil etmek istediğiniz sıralama dosyasını listelenmektedir:

|Türden|Yazmak için|Marshal yöntemi|İçerme dosyası|
|---------------|-------------|--------------------|------------------|
|System:: String ^|const char \*|marshal_context|Marshal. h|
|const char \*|System:: String ^|marshal_as|Marshal. h|
|Char \*|System:: String ^|marshal_as|Marshal. h|
|System:: String ^|const wchar_t\*|marshal_context|Marshal. h|
|const wchar_t \*|System:: String ^|marshal_as|Marshal. h|
|wchar_t \*|System:: String ^|marshal_as|Marshal. h|
|System:: IntPtr|TUTAMAÇLARDAN|marshal_as|marshal_windows. h|
|TUTAMAÇLARDAN|System:: IntPtr|marshal_as|marshal_windows. h|
|System:: String ^|BSTR|marshal_context|marshal_windows. h|
|BSTR|System:: String ^|marshal_as|Marshal. h|
|System:: String ^|bstr_t|marshal_as|marshal_windows. h|
|bstr_t|System:: String ^|marshal_as|marshal_windows. h|
|System:: String ^|std:: String|marshal_as|marshal_cppstd. h|
|std:: String|System:: String ^|marshal_as|marshal_cppstd. h|
|System:: String ^|std:: wstring|marshal_as|marshal_cppstd. h|
|std:: wstring|System:: String ^|marshal_as|marshal_cppstd. h|
|System:: String ^|CStringT\<char>|marshal_as|marshal_atl. h|
|CStringT\<char>|System:: String ^|marshal_as|marshal_atl. h|
|System:: String ^|CStringT<wchar_t>|marshal_as|marshal_atl. h|
|CStringT<wchar_t>|System:: String ^|marshal_as|marshal_atl. h|
|System:: String ^|CComBSTR|marshal_as|marshal_atl. h|
|CComBSTR|System:: String ^|marshal_as|marshal_atl. h|

Sıralama, yalnızca yönetilene yerel veri türlerine göre sıralama yaptığınızda ve dönüştürmekte olduğunuz yerel türün otomatik temizleme için yok edici olmadığından bağlam gerektirir. Sıralama bağlamı, yıkıcısında ayrılan yerel veri türünü yok eder. Bu nedenle, bağlam gerektiren dönüştürmeler yalnızca bağlam silinene kadar geçerli olur. Sıralanmış değerleri kaydetmek için, değerleri kendi değişkenlerinizle kopyalamanız gerekir.

> [!NOTE]
> `NULL`Dizeniz için katıştırılmış bir dize varsa, dizeyi hazırlama sonucu garanti edilmez. Katıştırılmış `NULL` s, dizenin kesilebilir olmasına neden olabilir veya korunmuş olabilir.

Bu örnek, bir ekleme üst bilgisi bildiriminde msclr dizininin nasıl ekleneceğini gösterir:

`#include "msclr\marshal_cppstd.h"`

Hazırlama Kitaplığı, kendi sıralama türlerinizi ekleyebilmeniz için genişletilebilir. Sıralama kitaplığını genişletme hakkında daha fazla bilgi için bkz. [nasıl yapılır: sıralama kitaplığını genişletme](../dotnet/how-to-extend-the-marshaling-library.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ destek kitaplığı](../dotnet/cpp-support-library.md)<br/>
[Nasıl yapılır: sıralama kitaplığını genişletme](../dotnet/how-to-extend-the-marshaling-library.md)
