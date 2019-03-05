---
title: MFC Sınıf Ekleme Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
ms.openlocfilehash: fa9b947ae6fc0e48aaecde61e35a5f4152c85f27
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304099"
---
# <a name="mfc-add-class-wizard"></a>MFC Sınıf Ekleme Sihirbazı

Varolan bir MFC projesine bir sınıf eklemek için bu kod Sihirbazı'nı kullanın ya da MFC destekleyen bir ATL projesine bir sınıf ekleyin. Ayrıca, MFC desteğine sahip Win32 projeleri için MFC sınıfları ekleyebilirsiniz. Projeyi oluştururken belirttiğiniz özellikleri bu iletişim kutusunda seçenekleri belirleme.

## <a name="names"></a>Adlar

Bu sayfada, sınıf adı, temel sınıf ve yeni bir sınıf için dosya adlarını belirtin.

- **Sınıf adı**

  Yeni bir sınıf adını belirtir ve varsayılan olarak kimlikleri ve bu sayfadaki dosya adlarını sağlar. C++ sınıfları genellikle "C" ile başlar örneğin, "CMyClass" "MyClass.h" olur vb.

- **Temel sınıf**

  Yeni bir sınıf temel sınıfın adını belirtir. Varsayılan olarak, temel bir sınıftır [CWnd](../../mfc/reference/cwnd-class.md). Seçtiğiniz temel sınıfı, bu sayfadaki diğer kutuları etkin olup olmadığını belirler.

  Temel sınıf sınıfında iletişim kimliği veya bir kaynak kimliği olup olmadığını belirleyen ayarladığınız sınıf türü Genel tür sınıfı aşağıdaki gibidir:

  - Sınıflar gibi [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), veya [CDocument](../../mfc/reference/cdocument-class.md), bir iletişim kutusu gerektirmeyen kimliği veya kaynak kimliği. Bu sınıfların bir iletişim kutusu veya kaynak kimliği kullanmayın Temel sınıfınız için bu sınıflardan birine seçerseniz **iletişim kimliği** kutusu ve **DHTML kaynak kimliği** kutusu soluk görünür.

  - Sınıflar gibi [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), veya [CPropertyPage](../../mfc/reference/cpropertypage-class.md), bir iletişim ID gerektir

  - Sınıf [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), bir iletişim kutusu IDSİ DHTML kaynak kimliği ve bir HTML dosya adı gerektirir.

  Bir iletişim kutusu IDSİ gerektiren sınıflar için bunu kullanmak için daha verimli bulabilirsiniz [Kaynak Düzenleyicisi](../../windows/resource-editors.md) Kimliğini, iletişim kaynağını oluşturma atama [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ve ardından ilişkili bir sınıf oluşturun Bu kaynak kimliği ile Bkz: [yeni iletişim kutusu oluşturma](../../windows/creating-a-new-dialog-box.md) standart bir Windows iletişim kutusu oluşturma hakkında daha fazla bilgi.

  > [!NOTE]
  > Bir iletişim kutusu kaynağı ilk oluşturun ve kendi yeni sınıfından türetilen `CDHtmlDialog`, standart Windows Sil **Tamam** ve **iptal** varsayılan iletişim kutusunda görünen düğme. Standart bir Windows iletişim kutusu içeren kendi DHTML formun barındıran **Tamam** ve **iptal** düğmeleri.

  İletişim kutusu, hem Windows denetimleri ve DHTML denetimleri içerebilir ancak önerilmez.

- **İletişim kutusu kimliği**

  Seçtiyseniz, iletişim Kimliğini belirtir `CDialog`, `CFormView`, `CPropertyPage`, veya `CDHtmlDialog` olarak **temel sınıfı**.

- **.h dosyası**

  Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

  Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **.cpp dosyası**

  Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

  Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Etkin Erişilebilirlik**

  Çağırarak etkin erişilebilirlik için MFC'nin desteğini etkinleştirir [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) oluşturucuda. Türetilmiş sınıflar için bu seçenek kullanılabilir [CWnd](../../mfc/reference/cwnd-class.md).

- **DHTML kaynak kimliği**

  Türetilen sınıflar için geçerlidir `CDHtmlDialog` yalnızca. DHTML iletişim kutusu kaynak Kimliğini belirtir. Kaynak Kimliği, projenin .rc dosyasında, HTML iletişim kutusu dosya adının yanı sıra HTML bölümünde görünür. Bu kimlik tarafından tanımlanan DHTML kaynak tarafından tanımlanan iletişim kutusu tarafından barındırılan **iletişim kimliği**.

- **. HTM dosyası**

  Türetilen sınıflar için geçerlidir `CDHtmlDialog` yalnızca. DHTML iletişim kutusu için HTML dosya adını ayarlar. Varsayılan olarak, bu dosya adı, sınıf adını temel alır. DHTML iletişim kutusu kaynak kimliği ile birlikte projenin .rc dosyasının HTML bölümünde dosya adı görüntülenir.

- **Otomatikleştirme**

  Destek için sınıf düzeyinde ayarlar [Otomasyon](../../mfc/automation.md). Sınıf düzeyinde Otomasyonu, Otomasyon destekleyen tüm sınıflar için kullanılabilir. Otomasyon için destek ile oluşturulan projeleri için de kullanılabilir. Diğer bir deyişle, ya da bir MFC projesini [ATL destekler](../../atl/reference/mfc-support-in-atl-projects.md), veya kendisi için seçtiğiniz bir MFC projesine **Otomasyon** onay kutusuna [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) MFC sayfası Uygulama Sihirbazı.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Yok.**|Sınıf Otomasyonu destek sahip olduğunu gösterir.|
  |**Otomatikleştirme**|Sınıf Otomasyonu desteklediğini belirtir. Bu seçeneği belirlerseniz, yeni oluşturulan sınıf, programlanabilir bir otomasyon istemci uygulamaları, Microsoft Visual Basic ve Microsoft Excel gibi nesnesiyle olarak kullanılabilir. Bu seçenek, bu tablodan sonra listelenen temel sınıflar için kullanılabilir değildir.|
  |**Tarafından türü kimliği**|Diğer uygulamaları otomasyonu kullanarak bu sınıfın nesneleri oluşturma sınıf ve proje desteklediğini gösterir. Bu seçenek belirtilmişse, Otomasyon istemcileri doğrudan bir Automation nesnesi oluşturabilirsiniz. Tür kimliği metin kutusunda, istemci uygulaması tarafından oluşturulacak nesne belirtmek için kullanılır; Bu sistem çapında ve benzersiz olmalıdır. Bu seçenek, bu tablodan sonra listelenen temel sınıflar için kullanılabilir değildir.|

  Aşağıdaki temel sınıflar için Otomasyon desteği yoktur:

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

- **Tür kimliği**

  Sınıf türü kimliği ayarlar. **Türü kimliği** kutusunda proje adı ve yeni sınıf adı şu şekilde birleştirir: *MFCProj.MFCClass*. Bu kimliği yalnızca seçtiyseniz, takımdaki herhangi biri **Otomasyon** seçeneği **tür Kimliğine göre Creatable**.

- **DocTemplate kaynaklar oluştur**

  Uygulamanın oluşturduğu belgeler belge şablonu kaynaklara sahip olduğunu gösterir. Bu onay kutusu etkinleştirmek için proje MFC belge/görünüm mimarisinin desteklemesi gerekir ve bu sınıfın temel sınıfına olmalıdır [CFormView](../../mfc/reference/cformview-class.md).

  Bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[MFC sınıfı](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
