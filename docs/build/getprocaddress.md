---
title: GetProcAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- GetProcAddress
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cec73a7d7aa212c6f53bc2654db6fe40ff96472a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367972"
---
# <a name="getprocaddress"></a>GetProcAddress
DLL çağrı açıkça bağlama işlemleri [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL dışarı aktarılan bir işlevin adresini elde edin. Döndürülen işlev işaretçisi DLL işlevi çağırmak için kullanın. **GetProcAddress** DLL modül tanıtıcısını parametre alır (tarafından döndürülen **LoadLibrary**, `AfxLoadLibrary`, veya **GetModuleHandle**) ve her iki istediğiniz işlevin adını alır Arama veya işlevin dışarı aktarma sıra.  
  
 İşaretçi üzerinden DLL işlevi çağırma ve hiçbir derleme zamanı tür denetlemesi olduğundan, böylece etmez yığında ayrılan bellek overstep ve bir erişim ihlali neden işlev parametrelerinin doğru olduğundan emin olun. Tür güvenliği sağlamak için bir dışarı aktarılan işlevleri işlev prototipleri arayın ve işlev işaretçileri için eşleşen tür tanımları oluşturmak için yoludur. Örneğin:  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 Çağrılırken istediğiniz işlevi belirttiğiniz nasıl **GetProcAddress** nasıl DLL oluşturulduğuna bağlı.  
  
 Sıralı dışarı aktarma için bağlama DLL modül tanımlama (.def) dosyası ile oluşturulduysa ve sıra numaraları işlevleriyle listede yoksa yalnızca edinebilirsiniz **dışarı** DLL .def dosyası bölümü. Çağırma **GetProcAddress** verme ile işlev adı aksine sıra DLL birçok dışarı aktarılan işlevler varsa DLL'nin dizin tablo olarak dışarı aktarma sıra numaraları gördükleri için biraz daha hızlıdır. Bir verme sıra ile **GetProcAddress** DLL dışarı aktarma tablosundaki işlev adları için belirtilen ad karşılaştırma aksine doğrudan işlevi bulabilirsiniz. Ancak, çağırmalıdır **GetProcAddress** yalnızca .def dosyası dışarı aktarılan işlevler sıra numaraları atama üzerinde denetim varsa dışarı aktarma sıra ile.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Bir DLL'e örtük olarak bağlanma](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [LoadLibrary ve AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)