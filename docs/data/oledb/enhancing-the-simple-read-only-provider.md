---
title: Basit salt okunur sağlayıcıyı geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f798eb6219fdbc6c54e4c80474491f84f25a8060
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216480"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Basit Salt Okunur Sağlayıcıyı Geliştirme

Bu bölüm nasıl geliştirileceğini gösterir [basit salt okunur sağlayıcıyı](../../data/oledb/implementing-the-simple-read-only-provider.md) önceki bölümde oluşturduğunuz. `IRowsetLocateImpl` için bir uygulama oluşturur `IRowsetLocate` arabirim ve sizin için yer işareti desteği ekler.

Çalışma sağlayıcısı olduğunda olmak sağlayıcısı güncelleştirme işlemi işleyeceği veya satır getirme algoritmasının performansını artırmak için artırmak isteyebilirsiniz. Var olan bir COM nesnesine bir arabirim ekleme çoğu sağlayıcı geliştirmeleri içerir.

Aşağıdaki konularda örnek ekleyerek satır getirme mekanizması geliştirir `IRowsetLocate` arabirimini `CAgentRowset`. Konular şunları nasıl yapacağınız için:

- [IRowsetLocate devralır RCustomRowset olun](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Bir Salt Okunur Sağlayıcı Oluşturma](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
