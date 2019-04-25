---
title: ATL OLE DB Tüketicisi Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: d93bf715f8fd8a03c75b1d1bf2e44f12c1d1b9c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261383"
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB Tüketicisi Ekleme

ATL OLE DB tüketici bir projeye eklemek için bu sihirbazı kullanın. ATL OLE DB tüketici bir OLE DB erişimci sınıf ve veri bağlamalarını bir veri kaynağına erişmek için gerekli oluşur. Projenin ATL COM uygulama veya (ATL OLE DB Tüketicisi Sihirbazı otomatik olarak ekler) ATL desteği içeren bir MFC veya Win32 uygulaması olarak oluşturulmuş olması gerekir.

> [!NOTE]
> Bir OLE DB Tüketicisi bir MFC projesine ekleyebilirsiniz. ATL OLE DB Tüketicisi Sihirbazı, bunu yaparsanız, projenize gerekli COM desteği ekler. Bu MFC projesi oluşturduğunuzda, seçtiğiniz varsayar **ActiveX denetimlerini** onay kutusunu (içinde **Gelişmiş Özellikler** proje MFC Uygulama Sihirbazı sayfasında), varsayılan olarak işaretli. Bu seçeneğin belirlenmesi sağlar uygulama çağırır `CoInitialize` ve `CoUninitialize`. Seçeneğini belirlemediyseniz **ActiveX denetimlerini** MFC projesi oluşturduğunuzda, çağırmanız gerekir `CoInitialize` ve `CoUninitialize` ana kod.

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>ATL OLE DB Tüketici projenize eklemek için

1. İçinde **sınıf görünümü**, projeye sağ tıklayın. Kısayol menüsünde **Ekle** ve ardından **sınıfı Ekle**.

1. Visual C++ klasörünü çift tıklatarak **ATL OLE DB Tüketicisi** simgesi veya seçin ve **açık**.

   ATL OLE DB Tüketicisi Sihirbazı açılır.

1. Bölümünde anlatıldığı gibi ayarları tanımlama [ATL OLE DB Tüketicisi Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md).

1. Tıklayın **son** sihirbazı kapatın. Yeni oluşturulan OLE DB Tüketici kod projenize eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
