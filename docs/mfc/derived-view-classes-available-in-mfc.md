---
title: MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 12b31074e4fcc2ed6a83e3669e1044f5b9caedab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373499"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları

Aşağıdaki tabloda MFC'nin görünüm sınıfları ve birbirleriyle olan ilişkileri gösterilmektedir. Görünüm sınıfınızın yetenekleri, türetildiği MFC görünüm sınıfına bağlıdır.

### <a name="view-classes"></a>Sınıfları Görüntüle

|Sınıf|Açıklama|
|-----------|-----------------|
|[Cview](../mfc/reference/cview-class.md)|Tüm görünümlerin taban sınıfı.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Taban sınıf `CTreeView` `CListView`, `CEditView`, `CRichEditView`, ve . Bu sınıflar, belirtilen Windows ortak denetimleri ile belge/görünüm mimarisini kullanmanıza izin verebilirsiniz.|
|[Ceditview](../mfc/reference/ceditview-class.md)|Windows edit kutusu denetimini temel alan basit bir görünüm. Metin girmenize ve düzenlemeye izin verir ve basit bir metin düzenleyicisi uygulaması için temel olarak kullanılabilir. Ayrıca `CRichEditView`bakınız.|
|[Cricheditview](../mfc/reference/cricheditview-class.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) nesnesi içeren bir görünüm. Bu `CEditView`sınıf, biçimlendirilmiş metni `CEditView` `CRichEditView` işler, ancak bunun aksine benzerdir.|
|[Clistview](../mfc/reference/clistview-class.md)|[CListCtrl](../mfc/reference/clistctrl-class.md) nesnesi içeren bir görünüm.|
|[CTreeView karşılaştırması](../mfc/reference/ctreeview-class.md)|Visual C++'daki Çözüm Gezgini penceresine benzeyen görünümler için [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesnesi içeren bir görünüm.|
|[Cscrollview](../mfc/reference/cscrollview-class.md)|Taban sınıf `CFormView` `CRecordView`, `CDaoRecordView`ve . Görünümün içeriğini kaydırmayı uygular.|
|[Cformview](../mfc/reference/cformview-class.md)|Form görünümü, denetimler içeren bir görünüm. Form tabanlı bir uygulama, bir veya daha fazla form arabirimi sağlar.|
|[Chtmlview](../mfc/reference/chtmlview-class.md)|Uygulamanın kullanıcısının World Wide Web'deki sitelere ve yerel dosya sistemindeki ve ağdaki klasörlere göz atabileceği bir Web tarayıcısı görünümü. Web tarayıcısı görünümü de Etkin belge kapsayıcısı olarak çalışabilir.|
|[Crecordview](../mfc/reference/crecordview-class.md)|Denetimlerde ODBC veritabanı kayıtlarını görüntüleyen bir form görünümü. Projenizde ODBC desteğini seçerseniz, görünümün taban `CRecordView`sınıfı . Görünüm bir `CRowset` nesneye bağlı.|
|[Cdaorecordview](../mfc/reference/cdaorecordview-class.md)|Denetimlerde DAO veritabanı kayıtlarını görüntüleyen bir form görünümü. Projenizde DAO desteğini seçerseniz, görünümün taban `CDaoRecordView`sınıfı . Görünüm bir `CDaoRecordset` nesneye bağlı.|
|[Coledbrecordview](../mfc/reference/coledbrecordview-class.md)|Denetimlerde OLE DB kayıtlarını görüntüleyen bir form görünümü. Projenizde OLE DB desteğini seçerseniz, görünümün taban `COleDBRecordView`sınıfı . Görünüm bir `CRowset` nesneye bağlı.|

> [!NOTE]
> MFC sürüm 4.0 `CEditView` itibariyle, `CCtrlView`türetilmiştir.

Uygulamanızda bu sınıfları kullanmak için, uygulamanın görünüm sınıflarını onlardan türetin. İlgili bilgiler için Bkz. [Kaydırma ve Ölçekleme Görünümleri.](../mfc/scrolling-and-scaling-views.md) Veritabanı sınıfları hakkında daha fazla bilgi için genel [bakış: Veritabanı Programlama.](../data/data-access-programming-mfc-atl.md)

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](../mfc/using-views.md)
