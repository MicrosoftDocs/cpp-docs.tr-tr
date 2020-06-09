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
ms.openlocfilehash: 2399b27fc081dcc810277079729b0e62ef80d603
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616946"
---
# <a name="dialog-box-classes"></a>İletişim Kutusu Sınıfları

Sınıf `CDialog` ve türetilmiş sınıfları iletişim kutusu işlevselliğini Kapsüller. İletişim kutusu özel bir pencere türü olduğundan, `CDialog` öğesinden türetilir `CWnd` . İletişim kutusu sınıflarınızı bir `CDialog` dosya açma veya kaydetme, yazdırma, yazı tipi veya renk seçme, bir arama ve değiştirme işlemini başlatma veya OLE ile ilgili çeşitli işlemleri gerçekleştirme gibi standart iletişim kutuları için ortak iletişim kutusu sınıflarından birini kullanın veya kullanın.

[CDialog](reference/cdialog-class.md)<br/>
Tüm iletişim kutuları için hem kalıcı hem de kalıcı olmayan temel sınıf.

[CDataExchange](reference/cdataexchange-class.md)<br/>
İletişim kutuları için veri değişimi ve doğrulama bilgilerini sağlar.

## <a name="common-dialogs"></a>Ortak Iletişim kutuları

Bu iletişim kutusu sınıfları Windows ortak iletişim kutularını kapsülle. Bunlar karmaşık iletişim kutularının kullanımı kolay uygulamalarını sağlar.

[Ccommoniletişim kutusu](reference/ccommondialog-class.md)<br/>
Tüm ortak iletişim kutuları için temel sınıf.

[CFileDialog](reference/cfiledialog-class.md)<br/>
Dosya açmak veya kaydetmek için standart bir iletişim kutusu sağlar.

[CColorDialog](reference/ccolordialog-class.md)<br/>
Renk seçmek için standart bir iletişim kutusu sağlar.

[CFontDialog](reference/cfontdialog-class.md)<br/>
Yazı tipi seçmek için standart bir iletişim kutusu sağlar.

[CFindReplaceDialog](reference/cfindreplacedialog-class.md)<br/>
Arama ve değiştirme işlemi için standart bir iletişim kutusu sağlar.

[CPrintDialog](reference/cprintdialog-class.md)<br/>
Dosya yazdırmak için standart bir iletişim kutusu sağlar.

[CPrintDialogEx](reference/cprintdialogex-class.md)<br/>
Bir Windows yazdırma özelliği sayfası sağlar.

[CPageSetupDialog](reference/cpagesetupdialog-class.md)<br/>
Windows ortak sayfa kurulumu iletişim kutusu tarafından sunulan hizmetleri, yazdırma kenar boşluklarını ayarlama ve değiştirme ile ilgili ek destek ile kapsüller.

## <a name="ole-common-dialogs"></a>OLE ortak Iletişim kutuları

OLE, Windows 'a birkaç ortak iletişim kutusu ekler. Bu sınıflar OLE ortak iletişim kutularını kapsülleme.

[Colet Iletişim kutusu](reference/coledialog-class.md)<br/>
Framework tarafından tüm OLE iletişim kutuları için ortak uygulamaları içerecek şekilde kullanılır. Kullanıcı arabirimi kategorisindeki tüm iletişim kutusu sınıfları bu temel sınıftan türetilir. `COleDialog`doğrudan kullanılamaz.

[COleInsertDialog](reference/coleinsertdialog-class.md)<br/>
Yeni OLE bağlantılı veya katıştırılmış öğeleri eklemek için standart Kullanıcı arabirimi olan nesne Ekle iletişim kutusunu görüntüler.

[COlePasteSpecialDialog](reference/colepastespecialdialog-class.md)<br/>
Özel Yapıştır iletişim kutusunu, düzenleme Özel Yapıştır komutunu uygulamak için standart Kullanıcı arabirimini görüntüler.

[Cotalinksdialog](reference/colelinksdialog-class.md)<br/>
Bağlantılı öğelerle ilgili bilgileri değiştirmek için standart Kullanıcı arabirimi olan bağlantıları Düzenle iletişim kutusunu görüntüler.

[COleChangeIconDialog](reference/colechangeicondialog-class.md)<br/>
OLE Embedded veya bağlantılı öğeyle ilişkili simgeyi değiştirmek için standart Kullanıcı arabirimi olan simge Değiştir iletişim kutusunu görüntüler.

[Cotaconvertdialog](reference/coleconvertdialog-class.md)<br/>
OLE öğelerini bir türden diğerine dönüştürmek için standart Kullanıcı arabirimi olan Dönüştür iletişim kutusunu görüntüler.

