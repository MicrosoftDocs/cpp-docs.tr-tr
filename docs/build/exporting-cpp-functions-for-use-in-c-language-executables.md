---
title: "C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma | Microsoft Docs"
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
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0511ae4c16332b2a8e98c2319e148249b66c8461
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma  
  
C dili modülünden erişmek istediğiniz, bu işlevler C++ bağlantı yerine C bağlantısı ile bildirmelisiniz C++ ile yazılmış bir DLL işlevleri varsa. Aksi belirtilmediği sürece, C++ derleyicisi C++ tür kullanımı uyumlu (ad düzenlemesi olarak da bilinir) adlandırma ve C++ çağırma C'den çağrı zor olabilir kuralları kullanır.  
  
C bağlantı belirtmek için belirtin `extern "C"` işlev bildirimleriniz için. Örneğin:  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [.Def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
-   [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)