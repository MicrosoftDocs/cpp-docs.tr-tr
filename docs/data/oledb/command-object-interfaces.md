---
title: Komut Nesnesi Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: d9f663d4e857d300e5c0f5783b86445ce824ea8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598880"
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri

Komut nesnesi kullanır `IAccessor` parametresi bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizisi geçirerek `DBBINDING` yapıları. `DBBINDING` Sütun bağlamaları (örneğin, türde ve uzunluktaki) hakkında bilgi içerir. Sağlayıcı, yapıları alır ve verileri nasıl transfer ve dönüştürmeler gerekli olup belirler.

`ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi komut özellikleri işler.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
