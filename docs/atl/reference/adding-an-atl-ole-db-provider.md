---
title: ATL OLE DB Sağlayıcısı Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, adding ATL OLE DB provider to projects
- ATL projects, adding ATL OLE DB providers
- ATL OLE DB providers
ms.assetid: 26fba1e3-880f-4bc6-90e5-2096a48a3a6c
ms.openlocfilehash: e593fdbd1c8c48a381cb2941971ebe4e0148965d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923777"
---
# <a name="adding-an-atl-ole-db-provider"></a>ATL OLE DB Sağlayıcısı Ekleme

::: moniker range="msvc-160"

ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bir projeye ATL OLE DB sağlayıcısı eklemek için bu sihirbazı kullanın. ATL OLE DB sağlayıcı bir veri kaynağı, oturum, komut ve satır kümesi sınıflarından oluşur. Projenin bir ATL COM uygulaması olarak oluşturulmuş olması gerekir.

## <a name="to-add-an-atl-ole-db-provider-to-your-project"></a>Projenize ATL OLE DB sağlayıcısı eklemek için

1. **Sınıf görünümü** , projeye sağ tıklayın. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle** ' ye tıklayın.

1. **Visual C++** klasöründe, **ATL OLE DB sağlayıcı** simgesine çift tıklayın veya seçin ve **Aç** ' a tıklayın.

   ATL OLE DB sağlayıcı Sihirbazı açılır.

1. [ATL OLE DB sağlayıcı Sihirbazı](../../atl/reference/atl-ole-db-provider-wizard.md)'nda açıklanan ayarları tanımlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın, böylece yeni oluşturulan OLE DB sağlayıcı kodu projenize eklenir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
