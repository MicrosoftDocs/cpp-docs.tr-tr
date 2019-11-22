---
title: Görünüm Sınıfları (Windows)
ms.date: 09/17/2019
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: a3e0f837bc13c022bec91bfff6e38c1513abaf16
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74302971"
---
# <a name="view-classes-windows"></a>Görünüm Sınıfları (Windows)

`CView` ve türetilmiş sınıfları, bir çerçeve penceresinin istemci alanını temsil eden alt Windows 'lardır. Görünümler, verileri gösterir ve bir belge için girişi kabul eder.

Bir görünüm sınıfı bir belge sınıfı ve bir belge şablonu nesnesi kullanan bir çerçeve pencere sınıfı ile ilişkilendirilir.

[CView](../mfc/reference/cview-class.md)<br/>
Belge verilerinin uygulamaya özgü görünümleri için temel sınıf. Görünümler verileri görüntüler ve verileri düzenlemek veya seçmek için Kullanıcı girişini kabul eder. Görünüm sınıfınızı veya sınıflarınızı `CView`türetebilirsiniz.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Kaydırma özelliklerine sahip görünümler için temel sınıf. Otomatik kaydırma için `CScrollView` görünüm sınıfınızı türetirsiniz.

## <a name="form-and-record-views"></a>Form ve kayıt görünümleri

Form görünümleri Ayrıca görünümleri de kaydırmalıdır. Bunlar bir iletişim kutusu şablonunu temel alır.

Kayıt görünümleri form görünümlerinden türetilir. İletişim kutusu şablonuna ek olarak, bir veritabanı bağlantısı da vardır.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Bir iletişim kutusu şablonunda düzeni tanımlanan bir kaydırma görünümü. Bir iletişim kutusu şablonuna dayalı kullanıcı arabirimini uygulamak için `CFormView` bir sınıf türetebilirsiniz.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Doğrudan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CDaoRecordView` iletişim kutusu şablonunu temel alır. DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CRecordView` iletişim kutusu şablonunu temel alır.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
WebBrowser HTML düzenlemesi platformunun işlevlerini sağlayan bir form görünümü.

## <a name="control-views"></a>Denetim görünümleri

Denetim görünümleri görünüm olarak bir denetim görüntüler.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows denetimleriyle ilişkili tüm görünümlerin temel sınıfı. Denetimleri temel alan görünümler aşağıda açıklanmıştır.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Windows standart düzenleme denetimi içeren bir görünüm (bkz. [Cedıt](../mfc/reference/cedit-class.md)). Düzenleme denetimleri, metin düzenleme, arama, değiştirme ve kaydırma özelliklerini destekler.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Windows zengin düzenleme denetimi içeren bir görünüm (bkz. [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzenleme denetiminin özelliklerine ek olarak, zengin düzenleme denetimleri yazı tiplerini, renkleri, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerini destekler.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünüm (bkz. [Clienstctrl](../mfc/reference/clistctrl-class.md)). Liste denetimi, dosya Gezgini 'nin sağ bölmesine benzer şekilde, her biri bir simge ve etiketten oluşan öğelerin koleksiyonunu görüntüler.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Windows ağaç denetimi içeren bir görünüm (bkz. [Ctreeci](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi, dosya Gezgini 'nin sol bölmesine benzer şekilde düzenlenmiş simge ve etiketlerin hiyerarşik bir listesini görüntüler.

## <a name="related-classes"></a>İlgili sınıflar

`CSplitterWnd`, tek bir çerçeve penceresi içinde birden çok görünümizin sağlar. `CPrintDialog` ve `CPrintInfo` görünümlerin yazdırma ve baskı önizleme özelliğini destekler. `CRichEditDoc` ve `CRichEditCntrItem` OLE kapsayıcı özelliklerini uygulamak için `CRichEditView` ile birlikte kullanılır.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
Kullanıcının birden çok bölmeye bölüneceği bir pencere. Bu bölmeler Kullanıcı veya sabit boyuta göre yeniden boyutlandırılabilir.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Dosya yazdırmak için standart bir iletişim kutusu sağlar.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Yazdırma veya baskı önizleme işi hakkında bilgi içeren bir yapı. `CView`yazdırma mimarisi tarafından kullanılır.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
`CRichEditView`olan OLE istemci öğelerinin listesini tutar.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
`CRichEditView`depolanan bir OLE öğesine istemci tarafı erişimi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
