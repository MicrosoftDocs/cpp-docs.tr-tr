---
title: Dosya Gezgini Stilinde MFC Uygulaması Oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcexplorer.project
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
ms.openlocfilehash: 3ddeb2e875ccdb45dd0bc2b29a2da3c1498138ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564768"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Dosya Gezgini Stilinde MFC Uygulaması Oluşturma

Çoğu Windows Sistem uygulamaları kullanıcı arabirimi (UI) için dosya Gezgini'ni kullanın. Örneğin, dosya Gezgini başlattığınızda, uygulama istemci alanını bölme çubuğu dikey bir ayırıcı ile bakın. İstemci alanını sol tarafındaki gezinti ve göz atma özellikleri sağlar ve istemci alanının sağ tarafındaki ayrıntıları seçime uygun sol bölmede gösterir. Kullanıcı sol bölmesindeki bir öğeye tıkladığında, uygulamayı sağ bölmeye yeniden doldurur. Bir MDI uygulamasında, şirket komutlarını kullanabilirsiniz **görünümü** sağ bölmede gösterilen ayrıntı miktarını değiştirmek için menü. (Bir SDI veya birden çok en üst düzey belge uygulaması, yalnızca araç çubuğu düğmeleri kullanarak ayrıntılı değiştirebilirsiniz.)

Bölmeleri içeriğini uygulamaya göre değişir. Sağ bölmede, klasörler, tek tek dosyalar ya da makineleri ve bunlarla ilgili ayrıntıları görüntülerken bir dosya sistemi tarayıcıda sol bölmede, dizinleri, makineler veya makine grupları, hiyerarşik bir görünümü gösterir. İçeriği mutlaka dosyaları olması gerekmez. Bunlar, e-posta iletileri, hata raporlarını veya diğer öğeleri bir veritabanı olabilir.

Aşağıdaki sınıflar sihirbaz sizin için oluşturur:

- `CLeftView` İstemci alanını sol bölmesinde sınıfı tanımlar. Bu her zaman türetilir [CTreeView](../../mfc/reference/ctreeview-class.md).

- C*ProjName*istemci alanının sağ bölme görünüm sınıfı tanımlar. Öğesinden türetilen varsayılan olarak, [CListView](../../mfc/reference/clistview-class.md) görünümü, belirttiğiniz sınıfı bağlı olarak başka bir türde olabilir, ancak **temel sınıfı** listesinde [oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfası Sihirbaz.

Oluşturulan uygulamayı tek Belgeli Arabirim (SDI), birden çok Belgeli Arabirim (MDI) veya bir birden çok üst düzey belge mimarisi olabilir. Uygulama oluşturur. her bir çerçeve penceresi kullanarak dikey olarak Böl [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md). Bu uygulama türü kodlama, bu tür bir uygulama her bölme bölmesinden ayrı denetim görünümleri olan bir ayırıcı kullanan normal bir MFC uygulaması kodlamaya benzerdir.

Sağ bölmede varsayılan liste görünümü kullanırsanız, sihirbaz ek menü seçenekleri (yalnızca MDI uygulamalarda) ve araç çubuğu düğmeleri Görünüm stilini büyük simgeler, küçük simgeler, liste ve ayrıntı modları arasında geçiş yapmak için oluşturur.

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Dosya Gezgini stilinde MFC yürütülebilir oluşturmaya başlamak için

1. Bölümündeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).

1. MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **dosya Gezgini** proje stili.

1. Diğer sihirbaz sayfalarında istediğiniz seçenekleri ayarlayın.

1. Tıklayın **son** çatı uygulama oluşturun.

Daha fazla bilgi için bkz.:

- [Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [Türetilmiş görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md)

- [Uygulama Tasarımı Seçimleri](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[Form Tabanlı MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md)

