---
title: Komut nesnesi arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8176bad2921edd22edaab1688e38bc7de275b0bb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074806"
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri

Komut nesnesi kullanır `IAccessor` parametresi bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizisi geçirerek `DBBINDING` yapıları. `DBBINDING` Sütun bağlamaları (örneğin, türde ve uzunluktaki) hakkında bilgi içerir. Sağlayıcı, yapıları alır ve verileri nasıl transfer ve dönüştürmeler gerekli olup belirler.

`ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi komut özellikleri işler.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)