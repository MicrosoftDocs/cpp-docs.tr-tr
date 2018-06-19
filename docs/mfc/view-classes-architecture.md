---
title: Görüntüleme sınıfları (Mimari) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.view
dev_langs:
- C++
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11bb3d9e551089a156d255f7b27fb55cbe87bdbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383753"
---
# <a name="view-classes-architecture"></a>Görünüm Sınıfları (Mimari)
`CView` ve türetilmiş sınıflarının bir çerçeve penceresinde istemci alanını temsil eden alt pencere. Görünümleri verileri görüntüleyin ve bir belge için giriş kabul edin.  
  
 View sınıfı, bir belge sınıfı ve bir belge şablonu nesnesi kullanılarak bir çerçeve pencere sınıfı ile ilişkilidir.  
  
 [CView](../mfc/reference/cview-class.md)  
 Uygulamaya özgü bir belgenin veri görünümleri için temel sınıf. Görünümler, verileri görüntülemek ve düzenlemek veya verileri seçmek için kullanıcı girişi kabul edin. Görünüm sınıfları öğesinden türetilen `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Özellikleri kaydırma ile görünümler için temel sınıf. Görünüm sınıfından türetilen `CScrollView` otomatik kaydırma için.  
  
## <a name="form-and-record-views"></a>Form ve kayıt görünümleri  
 Form görünümleri de görünümleri kaydırma. Bunlar, bir iletişim kutusu şablonunu temel alır.  
  
 Kayıt görünümleri form görünümleri türetilir. İletişim kutusu şablonu ek olarak, ayrıca bir veritabanına bir bağlantı sahiptirler.  
  
 [Cformview'yu](../mfc/reference/cformview-class.md)  
 Düzeni bir iletişim kutusu şablonda tanımlanan kaydırma görüntüleyin. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablona dayalı bir kullanıcı arabirimi uygulamak için.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Bir form sağlayan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablona dayalı.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 Bir uygulamadaki Web göz atmak için bir denetim destekler. Denetim dinamik HTML MFC'de destekler.  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 MFC OLE DB desteği için form görünümleri sağlar.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Bir form sağlayan bir açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablona dayalı.  
  
## <a name="control-views"></a>Denetim görünümleri  
 Denetim görünümleri denetim kendi görünüm olarak görüntüler.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows denetimleriyle ilişkili tüm görünümleri için temel sınıf. Denetimlere bağlı görünümler aşağıda açıklanmıştır.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bir Windows standart içeren bir görünüm düzenleme denetimi (bkz [CEdit](../mfc/reference/cedit-class.md)). Destek metin düzenleme denetimleri, arama, değiştirme ve yetenekleri kaydırma düzenleyin.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Zengin Windows içeren bir görünüm düzenleme denetimi (bkz [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzen denetimi özelliklere ek olarak, denetimleri destek yazı tipleri, renkler, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerine zengin düzenleyin.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows liste denetimi içeren bir görünüm (bkz [CListCtrl](../mfc/reference/clistctrl-class.md)). Liste denetimi bir şekilde dosya Explorer'ın sağ bölmeye benzer simgeler ve dizeleri görüntüler.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows ağaç denetimi içeren bir görünüm (bkz [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi, simgeler ve dosya Explorer'ın sol bölmeye benzer bir şekilde bir hiyerarşideki düzenlenmiş dizeleri görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

