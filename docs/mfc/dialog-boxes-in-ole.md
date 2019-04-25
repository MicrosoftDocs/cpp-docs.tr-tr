---
title: OLE'deki İletişim Kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
ms.openlocfilehash: fa3d87e2cc17e297c3e6387920c6d527d8ddbe39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153417"
---
# <a name="dialog-boxes-in-ole"></a>OLE'deki İletişim Kutuları

Bir kullanıcı OLE etkinleştirilmiş bir uygulama çalışırken, uygulama kullanıcıdan bilgi işlemi gerçekleştirmek için gereken zamanı zamanlar vardır. MFC OLE sınıfları, gerekli bilgileri toplamak için iletişim kutularını çok sayıda sağlar. Bu konuda, OLE iletişim kutuları tarafından işlenen görevleri ve bu iletişim kutularını görüntülemek için gereken sınıfları listelenmiştir. OLE iletişim kutuları ve bunların davranışını özelleştirmek için kullanılan yapılar hakkında daha fazla bilgi için bkz: [MFC başvurusu](../mfc/mfc-desktop-applications.md).

*Nesne Ekle*<br/>
Bu iletişim kutusunda yeni oluşturulan ekleme veya mevcut nesneleri kullanıcının bileşik belgeye izin verir. Ayrıca, simge olarak öğe görüntülemeyi izin verir ve simge komut düğmesini etkinleştirir. Kullanıcı Nesne Ekle Düzenle Menüsü'nden seçtiğinde bu iletişim kutusunu görüntüleyin. Kullanım [Coleınsertdialog](../mfc/reference/coleinsertdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf. Kendi içine bir MDI uygulaması ekleyemeyeceğinizi unutmayın. Bir SDI uygulaması olmadığı sürece, bir kapsayıcı/sunucu olmayan bir uygulamanın kendi içine eklenemiyor.

*Özel Yapıştır*<br/>
Bu iletişim kutusu veri bileşik bir belgeye yapıştırırken kullanılan biçimi denetlemek kullanıcı sağlar. Kullanıcı, veri biçimi ekleyin ya da veri bağlantısı ve simge olarak görüntülenip görüntülenmeyeceğini seçebilirsiniz. Düzen menüsü'nden kullanıcı özel Yapıştır olarak seçtiğinde bu iletişim kutusunu görüntüleyin. Kullanım [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.

*Simge Değiştir*<br/>
Bu iletişim kutusu, kullanıcının simgeyi bağlantılı veya katıştırılmış bir öğeyi temsil etmek için görüntülenen seçmesine olanak sağlar. Kullanıcı Düzenle Menüsü'nden simge seçer veya simge düğme ya da Özel Yapıştır ve Dönüştürme iletişim kutularında seçer, bu iletişim kutusunu görüntüleyin. Ayrıca kullanıcı Nesne Ekle iletişim kutusu açılır ve simge olarak seçer görüntüleyin. Kullanım [Colechangeıcondialog](../mfc/reference/colechangeicondialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.

*Dönüştürme*<br/>
Bu iletişim kutusunu bir gömülü veya bağlantılı öğe türünü değiştirmesine izin verir. Örneğin, bir meta dosyası bir bileşik belgeye gömülü ve daha sonra başka bir uygulama, katıştırılmış meta değiştirmek için kullanmak istediğiniz, dönüştürme iletişim kutusunu kullanabilirsiniz. Bu iletişim kutusunu tıklatarak genellikle görüntülenen *öğesi türünü* dönüştürme tıklayarak nesne için düzenleme menüsünü ve ardından basamaklı menüsü. Kullanım [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf. Örneğin, MFC OLE örneği çalıştırmak [OCLIENT](../overview/visual-cpp-samples.md).

*Düzenleme bağlantıları veya bağlantıları güncelleştir*<br/>
Edit Links iletişim kutusu kaynağı bağlı nesnede hakkındaki bilgileri değiştirmesine izin verir. Güncelleştirme Links iletişim kutusu, geçerli iletişim kutusunu bağlı tüm öğelerin kaynakları doğrular ve gerekirse Edit Links iletişim kutusu görüntüler. Kullanıcı bağlantıları Düzenle Menüsü'nden seçtiğinde Edit Links iletişim kutusu görüntüler. Güncelleştirme Links iletişim kutusu, genellikle bir bileşik belge ilk kez açıldığında görüntülenir. Hangisini [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) veya [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) sınıfı, görüntülemek istediğiniz bağlı olarak hangi iletişim kutusu.

*Sunucu meşgul veya sunucu yanıt vermiyor*<br/>
Kullanıcı bir öğeyi etkinleştirmeyi dener ve sunucu isteği işlemek genellikle sunucunun olduğundan başka bir kullanıcı tarafından kullanımda veya görev şu anda işleyemiyor sunucu meşgul iletişim kutusu görüntülenir. Sunucu etkinleştirme isteği hiç yanıt vermezse, sunucunun yanıt vermemesine iletişim kutusu görüntülenir. Bu iletişim kutularından aracılığıyla görüntülenen `COleMessageFilter`OLE arabiriminin göre `IMessageFilter`, ve kullanıcı etkinleştirme isteği yeniden denemek karar verebilirsiniz. Kullanım [COleBusyDialog](../mfc/reference/colebusydialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE](../mfc/ole-in-mfc.md)
