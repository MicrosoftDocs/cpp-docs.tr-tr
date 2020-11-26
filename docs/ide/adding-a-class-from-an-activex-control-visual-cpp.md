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
ms.openlocfilehash: d63f73e17e47f2cabb8f1a55c71325ec7068a2c8
ms.sourcegitcommit: 6284bca6549e7b4f199d4560c30df6c1278bd4a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96188932"
---
# <a name="add-a-class-from-an-activex-control"></a>ActiveX denetiminden sınıf ekleme

Kullanılabilir ActiveX denetimindeki bir arabirimden MFC sınıfı oluşturmak için bu sihirbazı kullanın. MFC [uygulamasına](../mfc/reference/creating-an-mfc-application.md), MFC [DLL](../mfc/reference/creating-an-mfc-dll-project.md)'sine veya [MFC ActiveX denetimine](../mfc/reference/creating-an-mfc-activex-control.md)MFC sınıfı ekleyebilirsiniz.

> [!WARNING]
> Visual Studio 2017 sürüm 15,9 ' de, Microsoft bu kod Sihirbazı 'nı kullanımdan kaldırılmıştır ve bu kodu Visual Studio 'nun gelecek bir sürümünde kaldıracağız. Bu sihirbaz nadiren kullanılır. ATL ve MFC için genel destek, bu sihirbazın kaldırılmasından etkilenmez. Bu kullanımdan kaldırma hakkında görüşlerinizi paylaşmak isterseniz, [Bu anketi](https://www.surveymonkey.com/r/QDWKKCN)doldurun. Görüşleriniz bizim için önemlidir.
<!-- Blank comment here to separate the warning and note. -->
> [!NOTE]
> ActiveX denetiminden bir sınıf eklemek için Otomasyon etkin olan MFC projenizi oluşturmanız gerekmez.

ActiveX denetimi, çok çeşitli OLE işlevlerini destekleyen bileşen nesne modeli (COM) tabanlı bir yeniden kullanılabilir yazılım bileşenidir. Bu, birçok yazılım ihtiyaçlarına uyacak şekilde özelleştirilebilir. ActiveX denetimlerini, World Wide Web sayfalarında sıradan ActiveX denetim kapsayıcılarında veya Internet üzerinde kullanabilirsiniz.

**ActiveX denetiminden MFC sınıfı eklemek için:**

1. **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ActiveX denetim sınıfını eklemek istediğiniz projenin adına sağ tıklayın.

1. Kısayol menüsünde **Ekle**' yi ve ardından **Sınıf Ekle**' yi seçin.

