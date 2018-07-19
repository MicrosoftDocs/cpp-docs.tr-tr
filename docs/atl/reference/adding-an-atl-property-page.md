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
ms.openlocfilehash: 54546c590104545a7ea5cd80bfaa774f5391cef3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956579"
---
# <a name="adding-an-atl-property-page"></a>ATL özellik sayfası ekleme
Bir Etkin Şablon kitaplığı (ATL) özellik sayfasını projeye eklemek için projenize ATL uygulamasını veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../../atl/reference/atl-project-wizard.md) ATL uygulamasını oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.  
  
 Bir özellik sayfası denetimi için ekliyorsanız, denetiminizin desteklemelidir [Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md) arabirimi. Varsayılan olarak, bu denetim türetme listesinde arabirimidir sınıfı, [ATL denetimi oluşturma](../../atl/reference/adding-an-atl-control.md) kullanarak [ATL denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md).  
  
> [!NOTE]
>  Denetim sınıfınıza yoksa [Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md) kendi türetme listesinde onu el ile eklemeniz gerekir.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>ATL özellik sayfası projenize eklemek için  
  
1.  Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ATL özellik sayfası eklemek istediğiniz proje adına sağ tıklayın.  
  
2.  Kısayol menüsünden tıklayın **Ekle** ve ardından **sınıfı Ekle**.  
  
3.  İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) Şablonlar bölmesinde, iletişim kutusu **ATL özellik sayfası** ve ardından **açık** görüntülenecek [ATL Özellik Sayfası Sihirbazı](../../atl/reference/atl-property-page-wizard.md).  
  
 Bir denetim için bir özellik sayfası oluşturduktan sonra sağlamanız gereken [PROP_PAGE](property-map-macros.md#prop_page) girişi denetimi için özellik eşlemesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../../atl/atl-com-property-pages.md)   
 [ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)

