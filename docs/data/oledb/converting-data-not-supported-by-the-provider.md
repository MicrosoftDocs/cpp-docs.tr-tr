---
title: Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e87aebc4d6f23343af9a2f966d2c522e95b304ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211503"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme

Tüketici, sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, `IRowsetImpl::GetData` için OLE DB sağlayıcısı şablon kodu, veri türünü dönüştürmek için Msdadc. dll ' yi çağırır.

Veri dönüştürme gerektiren `IRowsetChange` gibi bir arabirim uygularsanız, dönüştürmeyi yapmak için Msdaenum. dll ' yi çağırabilirsiniz. Atldb. h içinde tanımlanan `GetData`, örnek olarak kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
