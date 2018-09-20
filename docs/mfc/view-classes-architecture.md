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
ms.openlocfilehash: 12987a7563b685018de64201d60d0447d3a5d4cc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393827"
---
# <a name="view-classes-architecture"></a>Görünüm Sınıfları (Mimari)

`CView` ve türetilmiş sınıflarının bir çerçeve penceresinin istemci alanını temsil eden alt pencereler. Görünümleri, verileri gösterme ve bir belge için giriş kabul edin.

View sınıfı, bir belge şablonu nesnesi kullanılarak bir çerçeve penceresi sınıfı ve belge sınıfı ile ilişkilidir.

[CView](../mfc/reference/cview-class.md)<br/>
Bir belgenin verilerinin uygulamaya özgü görünümler için temel sınıf. Görünümler, verileri görüntülemek ve düzenlemek veya verileri seçmek için kullanıcı girişi kabul edin. Görünüm sınıfları öğesinden türetilen `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Görünümleri kaydırma özelliğine sahip bir temel sınıf. Görünüm sınıfından türetilir `CScrollView` otomatik kaydırmayı.

## <a name="form-and-record-views"></a>Form ve kayıt görünümleri

Form görünümleri, ayrıca görünümleri kaydırma. Bunlar bir iletişim kutusu şablonunu temel alır.

Kayıt görünümleri form görünümleri türetilir. İletişim kutusu şablonu yanı sıra, ayrıca bir veritabanına bir bağlantı sahiptirler.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Bir kaydırma görünümü, düzen bir iletişim kutusu şablonunda tanımlanır. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablonu temel alan bir kullanıcı arabirimini uygulamak için.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Bir form sağlar doğrudan bir veri erişim nesnesi (DAO) kayıt nesnesine bağlıdır. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablonu temel alan.

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Bir uygulamadaki Web'e göz atmak için bir denetimi destekler. Denetim dinamik HTML MFC'de destekler.

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
Form görünümleri için MFC OLE DB desteği sağlar.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Bir form sağlar açık veritabanı bağlantısı (ODBC) kayıt nesneye doğrudan bağlı görünümü. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablonu temel alan.

## <a name="control-views"></a>Denetim görünümleri

Denetim görünümleri, görünüm olarak bir denetim görüntüler.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows denetimleri ile ilgili tüm görünümleri için temel sınıf. Denetimlerine göre görünümleri aşağıda açıklanmıştır.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bir Windows standart içeren bir görünümü düzenleme denetimi (bkz [CEdit](../mfc/reference/cedit-class.md)). Metin denetimleri düzenleme desteği, arama, değiştirme ve kaydırma düzenleyin.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Zengin bir Windows içeren bir görünümü düzenleme denetimi (bkz [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir düzenleme denetimi özelliklere ek olarak, denetimleri destek yazı tiplerini, renkleri, paragraf biçimlendirmesini ve katıştırılmış OLE nesnelerine zengin düzenleme.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünümü (bkz [CListCtrl](../mfc/reference/clistctrl-class.md)). Liste denetimi, dosya Gezgini içinde sağ bölmeye benzer şekilde simgeleri ve dizeleri görüntüler.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Bir Windows ağaç denetimi içeren bir görünümü (bkz [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ağaç denetimi, simgeler ve dosya Gezgini'nin sol bölmeye benzer şekilde, bir hiyerarşideki düzenlenmiş dizeleri görüntüler.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

