---
title: Üye değişkeni ekleme
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.member.variable
- vc.codewiz.variable.overview
helpviewer_keywords:
- member variables, adding
- member variables
- add member variable wizard [C++]
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
ms.openlocfilehash: 2a519c0606a7df6e0ce55997a055d78865afafbf
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694419"
---
# <a name="add-a-member-variable"></a>Üye değişkeni ekleme

Sınıf görünümü kullanarak bir sınıfa üye değişkeni ekleyebilirsiniz. Üye değişkenleri için ya da olabilir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md), veya genel olabilir. Veri üye değişkeni Sihirbazı'nı ilgili bilgileri alın ve uygun yerlerde, kaynak dosyalarında öğe eklemek için kullanmak üzere tasarlanmıştır. Bir üye değişkeninin ekleyebilir [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) içinde [kaynak görünümü](../windows/resource-view-window.md), veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).

> [!NOTE]
> Tasarladığınız ve iletişim kutusu uygulama, onu daha verimli bir iletişim kutusunda kullanılacak Düzenleyicisi iletişim kutusu denetimleri eklemek için bulabilirsiniz ve ardından Denetim üyesi değişkenleri uygulamak için.

**Üye değişkeni Ekleme Sihirbazı'nı kullanarak kaynak görünümünde bir iletişim denetimi için bir üye değişkeni eklemek için:**

1. Kaynak Görünümü'nde, proje ve proje iletişim kutuları listesini görüntülemek için iletişim düğümlerini genişletin.

1. İletişim kutusu Düzenleyicisi'nde açmak için üye değişkeni eklemek istediğiniz iletişim kutusu çift tıklayın.

1. İletişim kutusu Düzenleyicisi'nde görüntülenen iletişim kutusunda, bir üye değişkeni eklemek istediğiniz denetime sağ tıklayın.

