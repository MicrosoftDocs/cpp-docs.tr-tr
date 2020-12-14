---
description: 'Hakkında daha fazla bilgi edinin: tür kitaplığından MFC sınıfı ekleme'
title: Tür Kitaplığından Bir MFC Sınıfı Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: b5a9979e2581eb3a560736c57c4b1eac4a7e1e81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248378"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Tür Kitaplığından Bir MFC Sınıfı Ekleme

Kullanılabilir bir tür kitaplığındaki arabirimden bir MFC sınıfı oluşturmak için bu sihirbazı kullanın. MFC [uygulamasına](../../mfc/reference/creating-an-mfc-application.md), MFC [DLL](../../mfc/reference/creating-an-mfc-dll-project.md)'sine veya [MFC ActiveX denetimine](../../mfc/reference/creating-an-mfc-activex-control.md)MFC sınıfı ekleyebilirsiniz.

> [!NOTE]
> Bir tür kitaplığından bir sınıf eklemek için Otomasyon etkin olan MFC projenizi oluşturmanız gerekmez.

Bir tür kitaplığı, bir bileşen tarafından sunulan arabirimlerin, parametreleri ve dönüş türleriyle birlikte yöntemlerini tanımlayarak ikili bir açıklamasını içerir. Tür kitaplığınızın, TypeLib 'den sınıf ekleme Sihirbazı ' nda **kullanılabilir tür kitaplıkları** listesinde görünmesi için kayıtlı olması gerekir.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Bir tür kitaplığından bir MFC sınıfı eklemek için

1. **Çözüm Gezgini** ya da [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), sınıfı eklemek istediğiniz projenin adına sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Sınıf Ekle**' ye tıklayın.

1. [Sınıf Ekle](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusunda, Şablonlar bölmesinde, **TypeLib 'den MFC sınıfı**' na tıklayın ve ardından **Aç** ' a tıklayarak [tür kitaplığı 'ndan Sınıf Ekle sihirbazını](../../mfc/reference/add-class-from-typelib-wizard.md)görüntüleyin.

Sihirbazda, bir tür kitaplığına birden fazla sınıf ekleyebilirsiniz. Benzer şekilde, tek bir sihirbaz oturumunda birden fazla tür kitaplığından sınıflar ekleyebilirsiniz.

Sihirbaz, seçilen tür kitaplığından eklediğiniz her arabirim için [Cotadispatchdriver](../../mfc/reference/coledispatchdriver-class.md)sınıfından TÜRETILMIŞ bir MFC sınıfı oluşturur. `COleDispatchDriver` OLE otomasyonunun istemci tarafını uygular.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon Istemcileri](../../mfc/automation-clients.md)<br/>
[Otomasyon Istemcileri: tür kitaplıklarını kullanma](../../mfc/automation-clients-using-type-libraries.md)
