---
description: 'Daha fazla bilgi edinin: basit Read-Only sağlayıcıyı geliştirme'
title: Basit Salt Okunur Sağlayıcıyı Geliştirme
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: 00a0ea4fb9b759447026353ba0d78c7c856b15ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317649"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Basit Salt Okunur Sağlayıcıyı Geliştirme

Bu bölümde, önceki bölümde oluşturulan [basit salt okunurdur sağlayıcıyı](../../data/oledb/implementing-the-simple-read-only-provider.md) geliştirme gösterilmektedir. `IRowsetLocateImpl` arabirim için bir uygulama oluşturur `IRowsetLocate` ve sizin için yer işareti desteği ekler.

Çalışan bir sağlayıcı varsa, sağlayıcıyı güncelleştirmek, işlemleri işlemek veya satır getirme algoritmasının performansını geliştirmek için onu geliştirmek isteyebilirsiniz. Birçok sağlayıcı geliştirmesi, var olan bir COM nesnesine arabirim eklemeyi içerir.

Aşağıdaki konulardaki örnek, arabirimini öğesine ekleyerek satır getirme mekanizmasını geliştirir `IRowsetLocate` `CAgentRowset` . Konular şunları gösterir:

- [RCustomRowset 'In IRowsetLocate 'ten devralmasını sağlayın](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Tüketiciye döndürülen sütunları dinamik olarak belirleme](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca bkz.

[Basit bir Read-Only sağlayıcısı oluşturma](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
