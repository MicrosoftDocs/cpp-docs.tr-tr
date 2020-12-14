---
description: "Daha fazla bilgi edinin: MFC 'de kullanılabilen türetilmiş Görünüm sınıfları"
title: MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 669fb0f47cc2124fcf45d0eed3666869837f56f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211901"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları

Aşağıdaki tabloda, MFC 'nin Görünüm sınıfları ve bunların birbiriyle ilişkileri gösterilmektedir. Görünüm sınıfınızın özellikleri, türetildiği MFC görünüm sınıfına bağlıdır.

### <a name="view-classes"></a>Sınıfları görüntüle

|Sınıf|Açıklama|
|-----------|-----------------|
|[CView](reference/cview-class.md)|Tüm görünümlerin temel sınıfı.|
|[CCtrlView](reference/cctrlview-class.md)|`CTreeView`,, Ve temel `CListView` sınıfı `CEditView` `CRichEditView` . Bu sınıflar, belirtilen Windows ortak denetimleriyle belge/görünüm mimarisini kullanmanıza olanak sağlar.|
|[CEditView](reference/ceditview-class.md)|Windows düzenleme kutusu denetimine dayalı basit bir görünüm. Metnin girilmesine ve düzenlenmesine izin verir ve basit bir metin Düzenleyicisi uygulamasının temeli olarak kullanılabilir. Ayrıca bkz `CRichEditView` ..|
|[CRichEditView](reference/cricheditview-class.md)|[CRichEditCtrl](reference/cricheditctrl-class.md) nesnesini içeren bir görünüm. Bu sınıf, olarak benzerdir `CEditView` , ancak aksine `CEditView` , `CRichEditView` biçimlendirilen metni işler.|
|[CListView](reference/clistview-class.md)|[CListCtrl](reference/clistctrl-class.md) nesnesini içeren bir görünüm.|
|[CTreeView karşılaştırması](reference/ctreeview-class.md)|Visual C++ Çözüm Gezgini pencereye benzeyen görünümler için [Ctreecu](reference/ctreectrl-class.md) nesnesi içeren bir görünüm.|
|[CScrollView](reference/cscrollview-class.md)|`CFormView`, Ve temel sınıfı `CRecordView` `CDaoRecordView` . Görünümün içeriğini kaydırmayı uygular.|
|[CFormView](reference/cformview-class.md)|Denetimleri içeren bir görünüm olan form görünümü. Form tabanlı bir uygulama, bir veya daha fazla form arabirimi sağlar.|
|[CHtmlView](reference/chtmlview-class.md)|Uygulamanın kullanıcısının World Wide Web sitelere ve yerel dosya sisteminde ve bir ağdaki klasörlere gözatabildiği bir Web tarayıcısı görünümü. Web tarayıcısı görünümü Ayrıca etkin bir belge kapsayıcısı olarak da çalışabilir.|
|[CRecordView](reference/crecordview-class.md)|Denetimlerde ODBC veritabanı kayıtlarını görüntüleyen bir form görünümü. Projenizde ODBC desteği ' ni seçerseniz, görünümün temel sınıfı olur `CRecordView` . Görünüm bir `CRowset` nesnesine bağlıdır.|
|[CDaoRecordView](reference/cdaorecordview-class.md)|Denetimlerde DAO veritabanı kayıtlarını görüntüleyen bir form görünümü. Projenizde DAO desteği ' ni seçerseniz, görünümün temel sınıfı olur `CDaoRecordView` . Görünüm bir `CDaoRecordset` nesnesine bağlıdır.|
|[COleDBRecordView](reference/coledbrecordview-class.md)|Denetimlerde OLE DB kayıtları görüntüleyen bir form görünümü. Projenizde OLE DB desteği ' ni seçerseniz, görünümün temel sınıfı olur `COleDBRecordView` . Görünüm bir `CRowset` nesnesine bağlıdır.|

> [!NOTE]
> MFC sürüm 4,0 itibariyle, `CEditView` öğesinden türetilir `CCtrlView` .

Uygulamanızda bu sınıfları kullanmak için uygulamanın görünüm sınıflarını türetirsiniz. İlgili bilgiler için bkz. [görünümleri kaydırma ve ölçeklendirme](scrolling-and-scaling-views.md). Veritabanı sınıfları hakkında daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../data/data-access-programming-mfc-atl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri kullanma](using-views.md)