1. [Sınıf Ekle](./adding-a-class-visual-cpp.md#add-class-dialog-box) Iletişim kutusundaki **Şablonlar** bölmesinde, **ActiveX denetiminden MFC sınıfı**' nı seçin ve ardından **Aç** ' ı seçerek [ActiveX denetimi 'nden Sınıf Ekle sihirbazını](#add-class-from-activex-control-wizard)görüntüleyin.

Sihirbazda, ActiveX denetimine birden fazla arabirim ekleyebilirsiniz. Ayrıca, tek bir sihirbaz oturumunda birden fazla ActiveX denetiminden sınıflar oluşturabilirsiniz.

Sisteminizde kayıtlı ActiveX denetimlerinden sınıflar ekleyebilir veya tür kitaplığı dosyalarında (. tlb,. olb,. dll,. ocx veya. exe) bulunan ActiveX denetimlerinden, önce bunları sisteminize kaydetmeden sınıfları ekleyebilirsiniz. ActiveX denetimlerini kaydetme hakkında daha fazla bilgi için bkz. [OLE denetimlerini kaydetme](../mfc/reference/registering-ole-controls.md).

Sihirbaz, seçilen ActiveX denetiminden eklediğiniz her arabirim için [CWnd](../mfc/reference/cwnd-class.md) 'Den veya [cotadispatchsürücüden](../mfc/reference/coledispatchdriver-class.md)türetilen bir MFC sınıfı oluşturur.

## <a name="in-this-section"></a>Bu bölümde

- [ActiveX denetimi sihirbazından sınıf ekleme](#add-class-from-activex-control-wizard)

## <a name="add-class-from-activex-control-wizard"></a>ActiveX denetimi sihirbazından sınıf ekleme

Kullanılabilir bir ActiveX denetiminden MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz, seçilen ActiveX denetiminden eklediğiniz her arabirim için bir sınıf oluşturur.

- **Sınıf Ekle**

  Sınıfın oluşturulduğu tür kitaplığının konumunu belirtir.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Kapsayıcı Kayıt Defteri**|Tür kitaplığı sisteme kaydedilir. Kayıtlı tür kitaplıkları **kullanılabilir ActiveX denetimlerinde** listelenmiştir.|
  |**Dosya**|Tür kitaplığı sistemde kayıtlı değildir, ancak bir dosyada depolanır. Dosya konumunu **konuma** girin.|

- **Kullanılabilir ActiveX denetimleri**

  Sistemde kayıtlı olan ActiveX denetimlerini belirtir. Arabirimlerini **arabirimler** listesinde göstermek için bu listeden bir ActiveX denetimi seçin. ActiveX denetimlerini kaydetme hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma](../mfc/mfc-activex-controls-distributing-activex-controls.md) .

  **Sınıf Ekle** altında **Dosya** ' yı seçerseniz bu kutu değişiklik için kullanılamaz.

- **Konum**

  ActiveX denetiminin konumunu belirtir. **Sınıfından sınıf Ekle** altında **Dosya** ' yı seçerseniz, tür kitaplığına sahip dosyanın konumunu sağlayabilirsiniz. Dosyanın konumuna gitmek için üç nokta düğmesini seçin.

  **Sınıf Ekle** altında, **kayıt defteri** ' ni seçerseniz bu kutu değişiklik için kullanılamaz.

- **Arabirimler**

  ActiveX denetimindeki arabirimleri belirtir. Sihirbaz, **kullanılabilir ActiveX denetimlerinde** Geçerli seçimden arabirimler kullanır veya **konumunda** belirtilen tür kitaplığı dosyasındaki arabirimleri kullanır.

  |Aktar düğmesi|Açıklama|
  |---------------------|-----------------|
  |**>**|**Arabirimler** listesinde seçili olan arabirimi ekler. Arabirim seçilmezse kullanılamaz.|
  |**>>**|Tüm arabirimleri ActiveX denetimine ekler. Sihirbaz, **kullanılabilir ActiveX denetimlerinde** Geçerli seçimden arabirimler kullanır veya **konumunda** belirtilen tür kitaplığı dosyasındaki arabirimleri kullanır.|
  |**\<**|**Oluşturulan sınıflar** listesinde şu anda seçili olan sınıfı kaldırır. **Oluşturulan sınıflar** listesinde şu anda hiçbir sınıf seçili değilse kullanılamaz.|
  |**\<\<**|**Oluşturulan sınıflar** listesindeki tüm sınıfları kaldırır. **Oluşturulan sınıflar** listesi boşsa kullanılamaz.|

- **Oluşturulan sınıflar**

  Or düğmesi kullanılarak eklenen arabirimlerde oluşturulacak sınıf adlarını belirtir **>** **>>** . Bir sınıf seçmek için bu kutuyu seçebilir ve sonra listede gezinmek için yukarı veya aşağı tuşlarını kullanabilirsiniz. **Son**' u seçtiğinizde, oluşturulan her sınıf adını **sınıf** kutusunda ve oluşturulan her dosya adını **. h dosya** kutusunda görüntüleyebilirsiniz. Bu kutuda tek seferde yalnızca bir sınıf seçebilirsiniz.

  Bir sınıfı bu listede seçip seçerek kaldırabilirsiniz **<** . Tüm sınıfları kaldırmak için **oluşturulan sınıflar** kutusunda bir sınıf seçmeniz gerekmez. Öğesini seçerek **<<** , **oluşturulan sınıflar** kutusundaki tüm sınıfları kaldırırsınız.

- **Sınıf**

   **Son**' u seçtiğinizde sihirbazın eklediği **oluşturulan sınıflar** kutusunda seçilen sınıfın adını belirtir. **Sınıf** kutusunda adı düzenleyebilirsiniz.

- **. h dosyası**

  Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Varsayılan olarak, bu ad, **üretilen sınıflarda** sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini seçin. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' u seçene kadar sihirbaz bu dosyayı seçili konuma kaydetmez.

  Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçip **son**' u seçerseniz, sihirbaz, sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' i seçin; sihirbaza dönmek için **Hayır** ' ı seçin ve başka bir dosya adı belirtin.

- **. cpp dosyası**

  Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, **üretilen sınıflarda** sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesini seçin. Bu dosya, sihirbazda **son** ' u seçene kadar seçili konuma kaydedilmez.

  Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçip **son**' u seçerseniz, sihirbaz, sınıf uygulamasının dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' i seçin; sihirbaza dönmek için **Hayır** ' ı seçin ve başka bir dosya adı belirtin.
