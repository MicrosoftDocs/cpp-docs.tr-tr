---
title: Sağlayıcı Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 7a8b4caf85ff7d0310c97cb953739796cca21c43
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707572"
---
# <a name="creating-the-provider"></a>Sağlayıcı Oluşturma

::: moniker range="vs-2019"

ATL OLE DB sağlayıcısı Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil.

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcısı Sihirbazı ile bir OLE DB sağlayıcısı oluşturmak için

1. Projeye sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.

1. İçinde **sınıfı Ekle** iletişim kutusunun **yüklü** > **Visual C++**  > **ATL**seçin **ATL OLEDB Sağlayıcısı** simgesine ve ardından **açık**.

1. İçinde **ATL OLE DB sağlayıcısı Sihirbazı**, sağlayıcınız için kısa bir ad girin **kısa ad** kutusu. Kısa ad aşağıdaki konuları kullanın *özel*, ancak başka bir ad kullanabilirsiniz. Girdiğiniz ad göre diğer ad kutularını doldurun.

1. Gerekirse diğer ad kutularını düzenleyin. Nesne ve dosya adları ek olarak, aşağıdaki düzenleyebilirsiniz:

   - **Coclass'ı**: COM sağlayıcısı oluşturmak için kullanacağı ad.

   - **ProgID**: Bir GUID yerine kullanılabilecek bir metin dizesi olan program tanımlayıcısı.

   - **Sürüm**: ProgID ve coclass'ı ile bir sürümüne bağımlı program kimliği oluşturmak için kullanılan

1. **Son**'a tıklayın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)
