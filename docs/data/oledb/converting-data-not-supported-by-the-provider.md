---
title: Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e60f6cd4f7dca1ed3e176cabefc42f69946436a4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033845"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme

OLE DB sağlayıcı şablonu tüketici sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, kod `IRowsetImpl::GetData` veri türüne dönüştürmek için Msdadc.dll çağırır.

Bir arabirim uygularsanız `IRowsetChange` veri dönüştürme gerektiren, dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. Kullanım `GetData`Atldb.h, örnek olarak içinde tanımlanmış.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)