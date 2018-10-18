---
title: Sağlayıcı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 10/15/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0dbdf7350eeba1a29392bafc2f099a857e212e37
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410752"
---
# <a name="creating-the-provider"></a>Sağlayıcı Oluşturma

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcısı Sihirbazı ile bir OLE DB sağlayıcısı oluşturmak için

1. Projeye sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.

1. İçinde **sınıfı Ekle** iletişim kutusunun **yüklü** > **Visual C++** > **ATL**, seçin**ATL OLEDB Sağlayıcısı** simgesine ve ardından **açık**.

1. İçinde **ATL OLE DB sağlayıcısı Sihirbazı**, sağlayıcınız için kısa bir ad girin **kısa ad** kutusu. Kısa ad "MyProvider" aşağıdaki konuları kullanın, ancak başka bir ad kullanabilirsiniz. Girdiğiniz ad göre diğer ad kutularını doldurun.

1. Gerekirse diğer ad kutularını düzenleyin. Nesne ve dosya adları ek olarak, aşağıdaki düzenleyebilirsiniz:

   - **Coclass'ı**: COM sağlayıcısı oluşturmak için kullanacağı ad.

   - **ProgID**: bir GUID yerine kullanılabilecek bir metin dizesi olan program tanımlayıcısı.

   - **Sürüm**: ProgID ve coclass'ı ile bir sürümüne bağımlı program kimliği oluşturmak için kullanılan

1. **Son**'a tıklayın.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)
