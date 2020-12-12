---
description: 'Daha fazla bilgi edinin: MFC ortak denetimler kitaplığı yalıtımı'
title: MFC Ortak Denetimler Kitaplığını Yalıtma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: f3e0f6ad981a690f6212455b8af891eaa97f2642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335826"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC Ortak Denetimler Kitaplığını Yalıtma

Ortak denetimler kitaplığı artık MFC içinde yalıtılarak, farklı modüllerin (örneğin, Kullanıcı dll 'Leri) bildirimlerinde sürümü belirterek ortak denetimler kitaplığının farklı sürümlerini kullanmasına izin verir.

MFC uygulaması (veya MFC tarafından çağrılan kullanıcı kodu), işlev gören sarmalayıcı işlevleri aracılığıyla ortak denetim kitaplığı API 'Lerine çağrı yapar `Afx` , burada *fonksiyonadı* ortak denetimler API 'sinin adıdır. Bu sarmalayıcı işlevleri afxcomctl32. h ve afxcomctl32. inl içinde tanımlanmıştır.

Ortak denetimler kitaplığının [GetProcAddress](../build/getprocaddress.md)çağırmak yerine belirli bir API 'yi uygulayıp uygulamadığını anlamak için [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) ve [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) makrolarını (afxcomctl32. h içinde tanımlanmıştır) kullanabilirsiniz.

Teknik olarak, bir sarmalayıcı sınıf `CComCtlWrapper` (afxcomctl32. h içinde tanımlanmıştır) aracılığıyla ortak denetim kitaplığı API 'lerine çağrılar yaparsınız. `CComCtlWrapper` comctl32.dll yükleme ve kaldırma işleminden da sorumludur. MFC modül durumu, örneğine bir işaretçi içerir `CComCtlWrapper` . Makrosunu kullanarak sarmalayıcı sınıfına erişebilirsiniz `afxComCtlWrapper` .

MFC uygulaması veya Kullanıcı DLL 'si, bildiriminde istenen ortak denetim kitaplığına bağlandığı için, bir MFC uygulamasından veya Kullanıcı DLL 'sinden ortak denetimler API 'sinin doğrudan çağrılmasının (MFC sarmalayıcı işlevlerini kullanmıyor) çoğu durumda çalıştığını unutmayın. Ancak, MFC kodunun kendisi farklı ortak denetim kitaplığı sürümleriyle Kullanıcı dll 'lerden çağrılabilir olduğundan, bu işlem sarmalayıcıları kullanması gerekir.
