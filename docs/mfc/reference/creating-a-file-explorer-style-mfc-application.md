---
title: Dosya Gezgini stilinde MFC uygulaması oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcexplorer.project
dev_langs:
- C++
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b0f5d4bdabc987d4f4177f616ce756c351b8b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Dosya Gezgini Stilinde MFC Uygulaması Oluşturma
Birçok Windows sistem uygulama kullanıcı arabirimi (UI) için dosya Gezgini'ni kullanın. Örneğin, dosya Explorer'ı başlattığınızda, uygulama istemci alanını bölme çubuğu Dikey bölme ile bakın. İstemci alanını sol tarafındaki gezinti ve göz atma özellikleri sağlar ve istemci alanını sağ tarafındaki ayrıntıları seçime uygun sol bölmede gösterir. Bir kullanıcı sol bölmesindeki bir öğeyi tıklattığında, uygulamayı sağ bölmede yeniden doldurur. MDI uygulamada üzerinde komutlarını kullanabilirsiniz **Görünüm** sağ bölmede gösterilen ayrıntı miktarını değiştirmek için menüsü. (Bir SDI veya birden çok üst düzey belge uygulama, yalnızca araç çubuğu düğmelerini kullanarak ayrıntı değiştirebilirsiniz.)  
  
 Bölmeleri içeriğini uygulamaya göre değişir. Sağ bölmede klasörler, tek tek dosyaların veya makineler ve bunları ayrıntılarını görüntülerken bir dosya sistemi tarayıcıda sol bölmede dizinlerin veya makineler veya makine grupları, hiyerarşik bir görünümü gösterir. İçeriği mutlaka dosyaları olması gerekmez. Bunlar, e-posta iletileri, hata raporlarını veya diğer öğeler bir veritabanında olabilir.  
  
 Sihirbaz aşağıdaki sınıflar sizin için oluşturur:  
  
-   **CLeftView** sınıfı istemci alanını sol bölmesinde tanımlar. Bu her zaman türetilir [CTreeView](../../mfc/reference/ctreeview-class.md).  
  
-   C*ProjName*görünüm sınıfı istemci alanını sağ bölmesinde tanımlar. Öğesinden türetilen varsayılan olarak, [CListView](../../mfc/reference/clistview-class.md) ancak başka bir görünüme bağlı olarak, belirttiğiniz sınıf türünde olabilir **temel sınıfı** listesinde [oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfası Sihirbazı.  
  
 Oluşturulan uygulamanın tek belge arabirimi (SDI), birden çok belge arabirimi (MDI) veya birden çok üst düzey belgeleri mimarisi olabilir. Bir uygulama oluşturur her çerçeve penceresi kullanarak Dikey bölme [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md). Bu uygulama türü kodlama, bu tür bir uygulama her Bölümlendirici bölmesinden ayrı denetim görünümleri olan bir ayırıcı kullanan normal bir MFC uygulaması kodlama için benzer.  
  
 Sağ bölmede varsayılan liste görünümünü kullanıyorsanız, sihirbaz ek menü seçenekleri (yalnızca MDI uygulamalarda) ve araç çubuğu düğmeleri Görünüm stilini büyük simgeler, küçük simgeler, liste ve ayrıntı modlar arasında geçiş yapmak için oluşturur.  
  
### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Dosya Gezgini stilinde MFC yürütülebilir oluşturmaya başlamak için  
  
1.  İçindeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, **dosya Gezgini** proje stili.  
  
3.  Diğer sihirbaz sayfalarında istediğiniz seçenekleri ayarlayın.  
  
4.  Tıklatın **son** iskelet uygulama oluşturun.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Birden Fazla Belge Türü, Görünüm ve Çerçeve Penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Türetilmiş görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Uygulama Tasarımı Seçimleri](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)   
 [Bir Web tarayıcısı stilinde MFC uygulaması oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [Form Tabanlı MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-forms-based-mfc-application.md)

