---
title: ATL OLE DB Tüketicisi Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: 7925063e03522c96d251748b23b6b929733999a1
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524633"
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB Tüketicisi Ekleme

::: moniker range="vs-2019"

ATL OLE DB Tüketicisi Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. İşlevselliğini el ile eklemeye devam edebilirsiniz. Daha fazla bilgi için [olmadan bir tüketici kullanarak sihirbaz oluşturma](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="vs-2017"

ATL OLE DB tüketici bir projeye eklemek için bu sihirbazı kullanın. ATL OLE DB tüketici bir OLE DB erişimci sınıf ve veri bağlamalarını bir veri kaynağına erişmek için gerekli oluşur. Projenin ATL COM uygulama veya (ATL OLE DB Tüketicisi Sihirbazı otomatik olarak ekler) ATL desteği içeren bir MFC veya Win32 uygulaması olarak oluşturulmuş olması gerekir.

> [!NOTE]
> Bir OLE DB Tüketicisi bir MFC projesine ekleyebilirsiniz. ATL OLE DB Tüketicisi Sihirbazı, bunu yaparsanız, projenize gerekli COM desteği ekler. Bu MFC projesi oluşturduğunuzda, seçtiğiniz varsayar **ActiveX denetimlerini** onay kutusunu (içinde **Gelişmiş Özellikler** proje MFC Uygulama Sihirbazı sayfasında), varsayılan olarak işaretli. Bu seçeneğin belirlenmesi sağlar uygulama çağırır `CoInitialize` ve `CoUninitialize`. Seçeneğini belirlemediyseniz **ActiveX denetimlerini** MFC projesi oluşturduğunuzda, çağırmanız gerekir `CoInitialize` ve `CoUninitialize` ana kod.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>ATL OLE DB Tüketici projenize eklemek için

1. İçinde **sınıf görünümü**, projeye sağ tıklayın. Kısayol menüsünde **Ekle** ve ardından **sınıfı Ekle**.

1. Visual C++ klasörünü çift tıklatarak **ATL OLE DB Tüketicisi** simgesi veya seçin ve **açık**.

   ATL OLE DB Tüketicisi Sihirbazı açılır.

1. Bölümünde anlatıldığı gibi ayarları tanımlama [ATL OLE DB Tüketicisi Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md).

1. Tıklayın **son** sihirbazı kapatın. Yeni oluşturulan OLE DB Tüketici kod projenize eklenir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
