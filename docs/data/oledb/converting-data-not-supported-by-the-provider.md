---
title: Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: a53781f71a55dfb07dc996e5e25644d9337e4c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473451"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme

OLE DB sağlayıcı şablonu tüketici sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, kod `IRowsetImpl::GetData` veri türüne dönüştürmek için Msdadc.dll çağırır.

Bir arabirim uygularsanız `IRowsetChange` veri dönüştürme gerektiren, dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. Kullanım `GetData`Atldb.h, örnek olarak içinde tanımlanmış.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)