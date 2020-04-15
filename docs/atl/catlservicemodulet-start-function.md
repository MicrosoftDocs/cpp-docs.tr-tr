---
title: CAtlServiceModuleT::Başlat Fonksiyonu
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 50054bbb34bcc31a1d11dd8bfab797f98e4e82f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317287"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Başlat Fonksiyonu

Hizmet çalıştırıldığında, `_tWinMain` çağırır `CAtlServiceModuleT::WinMain`, sırayla `CAtlServiceModuleT::Start`çağırır .

`CAtlServiceModuleT::Start`her hizmeti başlangıç `SERVICE_TABLE_ENTRY` işleviyle eşleyen bir dizi yapı oluşturur. Bu dizi daha sonra Win32 API işlevi, [StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)geçirilir. Teoride, bir EXE birden fazla hizmeti işleyebilir ve dizi birden fazla `SERVICE_TABLE_ENTRY` yapıya sahip olabilir. Ancak şu anda, ATL tarafından oluşturulan bir hizmet EXE başına yalnızca bir hizmeti destekler. Bu nedenle, dizi hizmet adı içeren ve `_ServiceMain` başlangıç işlevi olarak tek bir giriş vardır. `_ServiceMain`statik olmayan üye `CAtlServiceModuleT` işlevi çağıran statik bir üye `ServiceMain`işlevdir.

> [!NOTE]
> Hizmet `StartServiceCtrlDispatcher` denetim yöneticisine (SCM) bağlanılamaması büyük olasılıkla programın bir hizmet olarak çalışmadığı anlamına gelir. Bu durumda, program `CAtlServiceModuleT::Run` yerel bir sunucu olarak çalıştırılabilsin diye program doğrudan çağırır. Programı yerel bir sunucu olarak çalıştırma hakkında daha fazla bilgi için Hata [Ayıklama İpuçları'na](../atl/debugging-tips.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Başlat](../atl/reference/catlservicemodulet-class.md#start)
