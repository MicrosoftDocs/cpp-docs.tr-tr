---
title: OLE iletişim kutuları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fdff45963419b3676ea8ca6b1bf0239348387dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347847"
---
# <a name="dialog-boxes-in-ole"></a>OLE'deki İletişim Kutuları
Bir kullanıcı OLE etkinleştirilmiş bir uygulama çalışırken, uygulama kullanıcıdan bilgi alma işlemi gerçekleştirmek için gerektiği zaman zamanlar vardır. MFC OLE sınıfları gerekli bilgileri toplamak için iletişim kutularında çok sayıda sağlar. Bu konu, OLE iletişim kutuları tarafından işlenen görevleri ve bu iletişim kutusu görüntülemek için gereken sınıfları listeler. OLE iletişim kutuları ve bunların davranışını özelleştirmek için kullanılan yapılar hakkında daha fazla bilgi için bkz: [MFC başvurusu](../mfc/mfc-desktop-applications.md).  
  
 *Nesne Ekle*  
 Bu iletişim kutusu, yeni oluşturulan ekleme veya varolan nesneleri kullanıcıya bileşik belgeye sağlar. Ayrıca bir simge olarak öğe görüntülemeyi olanak tanır ve simge komut düğmesi sağlar. Kullanıcı düzenleme menüsünden Nesne Ekle seçtiğinde bu iletişim kutusunu görüntüleyin. Kullanım [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf. Kendi içine bir MDI uygulama ekleyemiyor unutmayın. SDI uygulama olmadığı sürece bir kapsayıcı/sunucu uygulamanın kendi içine eklenemez.  
  
 *Özel Yapıştır*  
 Bu iletişim kutusu kullanıcının verileri bileşik bir belgeye yapıştırılırken kullanılan biçimi denetlemesine olanak sağlar. Kullanıcı veri biçimi, ekleme ya da veri bağlantısı ve simge olarak görüntülenip görüntülenmeyeceğini seçebilirsiniz. Düzen menüsünden kullanıcı özel Yapıştır olarak seçtiğinde bu iletişim kutusunu görüntüleyin. Kullanım [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.  
  
 *Simge Değiştir*  
 Bu iletişim kutusu kullanıcının hangi simgesi bağlantılı veya katıştırılmış öğeyi temsil edecek görüntülenir seçmesine olanak sağlar. Kullanıcı düzenleme menüsünden değişikliği simgesi seçer ya da Özel Yapıştır veya Dönüştür iletişim kutuları Simge Değiştir düğmesini seçer bu iletişim kutusunu görüntüleyin. Ayrıca kullanıcı Nesne Ekle iletişim kutusu açılır ve simge olarak seçtiği görüntüleyin. Kullanım [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.  
  
 *Dönüştür*  
 Bu iletişim kutusu kullanıcıya katıştırılmış veya bağlantılı bir öğe türü değiştirme olanağı sağlar. Örneğin, bir meta dosyası bileşik bir belgede katıştırılmış ve daha sonra katıştırılmış meta dosyası değiştirmek için başka bir uygulama kullanmak istiyorsanız, dönüştürme iletişim kutusunu kullanabilirsiniz. Bu iletişim kutusunu tıklatarak genellikle görüntülenen *öğesi türünü* Düzen menüsünde ve daha sonra geçişli menüsünde dönüştürme tıklayarak nesnesi. Kullanım [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) bu iletişim kutusunu görüntülemek için sınıf. Örneğin, MFC OLE örneği çalıştırmak [OCLIENT](../visual-cpp-samples.md).  
  
 *Düzenleme bağlantıları veya bağlantıları güncelleştir*  
 Bağlantılı nesne kaynağı ile ilgili bilgileri değiştirmek kullanıcı bağlantıları Düzenle iletişim kutusu sağlar. Güncelleştirme bağlantıları iletişim kutusu geçerli iletişim kutusundaki tüm bağlantılı öğeler kaynakları doğrular ve gerekirse Bağlantıları Düzenle iletişim kutusu görüntüler. Kullanıcı düzenleme menüsünden bağlantılar seçtiğinde Bağlantıları Düzenle iletişim kutusunu görüntüleyin. Bileşik belge ilk kez açıldığında bağlantıları güncelleştir iletişim kutusu genellikle görüntülenir. Kullanın ya da [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) veya [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) sınıfı, görüntülemek istediğiniz bağlı olarak hangi iletişim kutusu.  
  
 *Sunucu meşgul veya sunucu yanıt vermiyor*  
 Sunucu meşgul iletişim kutusu, kullanıcı bir öğeyi etkinleştirme girişiminde ve sunucusu isteği işlemek için genellikle sunucunun olduğundan başka bir kullanıcı tarafından kullanımda veya görev şu anda işleyemiyor görüntülenir. Sunucuyu etkinleştirme isteği için hiç yanıt vermiyorsa sunucusu yanıt vermiyor iletişim kutusu görüntülenir. Bu iletişim kutularından aracılığıyla görüntülenen `COleMessageFilter`bağlı OLE arabirimi uygulaması olarak **ı**, ve kullanıcı etkinleştirme isteği yeniden denemek karar verebilirsiniz. Kullanım [COleBusyDialog](../mfc/reference/colebusydialog-class.md) bu iletişim kutusunu görüntülemek için sınıf.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE](../mfc/ole-in-mfc.md)

