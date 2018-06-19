---
title: Normal MFC DLL'nin Modül durumları dinamik olarak MFC'ye bağlı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15f533473ebe90d6d105ddeb57dcdcddd90e87b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369376"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>Normal MFC DLL'nin Modül durumları dinamik olarak MFC'ye bağlı
MFC DLL normal MFC DLL dinamik olarak bağlama yeteneği oldukça karmaşık bazı yapılandırmalara izin verir. Örneğin, normal bir MFC DLL ve kullandığı yürütülebilir hem de dinamik olarak MFC DLL ve tüm MFC uzantı DLL'leri bağlayabilirsiniz.  
  
 Bu yapılandırma geçerli işaretçi gibi MFC genel verileriyle ilgili bir sorun oluşturur `CWinApp` nesnesine ve tanıtıcı eşlemeleri.  
  
 MFC sürüm 4.0 önce bu genel veriler MFC DLL kendisini belgeler ve modülleri tarafından işleminde paylaşılan. Win32 DLL kullanan her işlem DLL verilerinin kopyasını aldığından, bu düzen işlem içi veri izlemek için kolay bir yol sağlanır. Ayrıca, AFXDLL modeli olacağını yalnızca biri kabul ettiği için `CWinApp` nesne ve yalnızca bir dizi tanıtıcı eşlemeleri işleminde, bu öğeler MFC DLL kendisini izlenebilir.  
  
 Ancak normal bir MFC DLL MFC DLL'ye dinamik olarak bağlama özelliği sayesinde, artık iki veya daha fazla olması mümkündür `CWinApp` nesneleri bir işlemde — ve ayrıca iki veya daha fazla tanıtıcı eşlemeleri kümesi. Nasıl MFC kullanması gerektiğini hangilerinin izlemek?  
  
 Çözüm, her modül (uygulama veya Normal MFC DLL) bu genel durum bilgilerini kopyasını vermektir. Bu nedenle, yapılan bir çağrı **AfxGetApp** normal bir işaretçi MFC DLL döndürür `CWinApp` DLL olmayan yürütülebilir bir nesne. MFC genel verilerinin bu modül başına kopyası Modül durumu olarak bilinir ve açıklanan [MFC Teknik Not 58](../mfc/tn058-mfc-module-state-implementation.md).  
  
 Normal MFC DLL içinde uygulanan tüm ileti işleyiciler hakkında endişelenmeniz gerekmez şekilde MFC genel pencere yordamı otomatik olarak doğru modül durumuna geçer. Ancak, yürütülebilir Normal MFC DLL içine çağırdığında açıkça bir DLL için geçerli modül durumunu ayarlamak gerekir. Bunu yapmak için kullanın **AFX_MANAGE_STATE** makrosu her işlevde DLL'den dışarı. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek yapılır:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC uzantısı DLL’leri](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)