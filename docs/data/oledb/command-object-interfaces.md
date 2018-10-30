---
title: Komut nesnesi arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5d09e5794b66895d4bfd6a12fe7b0e1dbeeea7f
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216337"
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri

Komut nesnesi kullanır `IAccessor` parametresi bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizisi geçirerek `DBBINDING` yapıları. `DBBINDING` Sütun bağlamaları (örneğin, türde ve uzunluktaki) hakkında bilgi içerir. Sağlayıcı, yapıları alır ve verileri nasıl transfer ve dönüştürmeler gerekli olup belirler.

`ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi komut özellikleri işler.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
