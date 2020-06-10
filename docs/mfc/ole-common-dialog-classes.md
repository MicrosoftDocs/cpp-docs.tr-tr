---
title: OLE Ortak İletişim Kutusu Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
ms.openlocfilehash: 1854d19c540f5e3e64b47786f465a05213eced86
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617787"
---
# <a name="ole-common-dialog-classes"></a>OLE Ortak İletişim Kutusu Sınıfları

Bu sınıflar, bir dizi standart OLE iletişim kutusu uygulayarak ortak OLE görevlerini işler. Ayrıca OLE işlevselliği için tutarlı bir kullanıcı arabirimi sağlar.

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
Meşgul uygulamalara yapılan çağrıları işlemeye yönelik standart Kullanıcı arabirimi olan sunucu meşgul ve sunucu yanıt vermiyor iletişim kutularını görüntüler. Genellikle uygulama tarafından otomatik olarak gösterilir `COleMessageFilter` .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
