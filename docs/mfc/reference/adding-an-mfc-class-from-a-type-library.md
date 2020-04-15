---
title: Tür Kitaplığından Bir MFC Sınıfı Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: bf9c763a215a4880d5b0ad206f6a347341fea9eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371717"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Tür Kitaplığından Bir MFC Sınıfı Ekleme

Kullanılabilir tür kitaplığındaki arabirimden bir MFC sınıfı oluşturmak için bu sihirbazı kullanın. Bir [MFC uygulamasına,](../../mfc/reference/creating-an-mfc-application.md)Bir [MFC DLL'ye](../../mfc/reference/creating-an-mfc-dll-project.md)veya [MFC ActiveX denetimine](../../mfc/reference/creating-an-mfc-activex-control.md)Bir MFC sınıfı ekleyebilirsiniz.

> [!NOTE]
> Bir tür kitaplığından bir sınıf eklemek için Otomasyon etkinleştirilmiş olan MFC projenizi oluşturmanız gerekmez.

Tür kitaplığı, bir bileşen tarafından açığa çıkarılan arabirimlerin ikili açıklamasını içerir ve yöntemleri parametreleri ve dönüş türleri ile birlikte tanımlar. Typelib Sihirbazı'ndan Sınıf Ekle'deki **Kullanılabilir tür kitaplıkları** listesinde görünmesi için tür kitaplığınız kayıtlı olmalıdır. Daha fazla bilgi için MSDN kitaplığında "İç Dağıtılmış COM: Tür Kitaplıkları ve Dil Tümleştirmesi" başlıklı yazıya bakın.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Tür kitaplığından MFC sınıfı eklemek için

1. Çözüm **Gezgini** veya [Sınıf Görünümü'nde,](/visualstudio/ide/viewing-the-structure-of-code)sınıfı eklemek istediğiniz projenin adını sağ tıklatın.

1. Kısayol menüsünden **Ekle'yi**tıklatın ve sonra **Sınıf Ekle'yi**tıklatın.

1. Sınıf [Ekle](../../ide/add-class-dialog-box.md) iletişim kutusunda, Şablonlar bölmesinde **Typelib'den MFC Sınıfı'nı**tıklatın ve ardından [Typelib Sihirbazı'ndan Sınıf Ekle'yi](../../mfc/reference/add-class-from-typelib-wizard.md)görüntülemek için **Aç'ı** tıklatın.

Sihirbazda, tür kitaplığına birden fazla sınıf ekleyebilirsiniz. Aynı şekilde, tek bir sihirbaz oturumunda birden fazla tür kitaplığı sınıfları ekleyebilirsiniz.

Sihirbaz, seçili tür kitaplığından eklediğiniz her arabirim için [COleDispatchDriver'dan](../../mfc/reference/coledispatchdriver-class.md)türetilen bir MFC sınıfı oluşturur. `COleDispatchDriver`OLE otomasyonunun istemci tarafını uygular.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon Müşterileri](../../mfc/automation-clients.md)<br/>
[Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)
