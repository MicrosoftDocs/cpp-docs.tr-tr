---
title: ActiveX denetiminden sınıf ekleme
ms.date: 11/08/2018
f1_keywords:
- vc.codewiz.class.axcontrol
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
- ActiveX Control Wizard
- add class from ActiveX control wizard [C++]
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
ms.openlocfilehash: 1d91d98082a5c5d6d45bfa31e81c59e8925aa2c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386284"
---
# <a name="add-a-class-from-an-activex-control"></a>ActiveX denetiminden sınıf ekleme

Kullanılabilir bir ActiveX denetimi bir arabirimde bir MFC sınıfı oluşturmak için bu sihirbazı kullanın. Bir MFC sınıfı için ekleyebileceğiniz bir [MFC uygulaması](../mfc/reference/creating-an-mfc-application.md), bir [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md), veya bir [MFC ActiveX denetimi](../mfc/reference/creating-an-mfc-activex-control.md).

> [!WARNING]
> Visual Studio 2017 sürüm 15.9, Microsoft bu kod Sihirbazı'nı kullanım dışı ve Visual Studio'nun gelecekteki bir sürümde kaldıracağız. Bu sihirbaz nadiren kullanılır. ATL ve MFC genel desteği kaldırılmasını Bu sihirbaz tarafından etkilenmiş değil. Bu kullanımdan kaldırma hakkındaki görüşlerinizi paylaşmak istiyorsanız, tamamlamak [bu anketi](https://www.surveymonkey.com/r/QDWKKCN). Geri bildiriminiz bizim için önemlidir.
<!-- Blank comment here to separate the warning and note. -->
> [!NOTE]
> ActiveX denetiminden sınıf ekleme için etkinleştirilmiş Otomasyonu ile MFC projenize oluşturmanız gerekmez.

ActiveX denetimi Bileşen Nesne Modeli (çok çeşitli OLE işlevselliği destekleyen COM) dayalı bir yeniden kullanılabilir yazılım bileşenidir. Birçok yazılım gereksinimlerinize uyacak şekilde özelleştirilebilir. World Wide Web sayfaları'nda sıradan ActiveX denetim kapsayıcıları veya Internet'te ActiveX denetimleri kullanabilirsiniz.

**ActiveX denetiminden MFC sınıfı eklemek için:**

1. Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ActiveX denetim sınıfı eklemek istediğiniz proje adına sağ tıklayın.

1. Kısayol menüsünden **Ekle**ve ardından **sınıfı Ekle**.

1. İçinde [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusundaki **şablonları** bölmesinde seçin **ActiveX denetiminden MFC sınıfı**ve ardından **açık** görüntülemek için [ActiveX denetimi sihirbazından sınıf ekleme](#add-class-from-activex-control-wizard).

Sihirbazda, birden fazla ActiveX denetimi arabiriminde ekleyebilirsiniz. Tek bir sihirbaz oturumunda birden fazla ActiveX denetiminden sınıf de oluşturabilirsiniz.

ActiveX denetimlerinde sisteminizdeki kayıtlı sınıfları ekleyebilirsiniz ya da ActiveX denetimlerinde ilk bunları sisteminizde kayıt olmadan tür kitaplığı dosyalarını (.tlb, .olb, .dll, .ocx veya .exe) içinde bulunan sınıfları ekleyebilirsiniz. ActiveX denetimlerini kaydetme hakkında daha fazla bilgi için bkz. [kaydetme OLE denetimleri](../mfc/reference/registering-ole-controls.md).

MFC sınıfından türetilen bir sihirbaz [CWnd](../mfc/reference/cwnd-class.md) veya [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), seçilen ActiveX denetiminden eklediğiniz her arabirim için.

## <a name="in-this-section"></a>Bu bölümde

- [ActiveX denetimi sihirbazından sınıf ekleme](#add-class-from-activex-control-wizard)

## <a name="add-class-from-activex-control-wizard"></a>ActiveX denetimi sihirbazından sınıf ekleme

Kullanılabilir ActiveX denetiminden MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz seçilen ActiveX denetiminden eklediğiniz her arabirim için bir sınıf oluşturur.

- **Şuradan Sınıf Ekle**

  Sınıf oluşturulduğu tür kitaplığının konumu belirtir.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir ActiveX denetimleri**.|
  |**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyada depolanır. Dosya konumunda sağlamak **konumu**.|

- **Kullanılabilir ActiveX denetimleri**

  Şu anda sistemde kayıtlı ActiveX denetimleri belirtir. ActiveX denetimi arabirimlerinden içinde görüntülemek için bu listeden seç **arabirimleri** listesi. Bkz: [MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma](../mfc/mfc-activex-controls-distributing-activex-controls.md) ActiveX denetimlerini kaydetme hakkında daha fazla bilgi.

  Seçerseniz **dosya** altında **sınıfı gelen ekleme**, bu kutusuna değişiklik için kullanılamıyor.

- **Konum**

  ActiveX denetimi konumunu belirtir. Seçerseniz **dosya** altında **sınıfı gelen ekleme**, tür kitaplığı sahip bir dosya konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesini seçin.

  Seçerseniz **kayıt defteri** altında **sınıfı gelen ekleme**, bu kutusuna değişiklik için kullanılamıyor.

- **Arabirimler**

  Arabirimler ActiveX denetimini belirtir. Geçerli seçimde arabirimlerinden Sihirbazı'nı kullanan **kullanılabilir ActiveX denetimleri**, ya da bu arabirimi belirtilen tür kitaplığı dosyası kullanır **konumu**.

  |Aktarım düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Herhangi bir arabirim seçilirse kullanılabilir.|
  |**>>**|Tüm arabirimleri ActiveX denetimi ekler. Geçerli seçimde arabirimlerinden Sihirbazı'nı kullanan **kullanılabilir ActiveX denetimleri**, ya da bu arabirimi belirtilen tür kitaplığı dosyası kullanır **konumu**.|
  |**\<**|Şu anda seçili sınıfını kaldırır **sınıfları oluşturulan** listesi. Hiçbir sınıf içinde seçtiyseniz, kullanılabilir **sınıfları oluşturulan** listesi.|
  |**\<\<**|Tüm sınıfları kaldırır **sınıfları oluşturulan** listesi. Kullanılabilir ise **sınıfları oluşturulan** listesi boş.|

- **Oluşturulan sınıflar**

  Sınıf adları kullanılarak eklenen arabirimlerinden oluşturulacak belirtir **>** veya **>>** düğmesi. Bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını listede gezinmek için bu kutuyu seçebilirsiniz. Seçtiğinizde, **son**, her oluşturulan sınıfın adı görüntüleyebileceğiniz **sınıfı** kutusu ve oluşturulan her dosya adı **.h dosyası** kutusu. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.

  Bu listeden seçim ve seçerek bir sınıf kaldırabilirsiniz **<**. Bir sınıfta seçmeniz gerekmez **sınıfları oluşturulan** kutusunu tüm sınıflar Kaldır. Seçerek **<<**, içindeki tüm sınıflar Kaldır **sınıfları oluşturulan** kutusu.

- **Sınıfı**

   Seçilen sınıfın adını belirtir **sınıfları oluşturulan** seçtiğinizde sihirbaz ekler kutusu **son**. Adlarında düzenleyebileceğiniz **sınıfı** kutusu.

- **.h dosyası**

  Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini seçin. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek Kaydet'i seçin olmaz **son** Sihirbazı'nda.

  Sihirbaz, bir dosyanın üzerine değil. Varolan bir dosyanın adını seçin ve ardından **son**, Sihirbazı dosya içeriği sınıf bildiriminin ekleneceği gösteren isteyip istemediğinizi sorar. Seçin **Evet** ; dosya eklemek için seçin **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **.cpp dosyası**

  Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesini seçin. Siz seçene kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

  Sihirbaz, bir dosyanın üzerine değil. Varolan bir dosyanın adını seçin ve ardından **son**, Sihirbazı dosya içeriği sınıf uygulamasının ekleneceği gösteren isteyip istemediğinizi sorar. Seçin **Evet** ; dosya eklemek için seçin **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.
