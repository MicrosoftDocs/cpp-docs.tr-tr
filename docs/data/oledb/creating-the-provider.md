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
ms.openlocfilehash: 230620a2375ac5aa822e55496d1f26751ee6f7b3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055352"
---
# <a name="creating-the-provider"></a>Sağlayıcı Oluşturma

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcısı Sihirbazı ile bir OLE DB sağlayıcısı oluşturmak için

1. Projeye sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.

1. İçinde **sınıfı Ekle** iletişim kutusunun **yüklü** > **Visual C++** > **ATL**, seçin**ATL OLEDB Sağlayıcısı** simgesine ve ardından **açık**.

1. İçinde **ATL OLE DB sağlayıcısı Sihirbazı**, sağlayıcınız için kısa bir ad girin **kısa ad** kutusu. Kısa ad aşağıdaki konuları kullanın *özel*, ancak başka bir ad kullanabilirsiniz. Girdiğiniz ad göre diğer ad kutularını doldurun.

1. Gerekirse diğer ad kutularını düzenleyin. Nesne ve dosya adları ek olarak, aşağıdaki düzenleyebilirsiniz:

   - **Coclass'ı**: COM sağlayıcısı oluşturmak için kullanacağı ad.

   - **ProgID**: bir GUID yerine kullanılabilecek bir metin dizesi olan program tanımlayıcısı.

   - **Sürüm**: ProgID ve coclass'ı ile bir sürümüne bağımlı program kimliği oluşturmak için kullanılan

1. **Son**'a tıklayın.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)
