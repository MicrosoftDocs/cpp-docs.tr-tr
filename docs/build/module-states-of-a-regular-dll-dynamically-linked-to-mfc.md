---
title: Normal MFC DLL'SİNİN modül durumları dinamik olarak MFC'ye bağlı | Microsoft Docs
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
ms.openlocfilehash: d458c445930896fb04cb339c7191f649be542faf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717034"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>MFC'ye dinamik olarak bağlı normal MFC DLL'SİNİN modül durumları

Oldukça karmaşık bazı yapılandırmalar dinamik olarak Normal MFC DLL, MFC DLL için bağlama yeteneği sağlar. Örneğin, Normal MFC DLL'SİNİN ve onu kullanan yürütülebilir dosya hem de dinamik olarak MFC DLL ve herhangi bir MFC uzantısı DLL'leri bağlayabilirsiniz.

Bu yapılandırma geçerli bir işaretçi gibi MFC genel verileriyle ilgili bir sorun paylaşılmamasını `CWinApp` nesne ve tanıtıcı eşlemeleri.

MFC sürüm 4.0 önce bu genel veri MFC DLL kendisini belgeler ve modülleri tarafından işlemde paylaşıldı. Bir Win32 DLL kullanan her işlem kendi DLL'nin verilerin kopyasını aldığından, bu düzen, işlem içi verileri izlemek için kolay bir yol sağlanır. Ayrıca, AFXDLL model olacağını yalnızca bir varsayılan olduğundan `CWinApp` nesne ve yalnızca bir dizi tanıtıcı eşlemeleri işleminde, bu öğeler, MFC DLL kendisini izlenebilir.

Ancak Normal MFC DLL'SİNİN MFC DLL için dinamik bağlama özelliği sayesinde, artık iki veya daha fazla olması mümkündür `CWinApp` nesneleri bir işlemde — ve ayrıca iki veya daha fazla tanıtıcı eşlemeleri kümesi. Nasıl MFC kullanması gerektiğini, hangilerinin izler mi?

Çözüm, bu genel durum bilgilerini kendine ait kopyasını her Modülü (uygulama veya Normal MFC DLL'SİNİN) vermektir. Bu nedenle, bir çağrı **AfxGetApp** içinde Normal MFC DLL için bir işaretçi döndürür. `CWinApp` DLL'deki, bir yürütülebilir dosya değil. Bu modül başına kopya MFC genel veri Modül durumu olarak bilinir ve açıklanan [MFC Teknik Notu 58](../mfc/tn058-mfc-module-state-implementation.md).

Normal MFC DLL içinde uygulanan herhangi bir ileti işleyicileri endişelenmenize gerek kalmayacak şekilde MFC ortak pencere yordamını otomatik olarak doğru modülü durumuna geçer. Ancak, yürütülebilir dosyanın Normal MFC DLL'yi çağırdığında, açıkça geçerli modül durumunu bir DLL için ayarlamanız gerekir. Bunu yapmak için **AFX_MANAGE_STATE** her işlevde makrosu DLL'den dışarı. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek gerçekleştirilir:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)