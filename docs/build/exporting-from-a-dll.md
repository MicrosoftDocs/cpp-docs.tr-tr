---
title: "DLL'den dışarı aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64571a0f648c0e33635990d9ca57744877429049
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-from-a-dll"></a>DLL'den Dışarı Aktarma  
  
Önemli bir farkla bir .exe dosyası için çok benzer bir düzeni DLL dosyası olan — bir dışarı aktarma tablosu bir DLL dosyası içerir. Dışarı aktarma tablosu diğer yürütülebilir DLL dışarı aktarmaları her işlevin adını içerir. Bu işlevler DLL öğesinin içine giriş noktalarıdır; yalnızca işlevleri dışarı aktarma tablosundaki diğer yürütülebilir tarafından erişilebilir. Herhangi bir işlev DLL DLL'e özeldir. Kullanarak DLL'den dışarı aktarma tablosu görüntülenebilir [DUMPBIN](../build/reference/dumpbin-reference.md) aracı/dışarı aktarmalar seçeneği ile.  
  
 İki yöntemi kullanarak DLL'den işlevleri dışarı aktarabilirsiniz:  
  
-   Modül tanımlama (.def) dosyası oluşturun ve DLL oluştururken .def dosyası kullanın. İstiyorsanız bu yaklaşımı kullanın [işlevleri yerine sıraya göre adı, DLL'den dışarı](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
-   Anahtar sözcüğü kullanmak **__declspec(dllexport)** işlev tanımı'nda.  
  
 Her iki yöntemle işlevlerini dışarı aktarılırken kullandığınızdan emin olun [__stdcall](../cpp/stdcall.md) çağırma.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [.Def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [DLL'den sıra yerine ada göre dışarı aktarma işlevleri](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Bir uygulamaya aktarma](../build/importing-into-an-application.md)  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)