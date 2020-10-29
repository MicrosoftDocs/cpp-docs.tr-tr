---
title: Sağlayıcı Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
ms.openlocfilehash: 5a24245ae19fc6fa2a66d4bf102765b712b4cf5c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921511"
---
# <a name="creating-the-provider"></a>Sağlayıcı Oluşturma

::: moniker range="msvc-160"

ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

## <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB sağlayıcı sihirbazıyla OLE DB sağlayıcı oluşturmak için

1. Projeye sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle** ' ye tıklayın.

1. **Sınıf Ekle** iletişim kutusunda, **yüklü** > **Visual C++** > **ATL** altında, **ATL OLEDB Sağlayıcısı** simgesini seçin ve ardından **Aç** ' a tıklayın.

1. **ATL OLE DB sağlayıcı sihirbazında** , **kısa ad** kutusuna sağlayıcınız için kısa bir ad girin. Aşağıdaki konular *özel* kısa adı kullanır, ancak başka bir ad kullanabilirsiniz. Diğer ad kutuları, girdiğiniz ada göre doldurulur.

1. Gerekirse diğer ad kutularını düzenleyin. Nesne ve dosya adlarına ek olarak, aşağıdakileri düzenleyebilirsiniz:

   - **Coclass** : com tarafından sağlayıcıyı oluşturmak için kullanılan ad.

   - **ProgID** : GUID yerine kullanılabilen bir metin dizesi olan programlı tanımlayıcı.

   - **Sürüm** : sürüme bağımlı BIR programlı kimlik oluşturmak için ProgID ve coclass ile birlikte kullanılır.

1. **Finish (Son)** düğmesine tıklayın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)
