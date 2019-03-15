---
title: MFC'ye dinamik olarak bağlı normal MFC DLL'SİNİN modül durumları
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
ms.openlocfilehash: 3ab51ca8097bd5ec27e8e7cfd8b8f19d76195664
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822151"
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

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)
