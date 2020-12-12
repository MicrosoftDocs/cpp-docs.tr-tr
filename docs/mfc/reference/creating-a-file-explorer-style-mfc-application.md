---
description: 'Daha fazla bilgi edinin: MFC uygulaması Explorer-Style dosya oluşturma'
title: Dosya Gezgini Stilinde MFC Uygulaması Oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcexplorer.project
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
ms.openlocfilehash: 9419aae58cf34ec70585b952360cb12702424381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301327"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Dosya Gezgini Stilinde MFC Uygulaması Oluşturma

Birçok Windows sistem uygulaması, dosya Gezgini için Kullanıcı arabirimini (UI) kullanır. Örneğin, dosya Gezgini 'ni başlattığınızda, istemci alanını bölen dikey bir ayırıcı çubuğu olan bir uygulama görürsünüz. İstemci alanının sol tarafında gezinti ve tarama özellikleri sağlanır ve istemci alanının sağ tarafında sol bölmedeki seçimle ilgili ayrıntılar gösterilir. Kullanıcı sol bölmedeki bir öğeye tıkladığında, uygulama sağ bölmeyi yeniden doldurur. Bir MDI uygulamasında, sağ bölmede gösterilen ayrıntı miktarını değiştirmek için **Görünüm** menüsündeki komutları kullanabilirsiniz. (Bir SDI veya birden çok üst düzey belge uygulamasında, ayrıntıları yalnızca araç çubuğu düğmelerini kullanarak değiştirebilirsiniz.)

Bölmelerin içeriği uygulamaya göre değişir. Bir dosya sistemi tarayıcısında sol bölmede dizinlerin veya makinelerin veya makine gruplarının hiyerarşik bir görünümü gösterilir. sağ bölmede klasörler, tek tek dosyalar veya makineler ve bunlarla ilgili ayrıntılar görüntülenir. İçeriğin dosya olması gerekmez. Bunlar, bir veritabanındaki e-posta iletileri, hata raporları veya diğer öğeler olabilir.

Sihirbaz sizin için aşağıdaki sınıfları oluşturur:

- `CLeftView`Sınıfı, istemci alanının sol bölmesini tanımlar. Her zaman [CTreeView](../../mfc/reference/ctreeview-class.md)' den türetilir.

- C *ProjName* görünüm sınıfı, istemci alanının sağ bölmesini tanımlar. Varsayılan olarak, [Clienstview](../../mfc/reference/clistview-class.md) 'dan türetilir, ancak sihirbazın [oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında **temel sınıf** listesinden belirttiğiniz sınıfa bağlı olarak başka bir görünüm türü olabilir.

Oluşturulan uygulamanın tek bir belge arabirimi (SDI), birden çok belge arabirimi (MDI) veya birden çok üst düzey belge mimarisi olabilir. Uygulamanın oluşturduğu her çerçeve penceresi [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)kullanılarak dikey olarak bölünür. Bu uygulama türünü kodlamak, Bölümlendirici kullanan normal bir MFC uygulamasını kodlamaya benzer, ancak bu tür bir uygulama, her Bölümlendirici bölmesi içinde ayrı denetim görünümlerine sahip olur.

Sağ bölmede varsayılan liste görünümünü kullanıyorsanız, sihirbaz daha fazla menü seçeneği (yalnızca MDI uygulamalarında) ve araç çubuğu düğmeleri oluşturarak Görünüm stilini büyük simgeler, küçük simgeler, liste ve ayrıntı modları arasında değiştirin.

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Dosya Gezgini stilinde MFC yürütülebilir dosyası oluşturmaya başlamak için

1. [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md)yönergelerini izleyin.

1. MFC Uygulama Sihirbazı [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, **Dosya Gezgini** proje stilini seçin.

1. Sihirbazın diğer sayfalarında istediğiniz diğer seçenekleri ayarlayın.

1. İskelet uygulamasını oluşturmak için **son** ' a tıklayın.

Daha fazla bilgi için bkz:

- [Birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [Türetilmiş Görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md)

- [Uygulama tasarımı seçimleri](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Web Browser-Style MFC uygulaması oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[Forms-Based MFC uygulaması oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md)