[Cotapropertiesiletişim kutusu](reference/colepropertiesdialog-class.md)<br/>
Windows ortak OLE özellikleri iletişim kutusunu kapsüller. Ortak OLE özellikleri iletişim kutuları, bir OLE belge öğesinin özelliklerini Windows standartlarıyla tutarlı bir şekilde görüntülemenin ve değiştiremenin kolay bir yolunu sunar.

[Cotaupdatedialog](reference/coleupdatedialog-class.md)<br/>
Belgedeki tüm bağlantıları güncelleştirmek için standart Kullanıcı arabirimi olan Güncelleştir iletişim kutusunu görüntüler. İletişim kutusu, güncelleştirme yordamının tamamlanmasını nasıl kapatabelirten bir ilerleme göstergesi içerir.

[Colet Changesourcedialog](reference/colechangesourcedialog-class.md)<br/>
Bir bağlantının hedefini veya kaynağını değiştirmek için standart Kullanıcı arabirimi olan kaynak Değiştir iletişim kutusunu görüntüler.

[Cotabusi Iletişim kutusu](reference/colebusydialog-class.md)<br/>
Meşgul uygulamalara yapılan çağrıları işlemeye yönelik standart Kullanıcı arabirimi olan sunucu meşgul ve sunucu yanıt vermiyor iletişim kutularını görüntüler. Genellikle [COleMessageFilter](reference/colemessagefilter-class.md) uygulamasıyla otomatik olarak gösterilir.

## <a name="property-sheet-classes"></a>Özellik sayfası sınıfları

Özellik sayfası sınıfları, uygulamalarınızın sekmeli iletişim kutuları olarak da bilinen özellik sayfalarını kullanmasına izin verir. Özellik sayfaları, tek bir iletişim kutusunda çok sayıda denetimi düzenlemenin etkili bir yoludur.

[CPropertyPage](reference/cpropertypage-class.md)<br/>
Bir özellik sayfası içinde ayrı sayfalar sağlar. `CPropertyPage`Özellik sayfanıza eklenecek her sayfa için bir sınıf türetirsiniz.

[CPropertySheet](reference/cpropertysheet-class.md)<br/>
Birden çok özellik sayfası için çerçeve sağlar. Özellik `CPropertySheet` sayfalarınızı hızlı bir şekilde uygulamak için özellik sayfası sınıfınızı öğesinden türetirsiniz.

[COlePropertyPage](reference/colepropertypage-class.md)<br/>
Bir OLE denetiminin özelliklerini bir iletişim kutusuna benzer şekilde bir grafik arabirimde görüntüler.

## <a name="html-based-dialog-classes"></a>HTML tabanlı Iletişim sınıfları

[CDHtmlDialog](reference/cdhtmldialog-class.md)<br/>
Kullanıcı arayüzünü iletişim kutusu kaynakları yerine HTML ile uygulayan iletişim kutuları oluşturmak için kullanılır.

[CMultiPageDHtmlDialog](reference/cmultipagedhtmldialog-class.md)<br/>
Birden çok HTML sayfasını ardışık olarak görüntüler ve her sayfadaki olayları işler.

## <a name="related-classes"></a>İlgili sınıflar

Bu sınıflar, tek başına iletişim kutusu değildir, ancak iletişim kutusu şablonlarını kullanır ve iletişim kutularının davranışlarının büyük bir bölümünü kullanır.

[CDialogBar](reference/cdialogbar-class.md)<br/>
İletişim kutusu şablonunu temel alan bir denetim çubuğu.

[CFormView](reference/cformview-class.md)<br/>
Bir iletişim kutusu şablonunda düzeni tanımlanan bir kaydırma görünümü. Bir `CFormView` iletişim kutusu şablonunu temel alan bir kullanıcı arabirimi uygulamak için öğesinden bir sınıf türetebilirsiniz.

[CDaoRecordView](reference/cdaorecordview-class.md)<br/>
Doğrudan bir veri erişim nesnesi (DAO) kayıt kümesi nesnesine bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CDaoRecordView` iletişim kutusu şablonunu temel alır.

[CRecordView](reference/crecordview-class.md)<br/>
Açık veritabanı bağlantısı (ODBC) kayıt kümesi nesnesine doğrudan bağlı bir form görünümü sağlar. Tüm form görünümleri gibi, bir `CRecordView` iletişim kutusu şablonunu temel alır.

[CPrintInfo](reference/cprintinfo-structure.md)<br/>
Yazdırma veya baskı önizleme işi hakkında bilgi içeren bir yapı. [CView](reference/cview-class.md)'ın yazdırma mimarisi tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
