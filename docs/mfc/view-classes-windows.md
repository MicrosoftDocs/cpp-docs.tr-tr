---
title: "Görüntüleme sınıfları (Windows) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.view
dev_langs: C++
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0148ead7a978389f763efbe9ee6306ec7a5839cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="view-classes-windows"></a>Görünüm Sınıfları (Windows)
`CView`ve türetilmiş sınıflarının bir çerçeve penceresinde istemci alanını temsil eden alt pencere. Görünümleri verileri görüntüleyin ve bir belge için giriş kabul edin.  
  
 View sınıfı, bir belge sınıfı ve bir belge şablonu nesnesi kullanılarak bir çerçeve pencere sınıfı ile ilişkilidir.  
  
 [CView](../mfc/reference/cview-class.md)  
 Uygulamaya özgü bir belgenin veri görünümleri için temel sınıf. Görünümler, verileri görüntülemek ve düzenlemek veya verileri seçmek için kullanıcı girişi kabul edin. View sınıfı veya sınıftan türetilen `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Özellikleri kaydırma ile görünümler için temel sınıf. Görünüm sınıfından türetilen `CScrollView` otomatik kaydırma için.  
  
## <a name="form-and-record-views"></a>Form ve kayıt görünümleri  
 Form görünümleri de görünümleri kaydırma. Bunlar, bir iletişim kutusu şablonunu temel alır.  
  
 Kayıt görünümleri form görünümleri türetilir. İletişim kutusu şablonu ek olarak, ayrıca bir veritabanına bir bağlantı sahiptirler.  
  
 [Cformview'yu](../mfc/reference/cformview-class.md)  
 Düzeni bir iletişim kutusu şablonda tanımlanan kaydırma görüntüleyin. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablona dayalı bir kullanıcı arabirimi uygulamak için.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Bir form sağlayan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablona dayalı.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Bir form sağlayan bir açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablona dayalı.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 WebBrowser HTML düzenleme platform işlevlerini sağlayan bir form görünümü.  
  
## <a name="control-views"></a>Denetim görünümleri  
 Denetim görünümleri denetim kendi görünüm olarak görüntüler.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows denetimleriyle ilişkili tüm görünümleri için temel sınıf. Denetimlere bağlı görünümler aşağıda açıklanmıştır.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bir Windows standart içeren bir görünüm düzenleme denetimi (bkz [CEdit](../mfc/reference/cedit-class.md)). Destek metin düzenleme denetimleri, arama, değiştirme ve yetenekleri kaydırma düzenleyin.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Zengin Windows içeren bir görünüm düzenleme denetimi (bkz [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzen denetimi özelliklere ek olarak, denetimleri destek yazı tipleri, renkler, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerine zengin düzenleyin.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows liste denetimi içeren bir görünüm (bkz [CListCtrl](../mfc/reference/clistctrl-class.md)). Öğeleri koleksiyonu, her bir simge ve dosya Explorer'ın sağ bölmeye benzer bir şekilde bir etiket oluşan bir liste denetimini gösterir.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows ağaç denetimi içeren bir görünüm (bkz [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi simgeler ve bir şekilde dosya Explorer'ın sol bölmeye benzer düzenlenmiş etiketleri hiyerarşik bir listesini görüntüler.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 `CSplitterWnd`bir tek çerçeve penceresi içinde birden çok görünüm sahip olmanızı sağlar. `CPrintDialog`ve `CPrintInfo` görünümleri yazdırma ve baskı önizleme özelliğini destekler. `CRichEditDoc`ve `CRichEditCntrItem` ile kullanılan `CRichEditView` OLE kapsayıcı özellikleri uygulamak için.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 Kullanıcı birden fazla bölmelere bölebilirsiniz penceresini açın. Bu bölmeleri kullanıcı veya sabit bir boyuta göre yeniden boyutlandırılabilir olabilir.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Bir dosya yazdırma için bir standart iletişim kutusu sağlar.  
  
 [Cprintınfo](../mfc/reference/cprintinfo-structure.md)  
 Yazdırın veya Önizleme işle ilgili bilgileri içeren bir yapısı. Tarafından kullanılan `CView`mimarisi yazdırma.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Bulunan OLE istemci öğeleri listesini tutar bir `CRichEditView`.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Öğesi içinde depolanan bir OLE istemci-tarafı erişim sağlayan bir `CRichEditView`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

