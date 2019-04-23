---
title: Komut Nesnesi Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 755c44cf8d0cb5bf5066197bfd0ead3e0f25e1f9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032407"
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri

Komut nesnesi kullanır `IAccessor` parametresi bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizisi geçirerek `DBBINDING` yapıları. `DBBINDING` Sütun bağlamaları (örneğin, türde ve uzunluktaki) hakkında bilgi içerir. Sağlayıcı, yapıları alır ve verileri nasıl transfer ve dönüştürmeler gerekli olup belirler.

`ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi komut özellikleri işler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
