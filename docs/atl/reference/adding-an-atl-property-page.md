---
title: ATL özellik sayfası ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 81f793fbdc6d9dda567051b8c35a96f3d3f2f470
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524623"
---
# <a name="adding-an-atl-property-page"></a>ATL özellik sayfası ekleme

> [!NOTE] 
> ATL Özellik Sayfası Sihirbazı, Visual Studio 2019 bulunan ve daha yeni değil.

Bir Etkin Şablon kitaplığı (ATL) özellik sayfasını projeye eklemek için projenize ATL uygulamasını veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../../atl/reference/atl-project-wizard.md) ATL uygulamasını oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

Bir özellik sayfası denetimi için ekliyorsanız, denetiminizin desteklemelidir [Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md) arabirimi. Varsayılan olarak, bu denetim türetme listesinde arabirimidir sınıfı, [ATL denetimi oluşturma](../../atl/reference/adding-an-atl-control.md) kullanarak [ATL denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
> Denetim sınıfınıza yoksa [Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md) kendi türetme listesinde onu el ile eklemeniz gerekir.

## <a name="to-add-an-atl-property-page-to-your-project"></a>ATL özellik sayfası projenize eklemek için

1. Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ATL özellik sayfası eklemek istediğiniz proje adına sağ tıklayın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **sınıfı Ekle**.

1. İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) iletişim kutusundaki **şablonları** bölmesinde tıklayın **ATL özellik sayfası** ve ardından **açık** görüntülenecek[ATL Özellik Sayfası Sihirbazı](../../atl/reference/atl-property-page-wizard.md).

Bir denetim için bir özellik sayfası oluşturduktan sonra sağlamanız gereken [PROP_PAGE](property-map-macros.md#prop_page) girişi denetimi için özellik eşlemesi.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../../atl/atl-com-property-pages.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)
