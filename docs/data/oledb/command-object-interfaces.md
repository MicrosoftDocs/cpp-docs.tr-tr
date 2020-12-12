---
description: 'Hakkında daha fazla bilgi edinin: komut nesnesi arabirimleri'
title: Komut Nesnesi Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 07dce6a71e7afd3a47c63942d48dd78d758103f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307528"
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri

Komut nesnesi, `IAccessor` parametre bağlamalarını belirtmek için arabirimini kullanır. Tüketici `IAccessor::CreateAccessor` , bir yapı dizisi geçirerek çağırır `DBBINDING` . `DBBINDING` sütun bağlamaları (tür ve uzunluk gibi) hakkında bilgi içerir. Sağlayıcı yapıları alır ve verilerin nasıl aktarılacağını ve dönüştürmenin gerekli olup olmadığını belirler.

Arabirim, bir `ICommandText` metin komutu belirtmek için bir yol sağlar. `ICommandProperties`Arabirim tüm komut özelliklerini işler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
