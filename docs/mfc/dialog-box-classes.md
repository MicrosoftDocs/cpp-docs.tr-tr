---
title: İletişim Kutusu Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.dialog
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
ms.openlocfilehash: 3533a548f009a65462ce0d821d782db0ada9aa4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490017"
---
# <a name="dialog-box-classes"></a>İletişim Kutusu Sınıfları

Sınıf `CDialog` ve türetilmiş sınıflarının iletişim kutusu işlevselliğini kapsüller. Bir iletişim kutusu penceresinde, özel bir tür olduğundan `CDialog` türetilir `CWnd`. İletişim sınıflarından `CDialog` kullanın opening ya da dosya, yazdırma, yazı tipi veya renk seçme kaydetme gibi standart iletişim kutuları için genel iletişim kutusu sınıfları, arama ve değiştirme işlemi başlatılıyor veya çeşitli gerçekleştirme veya OLE ile ilgili işlemler.

[CDialog](../mfc/reference/cdialog-class.md)<br/>
Tüm iletişim kutularında, kalıcı ve kalıcı olmayan taban sınıf.

[CDataExchange](../mfc/reference/cdataexchange-class.md)<br/>
İletişim kutusu veri değişimi ve doğrulaması bilgilerini sağlar.

## <a name="common-dialogs"></a>Ortak iletişim kutuları

Bu iletişim kutusu sınıfları Windows ortak iletişim kutuları kapsüller. Bunlar, karmaşık iletişim kutularının kullanımı kolay uygulamalar sunar.

[CCommonDialog](../mfc/reference/ccommondialog-class.md)<br/>
Tüm ortak iletişim kutuları için temel sınıf.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Standart iletişim kutusunu açmak veya dosyayı kaydetmek için sağlar.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Bir renk seçmek için bir standart iletişim kutusu sağlar.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Standart iletişim kutusu, yazı tipi seçmek için sağlar.

[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)<br/>
Arama ve değiştirme işlemi için bir standart iletişim kutusu sağlar.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Dosya yazdırma için standart bir iletişim kutusu sağlar.

[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)<br/>
Bir Windows Print özellik sayfası sağlar.

[CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)<br/>
Ayar ve yazdırma kenar boşluklarını değiştirmek için ek destek içeren Windows ortak Sayfa Yapısı iletişim kutusu tarafından sağlanan hizmetleri kapsüller.

## <a name="ole-common-dialogs"></a>OLE ortak iletişim kutuları

OLE ortak iletişim kutuları çeşitli Windows için ekler. Bu sınıfların OLE ortak iletişim kutuları kapsüller.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
Tüm OLE iletişim kutuları için yaygın olarak görülen uygulamalar içeren için framework tarafından kullanılır. Kullanıcı arabirimi kategorideki tüm iletişim kutusu sınıfları bu temel sınıfından türetilir. `COleDialog` doğrudan kullanılamaz.

[Coleınsertdialog](../mfc/reference/coleinsertdialog-class.md)<br/>
Yeni OLE ekleme ya da bağlı öğeleri gömülü nesne Ekle iletişim kutusu, standart kullanıcı arabirimi görüntüler.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
Paste Special iletişim kutusu, Düzen Özel Yapıştır komut uygulamak için standart kullanıcı arabirimi görüntüler.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
Bağlantılı öğeler hakkındaki bilgileri değiştirmek için standart kullanıcı arabirimi Edit Links iletişim kutusu görüntüler.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
Change Icon iletişim kutusu, katıştırılmış bir OLE ile ilişkili simgeyi değiştirme veya bağlantılı öğe için standart kullanıcı arabirimi görüntüler.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
Dönüştür iletişim kutusu, standart kullanıcı arabirimi OLE öğelerine bir türden diğerine dönüştürme için görüntüler.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Windows ortak OLE Özellikleri iletişim kutusunu kapsüller. Ortak OLE Özellikleri iletişim kutusu görüntülemek ve bir OLE belge öğesi Windows standartları ile tutarlı şekilde özelliklerini değiştirmek için kolay bir yol sağlar.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
Güncelleştirme iletişim kutusunda, bir belgedeki tüm bağlantıların güncelleştirilmesi için standart kullanıcı arabirimi görüntüler. İletişim kutusu, güncelleştirme yordamı tamamlanana kadar ne kadar yakın olduğunu belirten bir İlerleme göstergesi içerir.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
Kaynağı Değiştir iletişim kutusu, bir bağlantının kaynak ve hedef değiştirmek için standart kullanıcı arabirimi görüntüler.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
Sunucu meşgul ve sunucu yanıt iletişim kutularında, meşgul uygulamaların çağrıları işlemek için standart kullanıcı arabirimi görüntüler. Genellikle tarafından otomatik olarak görüntülenen [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) uygulaması.

## <a name="property-sheet-classes"></a>Özellik sayfası sınıfları

Özellik sayfaları, olarak da bilinen sekmeli iletişim kutularını kullanmak, uygulamalarınızı özellik sayfası sınıfları sağlar. Özellik sayfaları, çok sayıda tek bir iletişim kutusu denetimleri düzenlemek için etkili bir yoludur.

[CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
Bir özellik sayfası içinde tek tek sayfaları sağlar. Öğesinden bir sınıf türetin `CPropertyPage` , özellik sayfasına eklenecek her sayfa için.

[CPropertySheet](../mfc/reference/cpropertysheet-class.md)<br/>
Birden çok özellik sayfaları için bir çerçeve sağlar. Özellik sayfası sınıfından türetilir `CPropertySheet` özelliği sayfalarınızı hızlı bir şekilde uygulamak için.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
İletişim kutusuna benzer bir grafik arabiriminde denetimi bir OLE özelliklerini görüntüler.

## <a name="html-based-dialog-classes"></a>HTML tabanlı iletişim kutusu sınıfları

[CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)<br/>
Kullanıcı arabirimini kaynaklarla iletişim yerine HTML kullanan iletişim kutuları oluşturmak için kullanılır.

[CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)<br/>
Birden çok HTML sayfasını sıralı olarak görüntüler ve her sayfadaki olayları işler.

## <a name="related-classes"></a>İlgili sınıflar

Bu sınıfların iletişim kutuları başına uzatılmasında değildir, ancak bunlar iletişim kutusu şablonları ve iletişim kutuları davranışını çoğunu sahip.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Bir iletişim kutusu şablonu temel alan bir denetim çubuğu.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Bir kaydırma görünümü, düzen bir iletişim kutusu şablonunda tanımlanır. Öğesinden bir sınıf türetin `CFormView` bir iletişim kutusu şablonu temel alan bir kullanıcı arabirimini uygulamak için.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Bir form sağlar doğrudan bir veri erişim nesnesi (DAO) kayıt nesnesine bağlıdır. Tüm form görünümleri gibi bir `CDaoRecordView` bir iletişim kutusu şablonu temel alan.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Bir form sağlar açık veritabanı bağlantısı (ODBC) kayıt nesneye doğrudan bağlı görünümü. Tüm form görünümleri gibi bir `CRecordView` bir iletişim kutusu şablonu temel alan.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Bir yazdırma ya da yazdırma önizleme işinin hakkında bilgi içeren bir yapıya. Yazdırma mimarisi tarafından kullanılan [CView](../mfc/reference/cview-class.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

