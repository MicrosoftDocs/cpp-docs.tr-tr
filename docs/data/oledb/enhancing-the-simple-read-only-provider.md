---
title: Basit Salt Okunur Sağlayıcıyı Geliştirme
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: d61f24a9a9abffe836a7f11bd5d1517fddf97fe7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034082"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Basit Salt Okunur Sağlayıcıyı Geliştirme

Bu bölüm nasıl geliştirileceğini gösterir [basit salt okunur sağlayıcıyı](../../data/oledb/implementing-the-simple-read-only-provider.md) önceki bölümde oluşturduğunuz. `IRowsetLocateImpl` için bir uygulama oluşturur `IRowsetLocate` arabirim ve sizin için yer işareti desteği ekler.

Çalışma sağlayıcısı olduğunda olmak sağlayıcısı güncelleştirme işlemi işleyeceği veya satır getirme algoritmasının performansını artırmak için artırmak isteyebilirsiniz. Var olan bir COM nesnesine bir arabirim ekleme çoğu sağlayıcı geliştirmeleri içerir.

Aşağıdaki konularda örnek ekleyerek satır getirme mekanizması geliştirir `IRowsetLocate` arabirimini `CAgentRowset`. Konular şunları nasıl yapacağınız için:

- [IRowsetLocate devralır RCustomRowset olun](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca bkz.

[Basit Bir Salt Okunur Sağlayıcı Oluşturma](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
