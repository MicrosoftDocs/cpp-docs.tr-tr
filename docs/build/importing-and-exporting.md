---
title: İçeri ve dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee3ffe33dbb99f1f9b4124e2695d2e56dbe5544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="importing-and-exporting"></a>İçeri ve Dışarı Aktarma
Genel simgeler uygulamada içeri aktarmak ya da iki yöntemi kullanarak DLL'den dışarı aktarma işlevleri:  
  
-   DLL oluştururken modül tanımlama (.def) dosyası kullanın  
  
-   Anahtar sözcükler kullanın **__declspec(dllimport)** veya **__declspec(dllexport)** ana uygulama işlevi tanımında  
  
## <a name="using-a-def-file"></a>.Def dosyası kullanma  
 Bir modül-tanımlama (.def) dosyası, DLL çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. Kullanmıyorsanız, **__declspec(dllimport)** veya **__declspec(dllexport)** DLL işlevlerini dışarı aktarmak için DLL .def dosyası gerektirir.  
  
 .Def dosyaları için kullanabileceğiniz [alma bir uygulamaya](../build/importing-using-def-files.md) veya [DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md).  
  
## <a name="using-declspec"></a>__Declspec kullanma  
 Visual C++ kullanır **__declspec(dllimport)** ve **__declspec(dllexport)** değiştirmek için **__declspec(dllexport)** daha önce Visual C++, 16 bit sürümlerinde kullanılan anahtar sözcük.  
  
 Kullanmanız gerekmez **__declspec(dllimport)** doğru ancak bunun yapılması derlemek kodunuzu daha iyi kodu oluşturmak derleyici sağlar. Derleyici bir işlev DLL'de veya değil, normalde bir DLL sınırı aşıldığında bir işlev çağrısında mevcut olacaktır yöneltme düzeyini atlayan kod üretmek derleyici sağlayan var olup olmadığını belirleyebildiğinden daha iyi kodu oluşturabilir. Ancak, kullanmalıdır **__declspec(dllimport)** DLL'de kullanılan değişkenleri içeri aktarmak için.  
  
 Uygun .def dosyası dışarı bölümüyle **__declspec(dllexport)** gerekli değildir. **__declspec(dllexport)** bir .exe veya .dll dosyasından .def dosyası kullanmadan dışarı aktarma işlevleri için kolay bir yol sağlamak üzere eklendi.  
  
 Win32 Taşınabilir Çalıştırılabilir biçimi, içeri aktarmalar düzeltmek için değiştirilmesi gereken sayfaların sayısını en aza indirmek için tasarlanmıştır. Bunu yapmak için her program için tüm içe aktarma adreslerini aktarım adres tablosu denen tek bir yerde yerleştirir. Bu, bu içeri aktarmalar erişirken yalnızca bir veya iki sayfa değiştirmesini sağlar.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Uygulamanın içine aktarma](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)