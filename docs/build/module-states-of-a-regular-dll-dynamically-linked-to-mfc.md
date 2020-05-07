---
title: MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'nin modül durumları
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
ms.openlocfilehash: cedce676f5586369446c9856fd33e4d16c237b27
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220587"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'nin modül durumları

Normal bir MFC DLL 'yi MFC DLL 'ye dinamik olarak bağlama yeteneği, çok karmaşık olan bazı yapılandırmalara izin verir. Örneğin, normal bir MFC DLL ve bunu kullanan yürütülebilir dosya MFC DLL 'sine ve herhangi bir MFC uzantı dll 'Lerine dinamik olarak bağlanabilir.

Bu yapılandırma, geçerli `CWinApp` nesneye yönelik işaretçi ve tanıtıcı HARITALARı gibi MFC genel verileriyle ilgili bir sorun doğurur.

MFC sürüm 4,0 ' den önce, bu genel veriler MFC DLL 'sinde yer alan ve işlemdeki tüm modüller tarafından paylaşılmıştı. Win32 DLL kullanan her işlem DLL verilerinin kendi kopyasını aldığından, bu düzen işlem başına verileri izlemenin kolay bir yolunu sağladı. Ayrıca, AFXDLL modeli işlemde yalnızca bir `CWinApp` nesne ve yalnızca bir dizi tanıtıcı eşlemesi olduğunu kabul ettiğinden, bu öğeler MFC DLL 'sinde izlenebilir.

Ancak normal bir MFC DLL 'yi MFC DLL 'ye dinamik olarak bağlayabilme özelliği sayesinde, artık bir işlemde iki veya daha fazla `CWinApp` nesne ve ayrıca iki veya daha fazla tanıtıcı eşlemi kümesi olabilir. MFC hangi hangilerinin kullanılması gerektiğini nasıl izler?

Çözüm, her modülün (uygulama veya normal MFC DLL) Bu genel durum bilgilerinin kendi kopyasını vermektir. Bu nedenle, normal MFC DLL içindeki **AfxGetApp** öğesine yapılan bir çağrı, çalıştırılabilir dosyada DEĞIL `CWinApp` , dll 'deki nesnesine bir işaretçi döndürür. MFC genel verilerinin modül başına bu kopyası, modül durumu olarak bilinir ve [MFC teknik not58](../mfc/tn058-mfc-module-state-implementation.md)' te açıklanmaktadır.

MFC ortak pencere yordamı otomatik olarak doğru modül durumuna geçer, bu nedenle normal MFC DLL 'niz üzerinde uygulanan herhangi bir ileti işleyicilerinde endişelenmeniz gerekmez. Ancak, çalıştırılabiliriniz normal MFC DLL 'sine çağırdığında, geçerli modül durumunu DLL için bir tane olarak ayarlamanız gerekir. Bunu yapmak için, DLL 'den aktarılmış her işlevde **AFX_MANAGE_STATE** makrosunu kullanın. Bu, DLL 'den aktarılmış işlevlerin başlangıcına aşağıdaki kod satırı eklenerek yapılır:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı dll 'Leri](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
