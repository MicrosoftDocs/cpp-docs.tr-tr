---
title: MFC Ortak Denetimler Kitaplığını Yalıtma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: fd47854c7073565fbe0c15ca6be7a9843af5f387
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583618"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC Ortak Denetimler Kitaplığını Yalıtma

Ortak Denetimler kitaplığını artık MFC, farklı modülleri (örneğin, kullanıcı DLL'ler) izin içinde için yalıtılmış olduğundan, bildirimlerinde sürüm belirterek farklı sürümleri ortak denetimler kitaplığını kullanın.

Bir MFC uygulaması (veya MFC tarafından çağrılan kullanıcı kodu) API'leri sarmalayıcı işlevleri aracılığıyla adlı ortak denetimler kitaplığını çağrılar `Afx` *FunctionName*burada *FunctionName* ortak adı API denetimlerin. Bu sarmalayıcı işlevleri afxcomctl32.h ve afxcomctl32.inl tanımlanır.

Kullanabileceğiniz [afx_comctl32_ıf_exısts](reference/run-time-object-model-services.md#afx_comctl32_if_exists) ve [afx_comctl32_ıf_exısts2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) ortak denetimler kitaplığını çağırmak yerine belirli bir API'yi uygulayan olup olmadığını belirlemek için makroları (tanımlıysa afxcomctl32.h) [GetProcAddress](../build/getprocaddress.md).

Ortak Denetimler kitaplığı API'lere giden çağrıların bir sarmalayıcı sınıfı aracılığıyla teknik olarak yaptığınız `CComCtlWrapper` (afxcomctl32.h içinde tanımlanmıştır). `CComCtlWrapper` Ayrıca yükleme ve kaldırma comctl32.dll için sorumlu değildir. MFC modül durumunda örneğine bir işaretçi içeren `CComCtlWrapper`. Sarmalayıcı sınıfı kullanarak erişebileceğiniz `afxComCtlWrapper` makrosu.

Çağırmanın Not doğrudan ortak denetimleri API (MFC sarmalayıcı işlevleri kullanarak değil), bildirimde istenen ortak denetimler kitaplığını MFC Uygulama veya kullanıcıya DLL bağlı olduğundan bir MFC'den uygulama veya kullanıcıya DLL çoğu durumda çalışır). MFC kodu farklı ortak denetimleri kitaplık sürümleri ile kullanıcı DLL'leri öğesinden çağrılması çünkü ancak, MFC kodu sarmalayıcıları kullanması gerekir.

