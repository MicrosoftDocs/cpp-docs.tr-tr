---
title: Basit bir Salt Okunur Sağlayıcı Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: 466530cb8c2ebca7f1c87370389309d3a0486e26
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707618"
---
# <a name="creating-a-simple-read-only-provider"></a>Basit bir Salt Okunur Sağlayıcı Oluşturma

::: moniker range="vs-2019"

ATL OLE DB sağlayıcısı Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil.

::: moniker-end

::: moniker range="<=vs-2017"

Ne zaman oluşturduğunuz kullanarak bir OLE DB sağlayıcısından **ATL projesi Sihirbazı** ve **ATL OLE DB sağlayıcısı Sihirbazı**, desteklemek istediğiniz diğer işlevler ekleyebilirsiniz. Ne tür veriler, tüketici ve hangi koşullar altında ileti inceleyerek sağlayıcınız tasarlamaya başlayabilir. Komutlar, işlemleri ve diğer isteğe bağlı nesneler destek gerekip gerekmediğini belirlemek özellikle önemlidir. Önden iyi bir tasarım, uygulama ve test hızlandırır.

Örneğin, iki parça halinde sunulur:

- İlk bölümü gösterir nasıl [basit bir salt okunur sağlayıcı oluşturma](../../data/oledb/implementing-the-simple-read-only-provider.md) , dizelerden oluşan bir çift okur.

- İkinci bölümü gösterir nasıl [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md) ekleyerek `IRowsetLocate` arabirimi.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
