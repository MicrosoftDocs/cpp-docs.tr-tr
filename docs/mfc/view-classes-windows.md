---
title: Görünüm Sınıfları (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: ad58fd6fa2548c2cf320baf75b8fc33a835ddd55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296624"
---
# <a name="view-classes-windows"></a>Görünüm Sınıfları (Windows)

`CView` ve türetilmiş sınıflarının bir çerçeve penceresinin istemci alanını temsil eden alt pencereler. Görünümleri, verileri gösterme ve bir belge için giriş kabul edin.

View sınıfı, bir belge şablonu nesnesi kullanılarak bir çerçeve penceresi sınıfı ve belge sınıfı ile ilişkilidir.

[CView](../mfc/reference/cview-class.md)<br/>
Bir belgenin verilerinin uygulamaya özgü görünümler için temel sınıf. Görünümler, verileri görüntülemek ve düzenlemek veya verileri seçmek için kullanıcı girişi kabul edin. View sınıfı veya sınıflarından türetilen `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Görünümleri kaydırma özelliğine sahip bir temel sınıf. Görünüm sınıfından türetilir `CScrollView` otomatik kaydırmayı.

## <a name="form-and-record-views"></a>Form ve kayıt görünümleri

Form görünümleri, ayrıca görünümleri kaydırma. Bunlar bir iletişim kutusu şablonunu temel alır.

Kayıt görünümleri form görünümleri türetilir. İletişim kutusu şablonu yanı sıra, ayrıca bir veritabanına bir bağlantı sahiptirler.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Bir kaydırma görünümü, düzen bir iletişim kutusu şablonunda tanımlanır. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablonu temel alan bir kullanıcı arabirimini uygulamak için.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Bir form sağlar doğrudan bir veri erişim nesnesi (DAO) kayıt nesnesine bağlıdır. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablonu temel alan.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Bir form sağlar açık veritabanı bağlantısı (ODBC) kayıt nesneye doğrudan bağlı görünümü. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablonu temel alan.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
HTML WebBrowser düzenleme platformu işlevlerini sağlar bir form görünümü.

## <a name="control-views"></a>Denetim görünümleri

Denetim görünümleri, görünüm olarak bir denetim görüntüler.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows denetimleri ile ilgili tüm görünümleri için temel sınıf. Denetimlerine göre görünümleri aşağıda açıklanmıştır.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bir Windows standart içeren bir görünümü düzenleme denetimi (bkz [CEdit](../mfc/reference/cedit-class.md)). Metin denetimleri düzenleme desteği, arama, değiştirme ve kaydırma düzenleyin.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Zengin bir Windows içeren bir görünümü düzenleme denetimi (bkz [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzenleme denetimi özelliklere ek olarak, denetimleri destek yazı tiplerini, renkleri, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerine zengin düzenleme.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünümü (bkz [CListCtrl](../mfc/reference/clistctrl-class.md)). Bir öğe koleksiyonu, her bir simge ve dosya Gezgini'nin sağ bölmeye benzer bir şekilde bir etiket oluşan bir liste denetimini gösterir.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Bir Windows ağaç denetimi içeren bir görünümü (bkz [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi simgelerin ve etiketlerin bir şekilde dosya Gezgini için sol bölmedeki benzer düzenlenmiş, hiyerarşik bir listesini görüntüler.

## <a name="related-classes"></a>İlgili sınıflar

`CSplitterWnd` tek bir çerçeve içinde birden çok görünüm sahip olmanızı sağlar. `CPrintDialog` ve `CPrintInfo` görünümleri yazdırma ve yazdırma önizleme özelliğini destekler. `CRichEditDoc` ve `CRichEditCntrItem` ile kullanılan `CRichEditView` OLE kapsayıcı özellikleri uygulamak için.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
Kullanıcı birden çok bölmelere bölebilirsiniz bir pencere. Bu bölme kullanıcı veya sabit bir boyuta göre yeniden boyutlandırılabilir olabilir.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Dosya yazdırma için standart bir iletişim kutusu sağlar.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Bir yazdırma ya da yazdırma önizleme işinin hakkında bilgi içeren bir yapıya. Tarafından kullanılan `CView`mimarisi yazdırmak.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Bulunan bir OLE istemci öğeleri listesini tutar bir `CRichEditView`.

[Cricheditcntrıtem](../mfc/reference/cricheditcntritem-class.md)<br/>
Öğesi içinde depolanan bir OLE istemci-tarafı erişim sağlayan bir `CRichEditView`.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
