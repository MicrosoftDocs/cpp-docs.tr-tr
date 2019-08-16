---
title: 'CAtlServiceModuleT:: Start Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: e6de15f40e89bfffba504db04ee7a16b2a68cac9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491660"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT:: Start Işlevi

Hizmet çalıştırıldığında `_tWinMain` `CAtlServiceModuleT::WinMain`çağrılır ,çağırır.`CAtlServiceModuleT::Start`

`CAtlServiceModuleT::Start`her hizmeti başlangıç işlevine eşleyen `SERVICE_TABLE_ENTRY` yapıların dizisini ayarlar. Daha sonra bu dizi Win32 API işlevine geçirilir, [StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw). Teorik olarak, bir exe birden çok hizmeti işleyebilir ve dizi birden fazla `SERVICE_TABLE_ENTRY` yapıya sahip olabilir. Ancak şu anda, ATL tarafından oluşturulan bir hizmet EXE başına yalnızca bir hizmet destekler. Bu nedenle, dizinin, hizmet adını ve `_ServiceMain` başlangıç işlevini içeren tek bir girişi vardır. `_ServiceMain``CAtlServiceModuleT` ,`ServiceMain`statik olmayan üye işlevi çağıran öğesinin statik bir üye işlevidir.

> [!NOTE]
>  `StartServiceCtrlDispatcher` Service Control Manager 'a (SCM) Bağlanamamak, programın hizmet olarak çalışmadığı anlamına gelir. Bu durumda program doğrudan çağırır `CAtlServiceModuleT::Run` , böylece program yerel sunucu olarak çalıştırılabilir. Programı yerel sunucu olarak çalıştırma hakkında daha fazla bilgi için bkz. [hata ayıklama ipuçları](../atl/debugging-tips.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)
