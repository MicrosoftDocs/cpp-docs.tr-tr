---
title: Basit bir salt okunur sağlayıcı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c8fd4e5eb25ab1e8e6b20b576a0688da7b5aa2ef
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216402"
---
# <a name="creating-a-simple-read-only-provider"></a>Basit bir Salt Okunur Sağlayıcı Oluşturma

Ne zaman oluşturduğunuz kullanarak bir OLE DB sağlayıcısından **ATL projesi Sihirbazı** ve **ATL OLE DB sağlayıcısı Sihirbazı**, desteklemek istediğiniz diğer işlevler ekleyebilirsiniz. Ne tür veriler, tüketici ve hangi koşullar altında ileti inceleyerek sağlayıcınız tasarlamaya başlayabilir. Komutlar, işlemleri ve diğer isteğe bağlı nesneler destek gerekip gerekmediğini belirlemek özellikle önemlidir. Önden iyi bir tasarım, uygulama ve test hızlandırır.

Örneğin, iki parça halinde sunulur:

- İlk bölümü gösterir nasıl [basit bir salt okunur sağlayıcı oluşturma](../../data/oledb/implementing-the-simple-read-only-provider.md) , dizelerden oluşan bir çift okur.

- İkinci bölümü gösterir nasıl [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md) ekleyerek `IRowsetLocate` arabirimi.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
