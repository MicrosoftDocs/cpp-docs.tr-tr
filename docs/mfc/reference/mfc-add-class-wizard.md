---
title: MFC Sınıf Ekleme Sihirbazı
ms.date: 09/06/2019
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
ms.openlocfilehash: 2c82e084de2123c579299ca6490bdfcfdac5d255
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908024"
---
# <a name="mfc-add-class-wizard"></a>MFC Sınıf Ekleme Sihirbazı

Varolan bir MFC projesine bir sınıf eklemek veya bir ATL projesine MFC 'yi destekleyen bir sınıf eklemek için bu kod Sihirbazı 'nı kullanın. MFC desteği olan Win32 projelerine MFC sınıfları da ekleyebilirsiniz. Projenizi oluştururken belirttiğiniz özellikler, bu iletişim kutusunda kullanılabilen seçenekleri belirlenir. Sihirbaza erişmek için sınıf **ekleme** [Sihirbazı](mfc-class-wizard.md)' na tıklayın.

![MFC sınıfı ekleme Sihirbazı](media/add-mfc-class-wizard.png "MFC sınıfı ekleme Sihirbazı")

## <a name="names"></a>Adlar

Bu sayfada, sınıf adını, Taban sınıfını ve yeni sınıf için dosya adlarını belirtin.

- **Sınıf adı**

  Yeni sınıfın adını belirtir ve bu sayfadaki kimlik ve dosya adları için varsayılan temeli sağlar. C++sınıflar genellikle "C" ile başlar, örneğin "CMyClass", "MyClass. h" olur ve bu şekilde devam eder.

- **Temel sınıf**

  Yeni sınıf için temel sınıfın adını belirtir. Varsayılan olarak, temel sınıf [CWnd](../../mfc/reference/cwnd-class.md)' dir. Seçtiğiniz temel sınıf, bu sayfadaki diğer kutuların etkin olup olmadığını belirler.

  Temel sınıf olarak ayarladığınız sınıfın türü, sınıfın bir iletişim kutusu KIMLIĞI mi yoksa kaynak KIMLIĞI mi olduğunu belirler. Genel sınıf türleri şunlardır:

  - Bir iletişim kutusu KIMLIĞI veya kaynak KIMLIĞI gerektirmeyen [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md)veya [CDocument](../../mfc/reference/cdocument-class.md)gibi sınıflar. Bu sınıflar bir iletişim kutusu veya kaynak KIMLIĞI kullanmaz. Taban sınıfınız için bu sınıflardan birini seçerseniz, **iletişim kutusu kimliği** ve **DHTML kaynak kimliği** kutusu soluk kalır.

  - Bir iletişim KIMLIĞI gerektiren [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md)veya [CPropertyPage](../../mfc/reference/cpropertypage-class.md)gibi sınıflar.

  - Bir iletişim kutusu KIMLIĞI, bir DHTML kaynak KIMLIĞI ve bir HTML dosya adı gerektiren [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)sınıfı.

  İletişim kutusu KIMLIĞI gerektiren sınıflar için, [kaynak Düzenleyicisi](../../windows/resource-editors.md) 'ni kullanarak iletişim kaynağı oluşturma, kimliğini [sınıf Sihirbazı](mfc-class-wizard.md)'nda atama ve ardından bu kaynak kimliğiyle ilişkili bir sınıf oluşturma daha verimli bulabilirsiniz. Standart bir Windows iletişim kutusu oluşturma hakkında daha fazla bilgi için bkz. [Yeni Iletişim kutusu oluşturma](../../windows/creating-a-new-dialog-box.md) .

  > [!NOTE]
  > Önce bir iletişim kutusu kaynağı oluşturup yeni sınıfını öğesinden `CDHtmlDialog`türetirsiniz, varsayılan iletişim kutusunda görüntülenen standart Windows **Tamam** ve **iptal** düğmelerini silin. Standart Windows iletişim kutusu, kendi **Tamam** ve **Iptal** düğmelerini içeren DHTML formunu barındırır.

  İletişim kutusu hem Windows denetimleri hem de DHTML denetimleri içerdiğinde, önerilmez.

- **İletişim kutusu KIMLIĞI**

  `CDialog`,, Veya `CPropertyPage` `CFormView` öğesini`CDHtmlDialog` **temel sınıf**olarak seçtiyseniz, iletişim kutusunun kimliğini belirtir.

- **. h dosyası**

  Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **sınıf adı**' nda sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

  Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **. cpp dosyası**

  Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **sınıf adı**' nda sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

  Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **Etkin Erişilebilirlik**

  Oluşturucuda [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) ÇAĞıRARAK, MFC 'Nin Etkin Erişilebilirlik desteğini sunar. Bu seçenek, [CWnd](../../mfc/reference/cwnd-class.md)'den türetilmiş sınıflar için kullanılabilir.

- **Otomatikleştirme**

  [Otomasyon](../../mfc/automation.md)için destek sınıfı düzeyini ayarlar. Sınıf düzeyinde Otomasyon, otomasyonu destekleyen tüm sınıflar için kullanılabilir. Otomasyon desteğiyle oluşturulmuş projeler için de kullanılabilir. Diğer bir deyişle, [ATL destekleyen](../../atl/reference/mfc-support-in-atl-projects.md)bir MFC projesi ya da MFC Uygulama sihirbazının [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında **Otomasyon** onay kutusunu seçtiğiniz bir MFC projesi.

   Aşağıdaki temel sınıflar için Otomasyon desteği kullanılamaz:

  - `CAsyncMonitorFile`

  - `CAsyncSocket`

  - `CCachedDataPathProperty`

  - `CConnectionPoint`

  - `CDatabase`

  - `CDataPathProperty`

  - `CHttpFilter`

  - `CHttpServer`

  - `CInternetSession`

  - `CObject`

  - `CSocket`

## <a name="see-also"></a>Ayrıca bkz.

[MFC sınıfı](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
