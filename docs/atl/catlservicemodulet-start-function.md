---
title: CAtlServiceModuleT::Start işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b1edd5d01300324a8d24b41aa289f510cf078ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021780"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Start işlevi

Hizmet çalıştırıldığında `_tWinMain` çağrıları `CAtlServiceModuleT::WinMain`, sırayla çağıran `CAtlServiceModuleT::Start`.

`CAtlServiceModuleT::Start` bir dizi ayarlar `SERVICE_TABLE_ENTRY` her hizmetin kendi başlangıç işleve eşlemenizi yapılar. Bu dizi ardından Win32 API işlevine geçirilen [StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera). Teorik olarak, bir EXE birden çok hizmet işlemlerini gerçekleştirebilir ve birden çok dizisine sahip `SERVICE_TABLE_ENTRY` yapıları. Şu anda, ancak bir ATL oluşturulan hizmet EXE başına yalnızca bir hizmet destekler. Bu nedenle, hizmet adını içeren tek bir giriş dizi sahip ve `_ServiceMain` olarak başlangıç işlevi. `_ServiceMain` bir statik üye işlevi olduğu `CAtlServiceModuleT` statik olmayan üye işlev çağrılarının `ServiceMain`.

> [!NOTE]
>  Hata `StartServiceCtrlDispatcher` bağlanmak için Hizmet Denetimi Yöneticisi (SCM) büyük olasılıkla program hizmet olarak çalışmıyor anlamına gelir. Bu durumda, program çağırır `CAtlServiceModuleT::Run` doğrudan programın yerel sunucu olarak çalıştırabilirsiniz. Programı yerel sunucu olarak çalıştırma hakkında daha fazla bilgi için bkz. [hata ayıklama ipuçları](../atl/debugging-tips.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

