---
title: "C++'da hazırlamaya genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9d910c7d6346d23f094e9359f0e5fe3536ee09dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-marshaling-in-c"></a>C++'da Hazırlamaya Genel Bakış
Karma modda bazen yerel ve yönetilen türler arasında verilerinizi sıralamanız gerekir. [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)]yardımcı olmak için hazırlama kitaplığını sunulan sıralama ve basit bir şekilde veri dönüştürün.  
  
 Hazırlama kitaplığını ile veya olmadan kullanabilirsiniz bir [marshal_context sınıfı](../dotnet/marshal-context-class.md). Bazı dönüşümleri bir bağlam gerektirir. Diğer dönüştürme kullanarak uygulanabilir [marshal_as](../dotnet/marshal-as.md) işlevi. Aşağıdaki tabloda desteklenen geçerli dönüşümleri, bir bağlam ihtiyaç olup olmadığını ve hangi sıralama dosya eklemek zorunda:  
  
|Türünden|Türü için|Sıralama yöntemi|Dosya Ekle|  
|---------------|-------------|--------------------|------------------|  
|System::String ^|const char *|marshal_context|Marshal.h|  
|const char *|System::String ^|marshal_as|Marshal.h|  
|char *|System::String ^|marshal_as|Marshal.h|  
|System::String ^|const wchar_t *|marshal_context|Marshal.h|  
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
  
 Hazırlama kitaplığı üstbilgilerini msclr alt INCLUDE dizininde bulunur. Bu örnek bir dahil etme üstbilgi bildiriminde içeren msclr dizin gösterilmektedir:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Hazırlama kitaplığını genişletilebilir, böylelikle hazırlama türlerinizi ekleyebilirsiniz. Hazırlama kitaplığını genişletme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hazırlama kitaplığını genişletme](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 Önceki sürümlerde, verileri kullanarak sıralama [Platform Çağırma](/dotnet/framework/interop/consuming-unmanaged-dll-functions). Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../dotnet/calling-native-functions-from-managed-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ destek kitaplığı](../dotnet/cpp-support-library.md)   
 [Nasıl yapılır: Hazırlama Kitaplığını Genişletme](../dotnet/how-to-extend-the-marshaling-library.md)