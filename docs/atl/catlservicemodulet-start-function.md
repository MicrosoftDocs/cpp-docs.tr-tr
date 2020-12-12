---
description: 'Daha fazla bilgi edinin: CAtlServiceModuleT:: Start Işlevi'
title: 'CAtlServiceModuleT:: Start Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: cfdae47f88c7957a4470da3129f3d3e071614276
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148323"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT:: Start Işlevi

Hizmet çalıştırıldığında çağrılır `_tWinMain` `CAtlServiceModuleT::WinMain` , çağırır `CAtlServiceModuleT::Start` .

`CAtlServiceModuleT::Start``SERVICE_TABLE_ENTRY`her hizmeti başlangıç işlevine eşleyen yapıların dizisini ayarlar. Daha sonra bu dizi Win32 API işlevine geçirilir, [StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw). Teorik olarak, bir EXE birden çok hizmeti işleyebilir ve dizi birden fazla yapıya sahip olabilir `SERVICE_TABLE_ENTRY` . Ancak şu anda, ATL tarafından oluşturulan bir hizmet EXE başına yalnızca bir hizmet destekler. Bu nedenle, dizinin, hizmet adını ve başlangıç işlevini içeren tek bir girişi vardır `_ServiceMain` . `_ServiceMain``CAtlServiceModuleT`, statik olmayan üye işlevi çağıran öğesinin statik bir üye işlevidir `ServiceMain` .

> [!NOTE]
> `StartServiceCtrlDispatcher`Service Control Manager 'a (SCM) Bağlanamamak, programın hizmet olarak çalışmadığı anlamına gelir. Bu durumda program doğrudan çağırır, `CAtlServiceModuleT::Run` böylece program yerel sunucu olarak çalıştırılabilir. Programı yerel sunucu olarak çalıştırma hakkında daha fazla bilgi için bkz. [hata ayıklama ipuçları](../atl/debugging-tips.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)
