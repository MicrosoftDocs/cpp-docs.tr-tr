---
title: İletişim kutusu sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.dialog
dev_langs:
- C++
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d33289d8025d7cdcaf4f6f69062230730b958c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351696"
---
# <a name="dialog-box-classes"></a>İletişim Kutusu Sınıfları
Sınıf `CDialog` ve türetilmiş sınıflarının iletişim kutusu işlevleri kapsülleyen. Bir iletişim kutusu penceresinin özel bir tür olduğundan `CDialog` türetildiği `CWnd`. İletişim sınıflarından `CDialog` kullanın açma veya dosya, yazdırma, yazı tipi veya renk seçme kaydetme gibi standart iletişim kutuları için ortak iletişim kutusu sınıfları, bir arama ve değiştirme işlemi başlatılıyor veya çeşitli gerçekleştirme veya OLE ile ilgili işlemler.  
  
 [CDialog](../mfc/reference/cdialog-class.md)  
 Tüm iletişim kutularını, kalıcı ve kalıcı olmayan için temel sınıf.  
  
 [CDataExchange](../mfc/reference/cdataexchange-class.md)  
 İletişim kutusu veri değişimi ve doğrulaması bilgilerini sağlar.  
  
## <a name="common-dialogs"></a>Ortak iletişim kutuları  
 Bu iletişim kutusu sınıfları Windows ortak iletişim kutuları kapsüller. Karmaşık iletişim kutuları, kullanımı kolay uygulamalarını sağlarlar.  
  
 [CCommonDialog](../mfc/reference/ccommondialog-class.md)  
 Tüm ortak iletişim kutuları için temel sınıf.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Standart iletişim kutusu açılarak veya bir dosyayı kaydetmek için sağlar.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Bir renk seçmek için bir standart iletişim kutusu sağlar.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Standart iletişim kutusu, yazı tipi seçmek için sağlar.  
  
 [CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)  
 Standart iletişim kutusu için bir arama ve değiştirme işlemi sağlar.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Bir dosya yazdırma için bir standart iletişim kutusu sağlar.  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Bir Windows yazdırma özellik sayfası sağlar.  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 Ayar ve boşluklarının değiştirme için ek destek ile Windows ortak Sayfa Yapısı iletişim kutusu tarafından sağlanan hizmetlerin yalıtır.  
  
## <a name="ole-common-dialogs"></a>OLE ortak iletişim kutuları  
 OLE ortak iletişim kutuları birkaç Windows ekler. Bu sınıfların OLE ortak iletişim kutuları kapsüller.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Tüm OLE iletişim kutuları için ortak uygulamaları içerecek şekilde framework tarafından kullanıldı. Kullanıcı arabirimi kategorideki tüm iletişim kutusu sınıfları bu temel sınıfından türetilir. `COleDialog` doğrudan kullanılamaz.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Yeni OLE ekleme ya da bağlı öğeleri katıştırılmış nesne Ekle iletişim kutusu, standart kullanıcı arabirimi görüntüler.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Özel Yapıştır iletişim kutusu, Düzen Özel Yapıştır komut uygulamak için standart kullanıcı arabirimi görüntüler.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Bağlantılı öğeler hakkında bilgi değiştirmek için standart kullanıcı arabirimi Bağlantıları Düzenle iletişim kutusu görüntüler.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Simge Değiştir iletişim kutusu, bir OLE ile ilişkili simgeyi katıştırılmış değiştirme veya bağlantılı öğesi için standart kullanıcı arabirimi görüntüler.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Dönüştür iletişim kutusu, OLE öğeleri bir türden diğerine dönüştürme için standart kullanıcı arabirimi görüntüler.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Windows ortak OLE Özellikleri iletişim kutusu yalıtır. Ortak OLE Özellikleri iletişim kutusu görüntülemek ve OLE belge öğeyi Windows standartları ile tutarlı şekilde özelliklerini değiştirmek için kolay bir yol sağlar.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Güncelleştirme iletişim kutusunda, bir belgedeki tüm bağlantıların güncelleştirilmesi için standart kullanıcı arabirimi görüntüler. İletişim kutusu nasıl güncelleştirme yordamı tamamlanıncaya kadar yaklaştığını belirtmek için bir İlerleme göstergesi içerir.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Kaynağı Değiştir iletişim kutusu, bir bağlantının kaynak ve hedef değiştirmek için standart kullanıcı arabirimi görüntüler.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Sunucu meşgul ve sunucu yanıt iletişim kutularını, yoğun uygulamalar çağrıları işlemek için standart kullanıcı arabirimi görüntüler. Genellikle tarafından otomatik olarak görüntülenen [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) uygulaması.  
  
## <a name="property-sheet-classes"></a>Özellik sayfası sınıfları  
 Özellik sayfası sınıfları özellik sayfaları, olarak da bilinen sekmeli iletişim kutuları kullanmak, uygulamalarınızın izin verir. Özellik sayfaları, çok sayıda tek bir iletişim kutusu denetimleri düzenlemek için etkili bir yoludur.  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 Bir özellik sayfası içinde tek tek sayfaları sağlar. Öğesinden bir sınıf türetin `CPropertyPage` özellik sayfasına eklenecek her bir sayfa için.  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 Çerçevesi için birden çok özellik sayfaları sağlar. Özellik sayfası sınıfından türetilen `CPropertySheet` özellik sayfalarını hızlıca uygulamak için.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Bir iletişim kutusu için benzer bir grafik arabiriminde denetimi bir OLE özelliklerini görüntüler.  
  
## <a name="html-based-dialog-classes"></a>HTML tabanlı iletişim kutusu sınıfları  
 [CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)  
 Kendi kullanıcı arabirimini iletişim yerine HTML kaynaklarla iletişim kutuları oluşturmak için kullanılır.  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 Her bir sayfa olayları işler ve birden çok HTML sayfaları sıralı olarak görüntüler.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 Bu sınıfların iletişim kutuları başına uzatılmasında değildir, ancak bunlar iletişim kutusu şablonları kullanın ve iletişim kutuları davranışını çoğunu sahip.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Bir iletişim kutusu şablona dayalı bir denetim çubuğu.  
  
 [Cformview'yu](../mfc/reference/cformview-class.md)  
 Düzeni bir iletişim kutusu şablonda tanımlanan kaydırma görüntüleyin. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablona dayalı bir kullanıcı arabirimi uygulamak için.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Bir form sağlayan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablona dayalı.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Bir form sağlayan bir açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı Görünüm. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablona dayalı.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Yazdırın veya Önizleme işle ilgili bilgileri içeren bir yapısı. Yazdırma mimarisi tarafından kullanılan [CView](../mfc/reference/cview-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

