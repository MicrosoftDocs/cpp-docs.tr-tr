---
description: 'Hakkında daha fazla bilgi edinin: sağlayıcı tarafından desteklenmeyen verileri dönüştürme'
title: Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 9fb449247ff40118e89dbebee5f43a1208a1f181
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323372"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme

Tüketici, sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, çağrı için OLE DB sağlayıcısı şablon kodu, `IRowsetImpl::GetData` veri türünü dönüştürmek üzere Msdadc.dll.

Veri dönüştürme gerektiren gibi bir arayüz uygularsanız `IRowsetChange` , dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. , `GetData` Atldb. h içinde tanımlanan, örnek olarak kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
