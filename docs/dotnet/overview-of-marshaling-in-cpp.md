---
title: C++'da hazırlamaya genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76f6721ce4561e9c2b4323fef9c2eed3231f73cb
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079166"
---
# <a name="overview-of-marshaling-in-c"></a>C++'da Hazırlamaya Genel Bakış
Karma modda bazen yerel ve yönetilen türler arasında verilerinizi sıralamanız gerekir. Visual Studio 2008 sunulan *hazırlama kitaplığını* yardımcı olması için sıralama ve basit bir şekilde veri dönüştürün.  Hazırlama kitaplığını işlevleri kümesinden oluşur ve bir `marshal_context` gerçekleştirmek için genel türleri hazırlama sınıfı. Bu üstbilgilerin kitaplığa tanımlanan **dahil msclr** dizini, Visual Studio sürümü için:

|Üstbilgi|Açıklama|  
|---------------|-----------------|
|Marshal.h|`marshal_context` sınıf ve bağlam serbest hazırlama işlevleri|
|marshal_atl.h| ATL türlerini hazırlama işlevleri|
|marshal_cppstd.h|Standart C++ türlerini hazırlama işlevleri|
|marshal_windows.h|Windows türlerini hazırlama işlevleri|


İçin varsayılan yolu **msclr** klasördür şuna bağlı olarak hangi sürümünün yüklü ve yapı numarası:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

 Hazırlama kitaplığını ile veya olmadan kullanabilirsiniz bir [marshal_context sınıfı](../dotnet/marshal-context-class.md). Bazı dönüşümleri bir bağlam gerektirir. Diğer dönüştürme kullanarak uygulanabilir [marshal_as](../dotnet/marshal-as.md) işlevi. Aşağıdaki tabloda desteklenen geçerli dönüşümleri, bir bağlam ihtiyaç olup olmadığını ve hangi sıralama dosya eklemek zorunda:  
  
|Türünden|Türü için|Sıralama yöntemi|Dosya Ekle|  
|---------------|-------------|--------------------|------------------|  
|System::String ^|const char *|marshal_context|Marshal.h|  
|const char *|System::String ^|marshal_as|Marshal.h|  
|char *|System::String ^|marshal_as|Marshal.h|  
|System::String ^|const wchar_t*|marshal_context|Marshal.h|  
|const wchar_t *|System::String ^|marshal_as|Marshal.h|  
|wchar_t *|System::String ^|marshal_as|Marshal.h|  
|System::IntPtr|İŞLEME|marshal_as|marshal_windows.h|  
|İŞLEME|System::IntPtr|marshal_as|marshal_windows.h|  
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
|System::String ^|CStringT < wchar_t >|marshal_as|marshal_atl.h|  
|CStringT < wchar_t >|System::String ^|marshal_as|marshal_atl.h|  
|System::String ^|CComBSTR|marshal_as|marshal_atl.h|  
|CComBSTR|System::String ^|marshal_as|marshal_atl.h|  
  
 Sıralama bir bağlam yalnızca türleri yönetilen yerel verileri sıralama ve dönüştürüyorsanız yerel tür yıkıcı otomatik yok temizlenmesini gerektirir. Hazırlama bağlamı kendi yıkıcı ayrılmış yerel veri türü yok eder. Bu nedenle, yalnızca bağlam silinene kadar bir bağlam gerektiren dönüşümleri geçerli olacaktır. Herhangi bir sıralanmış değeri kaydetmek için kendi değişkenlere değerler kopyalamanız gerekir.  
  
> [!NOTE]
>  Katıştırılmış sahip değilse `NULL`dizenizi s, dize sıralama sonucu garanti edilmez. Katıştırılmış `NULL`s kesilecek dize neden olabilir ya da korunması.  
  
Bu örnek bir dahil etme üstbilgi bildiriminde içeren msclr dizin gösterilmektedir:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Hazırlama kitaplığını genişletilebilir, böylelikle hazırlama türlerinizi ekleyebilirsiniz. Hazırlama kitaplığını genişletme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hazırlama kitaplığını genişletme](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 Önceki sürümlerde, verileri kullanarak sıralama [Platform Çağırma](/dotnet/framework/interop/consuming-unmanaged-dll-functions). Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ destek kitaplığı](../dotnet/cpp-support-library.md)   
 [Nasıl yapılır: Hazırlama Kitaplığını Genişletme](../dotnet/how-to-extend-the-marshaling-library.md)
