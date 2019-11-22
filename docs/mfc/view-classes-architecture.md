---
title: Görünüm Sınıfları (Mimari)
ms.date: 09/17/2019
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
ms.openlocfilehash: fda4e968a4761fcf1e2245964bd5dca3f41a82ad
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74302983"
---
# <a name="view-classes-architecture"></a>Görünüm Sınıfları (Mimari)

`CView` ve türetilmiş sınıfları, bir çerçeve penceresinin istemci alanını temsil eden alt Windows 'lardır. Görünümler, verileri gösterir ve bir belge için girişi kabul eder.

Bir görünüm sınıfı bir belge sınıfı ve bir belge şablonu nesnesi kullanan bir çerçeve pencere sınıfı ile ilişkilendirilir.

[CView](../mfc/reference/cview-class.md)<br/>
Belge verilerinin uygulamaya özgü görünümleri için temel sınıf. Görünümler verileri görüntüler ve verileri düzenlemek veya seçmek için Kullanıcı girişini kabul eder. `CView`görünüm sınıfınızı türetirsiniz.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Kaydırma özelliklerine sahip görünümler için temel sınıf. Otomatik kaydırma için `CScrollView` görünüm sınıfınızı türetirsiniz.

## <a name="form-and-record-views"></a>Form ve kayıt görünümleri

Form görünümleri Ayrıca görünümleri de kaydırmalıdır. Bunlar bir iletişim kutusu şablonunu temel alır.

Kayıt görünümleri form görünümlerinden türetilir. İletişim kutusu şablonuna ek olarak, bir veritabanı bağlantısı da vardır.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Bir iletişim kutusu şablonunda düzeni tanımlanan bir kaydırma görünümü. Bir iletişim kutusu şablonuna dayalı kullanıcı arabirimini uygulamak için `CFormView` bir sınıf türetebilirsiniz.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Doğrudan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CDaoRecordView` iletişim kutusu şablonunu temel alır. DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Bir uygulama içinde Web 'e göz atma denetimini destekler. Denetim MFC 'de dinamik HTML 'yi destekler.

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
Form görünümleri için MFC OLE DB desteği sağlar.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CRecordView` iletişim kutusu şablonunu temel alır.

## <a name="control-views"></a>Denetim görünümleri

Denetim görünümleri görünüm olarak bir denetim görüntüler.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows denetimleriyle ilişkili tüm görünümlerin temel sınıfı. Denetimleri temel alan görünümler aşağıda açıklanmıştır.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Windows standart düzenleme denetimi içeren bir görünüm (bkz. [Cedıt](../mfc/reference/cedit-class.md)). Düzenleme denetimleri, metin düzenleme, arama, değiştirme ve kaydırma özelliklerini destekler.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Windows zengin düzenleme denetimi içeren bir görünüm (bkz. [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzenleme denetiminin özelliklerine ek olarak, zengin düzenleme denetimleri yazı tiplerini, renkleri, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerini destekler.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünüm (bkz. [Clienstctrl](../mfc/reference/clistctrl-class.md)). Liste denetimi, simgeleri ve dizeleri dosya Gezgini 'nin sağ bölmesine benzer şekilde görüntüler.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Windows ağaç denetimi içeren bir görünüm (bkz. [Ctreeci](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi, dosya Gezgini 'nin sol bölmesine benzer şekilde hiyerarşide düzenlenmiş simgeleri ve dizeleri görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
