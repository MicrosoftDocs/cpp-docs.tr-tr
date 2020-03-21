---
title: ATL Özellik sayfası ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 3e27d276e5500c1e32ca7b576b355f14f18a47f6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075271"
---
# <a name="adding-an-atl-property-page"></a>ATL Özellik sayfası ekleme

> [!NOTE]
> ATL Özellik sayfası Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

Projenize bir etkin şablon kitaplığı (ATL) özellik sayfası eklemek için projenizin ATL uygulaması olarak veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş olması gerekir. Bir atl uygulaması oluşturmak veya bir MFC uygulaması için ATL desteği uygulamak üzere [MFC UYGULAMANıZA ATL nesnesi eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) Için [atl Proje Sihirbazı](../../atl/reference/atl-project-wizard.md) ' nı kullanabilirsiniz.

Denetim için bir özellik sayfası ekliyorsanız, denetiminiz [ıdiifyıpropertypagesimpl](../../atl/reference/ispecifypropertypagesimpl-class.md) arabirimini desteklemelidir. Varsayılan olarak, [atl Denetim Sihirbazı 'nı](../../atl/reference/atl-control-wizard.md)kullanarak [bir ATL denetimi oluşturduğunuzda](../../atl/reference/adding-an-atl-control.md) , bu arabirim denetim sınıfınızın türetme listesinde bulunur.

> [!NOTE]
> Denetim sınıfınız, türetme listesinde [ıdiifyıpropertypagesimpl](../../atl/reference/ispecifypropertypagesimpl-class.md) içermiyorsa, el ile eklemeniz gerekir.

## <a name="to-add-an-atl-property-page-to-your-project"></a>Projenize bir ATL Özellik sayfası eklemek için

1. **Çözüm Gezgini** ya da [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), atl özellik sayfasını eklemek istediğiniz projenin adına sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle**' ye tıklayın.

1. [Sınıf Ekle](../../ide/add-class-dialog-box.md) Iletişim kutusundaki **Şablonlar** bölmesinde, **ATL Özellik** sayfası ' na tıklayın ve ardından [atl özellik sayfası Sihirbazı 'nı](../../atl/reference/atl-property-page-wizard.md)göstermek için **Aç** ' a tıklayın.

Bir denetim için bir özellik sayfası oluşturduktan sonra, denetimin özellik eşlemesinde [PROP_PAGE](property-map-macros.md#prop_page) girişi sağlamanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../../atl/atl-com-property-pages.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)
