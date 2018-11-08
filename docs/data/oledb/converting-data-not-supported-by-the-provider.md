---
title: Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 44cdde2bad24d21adbc728c90ecd173717c02b04
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265197"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme

OLE DB sağlayıcı şablonu tüketici sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, kod `IRowsetImpl::GetData` veri türüne dönüştürmek için Msdadc.dll çağırır.

Bir arabirim uygularsanız `IRowsetChange` veri dönüştürme gerektiren, dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. Kullanım `GetData`Atldb.h, örnek olarak içinde tanımlanmış.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)