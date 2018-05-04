---
title: İçeri ve dışarı aktarma satır içi işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b666d450766a5a285f02517d92d5eb4dc3f29c68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="importing-and-exporting-inline-functions"></a>Satır İçi İşlevleri İçeri ve Dışarı Aktarma
İçeri aktarılan işlevler satır içi olarak tanımlanabilir. Etkisi kabaca standart işlev satır içi tanımlama aynıdır; işlev çağrıları makro gibi satır içi koda genişletilir. C++ destekleyen bir şekilde DLL'de bazı üye işlevleri için verimliliğini sınıflarını gibi temelde faydalı olur.  
  
 Bir içe aktarılan satır içi işlev c++'ta adresini sürebilir özelliğidir. Derleyici DLL'de bulunan satır içi işlev kopyasını adresini döndürür. Başka bir içeri aktarılan satır içi işlevleri içeri aktarılan işlevinin genel içeri aktarılan verileri farklı olarak statik yerel veri başlatabilir özelliğidir.  
  
> [!CAUTION]
>  Sürüm çakışması olasılığı oluşturduğundan sağlama satır içi işlevleri içeri aktarırken dikkatli olmanız gerekir. Satır içi işlev uygulama koda genişletilmiş; işlevi yeniden yazma, uygulamanın kendisinin derlenmiştir sürece bu nedenle, onu güncelleştirilmez. (Normalde, DLL işlevleri bunları kullanan uygulamaları derlenmeden güncelleştirilebilir.)  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)  
  
-   [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)