1. Kısayol menüsünde **değişkeni Ekle** görüntülenecek [ekleme üye değişkeni Sihirbazı](#add-member-variable-wizard).

   > [!NOTE]
   > Varsayılan değer zaten sağlanan **denetim kimliği**.

1. Uygun Sihirbazı kutularındaki bilgileri sağlayın. Daha fazla bilgi için [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

1. Seçin **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.

**Sınıf Görünümü üye değişkeni Ekleme Sihirbazı'nı kullanarak bir üye değişkeni eklemek için:**

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), projede sınıflarını görüntülemek için proje düğümünü genişletin.

1. Bir değişkeni eklemek istediğiniz sınıf sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **değişken Ekle** ekleme üye değişkeni Sihirbazı görüntülenecek.

1. Uygun Sihirbazı kutularındaki bilgileri sağlayın. Daha fazla bilgi için [ekleme üye değişkeni Sihirbazı](#add-member-variable-wizard).

1. Seçin **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.

## <a name="in-this-section"></a>Bu bölümde

- [Üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard)
- [İletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types)

## <a name="add-member-variable-wizard"></a>Üye değişkeni Ekleme Sihirbazı

Bu sihirbaz bir üye değişken bildiriminde üstbilgi dosyasına ekler. Seçeneklere bağlı olarak, bunu .cpp dosyası için kod ekleyebilirsiniz. Sihirbazı kullanarak üye değişkenini ekledikten sonra kodu geliştirme ortamında düzenleyebilirsiniz.

- **Erişim**

  Erişim bir üye değişkeni ayarlar. Erişim değiştiricileri bir üye değişkeni diğer sınıflara sahip erişimi belirtin sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Üye değişkeni erişim düzeyini ayarlamak `public` varsayılan olarak.

  - [public](../cpp/public-cpp.md)
  - [protected](../cpp/protected-cpp.md)
  - [private](../cpp/private-cpp.md)

- **Değişken türü**

  Eklediğiniz üye değişkeni için dönüş türünü ayarlar.

  - Bir iletişim kutusu denetimi olmayan bir üye değişkeni ekliyorsanız, kullanılabilir türler listesinden seçin.

    Türleri hakkında daha fazla bilgi için bkz: [temel türler](../cpp/fundamental-types-cpp.md).

    |||
    |-|-|
    |`char`|`short`|
    |`double`|`unsigned char`|
    |`float`|`unsigned int`|
    |`int`|`unsigned long`|
    |`long`||

  - Bir iletişim kutusu denetimi için bir üye değişkeni ekliyorsanız, bu kutu bir denetim veya değer için döndürülen nesnenin türü ile doldurulur. Seçerseniz **denetimi**, ardından **değişken türü** seçtiğiniz denetim temel sınıfını belirtir **denetim kimliği** kutusu. İletişim kutusu denetiminin değeri tutabilir ve seçerseniz **değer**, ardından **değişken türü** denetimi tutabileceği değeri uygun türünü belirtir. Daha fazla bilgi için [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

    Bu değer seçime bağlıdır **denetim kimliği** ve değiştirilemez.

- **Değişken adı**

  Eklediğiniz üye değişkeni adını ayarlar. Üye değişkenleri genellikle tanımlayıcı dizesi ile başlayan `m_`, sağlanır, varsayılan olarak.

- **Denetim değişkeni**

  Üye değişkeni içeren bir iletişim kutusu denetimine yönetir gösterir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md) destekler. Daha fazla bilgi için [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange). Bu seçenek yalnızca türetilen sınıfların eklenen üye değişkenleri için kullanılabilir [CDialog](../mfc/reference/cdialog-class.md). Etkinleştirmek için bu kutuyu seçin **denetim kimliği** ve **denetim türü** seçenekleri.

- **Denetim Kimliği**

  Eklediğiniz denetim değişkeni için bir kimlik ayarlar. Listeden üye değişkeni eklediğiniz denetim türü kimliği seçin. Yalnızca etkin olduğunda listesidir **denetim değişkeni** kutusu seçilidir ve onun sınırlı kimlikleri denetimleri için iletişim kutusuna zaten eklendi. Örneğin, standart için **Tamam** düğme denetimi kimliğidir **IDOK**.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Denetimi**|Bu seçenek, Denetim türü için varsayılan olarak ayarlanır. (Bir liste kutusu, birleşik giriş kutusu veya düzenleme kutusu yönetmek isteyebileceğiniz gibi) denetim durumu ya da değil denetimin içeriğini yönetir.|
  |**Değer**|Bu seçenek, bir değer tutma veya bir düzenleme kutusuna veya bir onay kutusu gibi bir durum Göster denetim tipleri için kullanılabilir. Ayrıca, kendisi için aralık, içeriği veya durum yönettiğiniz denetim türleri için de kullanılabilir. Daha fazla bilgi için [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).|

- **Kategori**

  Değişkeni bir denetim türü veya denetimin değerini temel alan olup olmadığını belirtir.

- **Denetim türü**

  Eklenen denetimin türünü ayarlar. Bu kutuyu değiştirmek kullanılamaz. Örneğin, bir düğme denetim türü olan **düğmesi**, ve bir birleşik giriş kutusu denetim türünü **COMBOBOX**. Daha fazla bilgi için [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

- **En fazla karakter**

  Yalnızca **değişken türü** ayarlanır [CString](../atl-mfc-shared/reference/cstringt-class.md). En çok denetimi tutabileceği karakter sayısını gösterir.

- **En düşük değer**

  Değişken türü olduğunda kullanılabilir `BOOL`, `int`, `UINT`, `long`, `DWORD`, `float`, `double`, `BYTE`, `short`, [COLECurrency](../mfc/reference/colecurrency-class.md)veya [CTime](../atl-mfc-shared/reference/ctime-class.md). Bir ölçek veya tarih aralığını kabul edilebilir en düşük değeri gösterir.

- **En yüksek değer**

  Değişken türü olduğunda kullanılabilir `BOOL`, `int`, `UINT`, `long`, `DWORD`, `float`, `double`, `BYTE`, `short`, `COLECurrency`, veya `CTime`. Bir ölçek veya tarih aralığını kabul edilebilir en yüksek değeri gösterir.

- **.h dosyası**

  ActiveX denetimleri için üye değişkenleri olan bir sarmalayıcı sınıfı gerektirir. Sınıf bildirimi eklemek için üst bilgi dosyası adını ayarlar.

- **.cpp dosyası**

  ActiveX denetimleri için üye değişkenleri olan bir sarmalayıcı sınıfı gerektirir. Sınıf tanımı eklemek için uygulama dosyasının adını ayarlar.

- **Yorum**

  Üye değişkeni için üst bilgi dosyası bir açıklama sağlar.

## <a name="dialog-box-controls-and-variable-types"></a>İletişim kutusu denetimleri ve değişken türleri

Kullanabileceğiniz [üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard) MFC kullanılarak oluşturulan bir iletişim kutusu denetimine bir üye değişkeni eklemek için. Türü denetim üye değişkeni Ekle iletişim kutusunda görünen seçenekleri belirler.

MFC'de desteklenen tüm iletişim kutusu denetim türleri aşağıdaki tabloda açıklanmıştır ve [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md). Kullanılabilir türleri ve değerleri de görüntüler.

|Denetim|Denetim türü|Denetim değişkeni türü|Değişken türü değeri|En düşük/en yüksek değerleri (yalnızca değer türü)|
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|
|Animasyon denetimi|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|None; yalnızca denetim|Yok|
|Düğme|DÜĞME|[CButton](../mfc/reference/cbutton-class.md)|None; yalnızca denetim|Yok|
|Onay kutusu|ONAY|[CButton](../mfc/reference/cbutton-class.md)|`BOOL`|En düşük değer/en yüksek değeri|
|Birleşik giriş kutusu|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|En fazla karakter|
|Tarih Saat Seçici denetimi|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|En düşük değer/en yüksek değeri|
|Düzenleme kutusu|DÜZENLE|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, long, UINT, DWORD, double, BYTE, kısa, BOOL, float `COleDateTime`, veya `COleCurrency`|En düşük değer/en yüksek değeri; Bazı destek en fazla karakter|
|Kısayol tuşu denetimi|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|None; yalnızca denetim|Yok|
|Liste kutusu|LİSTE KUTUSU|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|En fazla karakter|
|Liste denetimi|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|None; yalnızca denetim|Yok|
|Ay takvim denetimi|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|En düşük değer/en yüksek değeri|
|İlerleme denetimi|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|None; yalnızca denetim|Yok|
|Zengin düzenleme 2 denetimi|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|En fazla karakter|
|Zengin düzenleme denetimi|RICHEDIT|`CRichEditCtrl`|`CString`|En fazla karakter|
|(Dikey veya yatay kaydırma çubuğu|KAYDIRMA ÇUBUĞU|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|En düşük değer/en yüksek değeri|
|Kaydırıcı denetimi|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|En düşük değer/en yüksek değeri|
|Döndürme denetimi|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|None; yalnızca denetim|Yok|
|Sekme denetimi|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|None; yalnızca denetim|Yok|
|Ağaç denetimi|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|None; yalnızca denetim|Yok|
