---
title: ATL özellik sayfası ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c84cdabddb96d2deeecd09f26101e37d9c99d0ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357075"
---
# <a name="adding-an-atl-property-page"></a>ATL özellik sayfası ekleme
Etkin Şablon kitaplığı (ATL) özellik sayfası projenize eklemek için projenize ATL uygulamasını veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş olması gerekir. Kullanabileceğiniz [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md) ATL uygulamasını oluşturmak için veya [ATL nesne MFC uygulamanıza eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC uygulaması için ATL desteği uygulamak için.  
  
 Bir denetim için bir özellik sayfası ekliyorsanız, Denetim desteklemelidir [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) arabirimi. Varsayılan olarak, bu denetim türetme listesinde arabirimidir sınıfı, [ATL Denetim oluşturma](../../atl/reference/adding-an-atl-control.md) kullanarak [ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Denetim sınıfınıza yoksa [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) kendi türetme listesinde onu el ile eklemeniz gerekir.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>Projenize ATL özellik sayfası ekleme  
  
1.  Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), ATL özellik sayfası eklemek istediğiniz proje adına sağ tıklayın.  
  
2.  Kısayol menüsünden tıklatın **Ekle** ve ardından **sınıfı Ekle**.  
  
3.  İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) Şablonlar bölmesinde iletişim kutusu **ATL özellik sayfası** ve ardından **açık** görüntülenecek [ATL Özellik Sayfası Sihirbazı](../../atl/reference/atl-property-page-wizard.md).  
  
 Bir denetim için bir özellik sayfası oluşturduktan sonra sağlamanız gereken [PROP_PAGE](property-map-macros.md#prop_page) denetimi için özellik eşlemesi girişi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../../atl/atl-com-property-pages.md)   
 [ATL COM nesneleri temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)

