---
title: "Hangi dışarı aktarma yöntemini kullanacağınızı belirleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7375d4baf31c1564493fd29938ef2ac8ee034f3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="determining-which-exporting-method-to-use"></a>Hangi Dışarı Aktarma Metodunu Kullanacağınızı Belirleme
İki yoldan biriyle işlevlerde verebilirsiniz — .def dosyası veya `__declspec(dllexport)` anahtar sözcüğü. Hangi DLL için daha iyi bir yoludur karar vermenize yardımcı olması için aşağıdaki soruları göz önünde bulundurun:  
  
-   Daha fazla işlevlerini dışarı daha sonra yapmayı planlıyor musunuz?  
  
-   Yeniden oluşturabilirsiniz veya yeniden oluşturulamıyor uygulamalar tarafından kullanılan uygulamalar tarafından kullanılan, DLL — Örneğin, üçüncü taraflar tarafından oluşturulan uygulamaları?  
  
## <a name="pros-and-cons-of-using-def-files"></a>Artıları ve eksileri .def dosyaları kullanma  
 İşlevleri dışarı aktarma sıra numaraları üzerinde denetim .def dosyası sağlar, dışarı aktarma. DLL için dışarı aktarılan bir işlevin eklediğinizde, verilen herhangi bir işlev'den daha yüksek bir sıra değeri atayabilirsiniz. Bunu yaptığınızda, yeni işlevi içeren içeri aktarma kitaplığını yeniden bağlamak örtük bağlantılandırma kullanan uygulamaları yok. Birçok uygulama tarafından kullanılacak bir DLL tanımlıyorsanız yeni işlevsellik eklemesine ve ayrıca zaten buna bağlı uygulamaların düzgün çalışması devam ettiğinden emin olun çünkü çok kullanışlı bir yoldur. Örneğin, MFC DLL'leri .def dosyaları kullanılarak oluşturulur.  
  
 .Def dosyası kullanmanın başka bir avantajı, kullanabilmenizdir `NONAME` bir işlev dışarı aktarmak için öznitelik. DLL dışarı aktarmaları tabloda yalnızca sıra koyar. Dışarı aktarılan işlevler, fazla sayıda kullanarak DLL'leri `NONAME` özniteliği DLL dosyasının boyutunu azaltın. Bir modül tanımlama deyimi yazma hakkında daha fazla bilgi için bkz: [modül tanımlama deyimleri kuralları](../build/reference/rules-for-module-definition-statements.md). Sıralı dışarı aktarma hakkında daha fazla bilgi için bkz: [dışarı aktarma işlevleri DLL'den göre sıralı yerine ada göre](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 .Def dosyası kullanarak bir dezavantajı işlevlerinizi C++ dosyasına dışa aktarıyorsanız, ya da sahip .def düzenlenmiş adlar yerleştirilecek dosya veya dışarı aktarılan işlevler yapmıştır ad düzenlemesi önlemek için extern "C" kullanarak tanımlayın olması için Visual C++ derleyicisi tarafından.  
  
 Düzenlenmiş adlar .def dosyasına yerleştirirseniz, bunları kullanarak elde edebilirsiniz [DUMPBIN](../build/reference/dumpbin-reference.md) bağlayıcı kullanarak veya aracı [/MAP](../build/reference/map-generate-mapfile.md) seçeneği. Derleyici tarafından üretilen düzenlenmiş adlar derleyici özgü; .def dosyasına derleyici tarafından üretilen düzenlenmiş adlar yerleştirirseniz, bu nedenle, DLL bağlantı veren uygulamalar da çağıran uygulamadaki düzenlenmiş adlar dışa aktarılan eşleşmesi derleyici aynı sürümünü kullanarak oluşturulmalıdır i adları n dll .def dosyası.  
  
## <a name="pros-and-cons-of-using-declspecdllexport"></a>Artıları ve eksileri __declspec(dllexport) kullanma  
 Kullanarak `__declspec(dllexport)` .def dosyası Bakımı ve dışarı aktarılan işlevlerin düzenlenmiş adlar alma hakkında endişelenmeye gerek olmadığı için uygundur. Ancak, bu şekilde, verme yararlılığı yeniden oluşturmak hazır olduğunuz bağlantılı uygulamalar sayısına göre sınırlıdır. DLL dışarı aktarmaları yeni ile yeniden oluşturursanız, ayrıca yeniden oluşturmak için derleyici farklı bir sürümünü kullanıyorsanız, dışarı aktarılan C++ işlevlerini düzenlenmiş adları değişebileceğinden uygulamaları yeniden gerekir.  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)