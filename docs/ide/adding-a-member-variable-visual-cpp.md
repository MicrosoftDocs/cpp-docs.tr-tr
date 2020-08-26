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
ms.openlocfilehash: e7fd5bd93198c494f18fe18755d13d40fe7fbf96
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845139"
---
# <a name="add-a-member-variable"></a>Üye değişkeni ekleme

Sınıf Görünümü kullanarak bir sınıfa üye değişkeni ekleyebilirsiniz. Üye değişkenleri [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md)için ya da genel olabilir. Veri üyesi değişkeni Sihirbazı ilgili bilgileri almak ve uygun konumlarda kaynak dosyalarınıza öğe eklemek için kullanmak üzere tasarlanmıştır. [Kaynak görünümü](../windows/how-to-create-a-resource-script-file.md#create-resources)veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) [iletişim kutusu düzenleyicisinden](../windows/dialog-editor.md) bir üye değişkeni ekleyebilirsiniz.

> [!NOTE]
> Bir iletişim kutusu tasarlarken ve uygularken, iletişim kutusu denetimlerini eklemek ve ardından denetimlerin üye değişkenlerini uygulamak için Iletişim kutusu düzenleyicisini kullanmayı daha verimli bulabilirsiniz.

**Kaynak Görünümü üye değişkeni Ekleme Sihirbazı 'Nı kullanarak bir iletişim kutusu denetimine bir üye değişkeni eklemek için:**

1. Kaynak Görünümü, projenin iletişim kutularının listesini göstermek için proje düğümünü ve Iletişim kutusu düğümünü genişletin.

1. Iletişim kutusu düzenleyicisinde açmak için üye değişkenini eklemek istediğiniz iletişim kutusuna çift tıklayın.

1. Iletişim kutusunda, Iletişim kutusunda, üye değişkenini eklemek istediğiniz denetime sağ tıklayın.

1. Kısayol menüsünde, **değişken Ekle** ' yi seçerek [üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard)' nı görüntüleyin.

   > [!NOTE]
   > **DENETIM kimliğinde**varsayılan bir değer zaten sağlanmış.

1. İlgili sihirbaz kutularındaki bilgileri sağlayın. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

1. Projeye tanım ve uygulama kodu eklemek ve Sihirbazı kapatmak için **son** ' u seçin.

**Üye değişkeni Ekleme Sihirbazı 'Nı kullanarak Sınıf Görünümü üye değişken eklemek için:**

1. [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), projedeki sınıfları göstermek için proje düğümünü genişletin.

1. Değişken eklemek istediğiniz sınıfa sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' yi seçin ve sonra da **değişken Ekle** ' yi seçerek üye değişkeni Ekleme Sihirbazı 'nı görüntüleyin.

1. İlgili sihirbaz kutularındaki bilgileri sağlayın. Daha fazla bilgi için bkz. [üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard).

1. Projeye tanım ve uygulama kodu eklemek ve Sihirbazı kapatmak için **son** ' u seçin.

## <a name="in-this-section"></a>Bu bölümde

- [Üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard)
- [İletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types)

## <a name="add-member-variable-wizard"></a>Üye değişkeni Ekleme Sihirbazı

Bu sihirbaz başlık dosyasına bir üye değişkeni bildirimi ekler. Seçeneklere bağlı olarak,. cpp dosyasına kod ekleyebilir. Sihirbazı kullanarak üye değişkenini ekledikten sonra, kodu geliştirme ortamında düzenleyebilirsiniz.

- **Erişim**

  Üye değişkenine erişimi ayarlar. Erişim değiştiricileri, diğer sınıfların üye değişkenine sahip olduğu erişimi belirten anahtar sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Üye değişkeni erişim düzeyi varsayılan olarak olarak ayarlanır **`public`** .

  - [genel](../cpp/public-cpp.md)
  - [protected](../cpp/protected-cpp.md)
  - [private](../cpp/private-cpp.md)

- **Değişken türü**

  Eklemekte olduğunuz üye değişkeni için dönüş türünü ayarlar.

  - İletişim kutusu denetimi olmayan bir üye değişkeni ekliyorsanız, kullanılabilir türler listesinden seçin.

    Türler hakkında daha fazla bilgi için bkz. [temel türler](../cpp/fundamental-types-cpp.md).

    - **`char`**
    - **`double`**
    - **`float`**
    - **`int`**
    - **`long`**
    - **`short`**
    - **`unsigned char`**
    - **`unsigned int`**
    - **`unsigned long`**

  - İletişim kutusu denetimi için bir üye değişkeni ekliyorsanız, bu kutu bir denetim veya değer için döndürülen nesne türü ile doldurulur. **Denetim**' i seçerseniz, **DEĞIŞKEN türü** **denetim kimliği** kutusunda seçtiğiniz denetimin temel sınıfını belirtir. İletişim kutusu denetimi bir değer tutabilir ve **değer**' i seçerseniz, **değişken türü** , denetimin tutatabilecek değer için uygun türü belirtir. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

    Bu değer, **DENETIM kimliğindeki** seçime bağlıdır ve değiştirilemez.

- **Değişken adı**

  Eklemekte olduğunuz üye değişkeninin adını ayarlar. Üye değişkenleri genellikle `m_` Varsayılan olarak sizin için belirtilen tanımlama dizesiyle başlar.

- **Denetim değişkeni**

  Üye değişkeninin, [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md) desteğiyle bir iletişim kutusu içindeki bir denetimi yönettiğini gösterir. Daha fazla bilgi için bkz. [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange). Bu seçenek yalnızca [CDialog](../mfc/reference/cdialog-class.md)'dan türetilmiş sınıflara eklenen üye değişkenleri için kullanılabilir. **DENETIM kimliği** ve **Denetim türü** seçeneklerini etkinleştirmek için bu kutuyu seçin.

- **Denetim KIMLIĞI**

  Eklemekte olduğunuz denetim değişkeninin KIMLIĞINI ayarlar. Üye değişkenini eklemekte olduğunuz denetim türünün KIMLIĞINI listeden seçin. Liste yalnızca **denetim değişkeni** kutusu seçildiğinde etkindir ve iletişim kutusuna zaten eklenmiş olan denetimler için kimlikler ile sınırlıdır. Örneğin, standart **Tamam** düğmesi Için, denetim kimliği **IDOK**olur.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Denetim**|Bu seçenek, denetim türü için varsayılan olarak ayarlanır. Denetimin durumunu veya içeriğini (liste kutusu, Birleşik giriş kutusu veya düzenleme kutusu için yönetmek isteyebileceğiniz gibi) değil, denetimin kendisini yönetir.|
  |**Değer**|Bu seçenek, bir değeri tutabilecek ya da bir düzenleme kutusu ya da onay kutusu gibi bir durumu gösteren denetim türleri için kullanılabilir. Ayrıca, Aralık, içerik veya durum yönetebileceğiniz Denetim türleri için de kullanılabilir. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).|

- **Kategori**

  Değişkenin bir denetim türüne mi yoksa denetimin değerine mi bağlı olduğunu belirtir.

- **Denetim türü**

  Eklenmekte olan denetimin türünü ayarlar. Bu kutu değiştirilemez. Örneğin, bir düğmenin denetim türü **düğmesi**vardır ve bir açılan kutuda denetim türü **ComboBox**bulunur. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri ve değişken türleri](#dialog-box-controls-and-variable-types).

- **En fazla karakter**

  Yalnızca **değişken türü** [CString](../atl-mfc-shared/reference/cstringt-class.md)olarak ayarlandığında kullanılabilir. Denetimin tutabileceğini en çok karakter sayısını gösterir.

- **En düşük değer**

  Yalnızca değişken türü,,,,,,,, `BOOL` **`int`** `UINT` **`long`** `DWORD` **`float`** **`double`** `BYTE` **`short`** , [cotapara birimi](../mfc/reference/colecurrency-class.md) veya [CTime](../atl-mfc-shared/reference/ctime-class.md)olduğunda kullanılabilir. Ölçek veya tarih aralığı için kabul edilebilir en düşük değeri gösterir.

- **En yüksek değer**

  Yalnızca değişken türü,,,,,,,, `BOOL` **`int`** `UINT` **`long`** `DWORD` **`float`** **`double`** `BYTE` **`short`** , `COLECurrency` , veya `CTime` olduğunda kullanılabilir. Ölçek veya tarih aralığı için kabul edilebilir en yüksek değeri gösterir.

- **. h dosyası**

  ActiveX denetimleri için üye değişkenleri sarmalayıcı sınıfı gerektirir. Sınıf bildirimini eklemek için üst bilgi dosyasının adını ayarlar.

- **. cpp dosyası**

  ActiveX denetimleri için üye değişkenleri sarmalayıcı sınıfı gerektirir. Sınıf tanımını eklemek için uygulama dosyasının adını ayarlar.

- **Yorum**

  Üye değişkeni için üstbilgi dosyasında bir açıklama sağlar.

## <a name="dialog-box-controls-and-variable-types"></a>İletişim kutusu denetimleri ve değişken türleri

MFC kullanılarak oluşturulan bir iletişim kutusu denetimine üye değişkeni eklemek için [üye değişkeni Ekleme Sihirbazı](#add-member-variable-wizard) ' nı kullanabilirsiniz. Üye değişkenini eklediğiniz denetimin türü, iletişim kutusunda görünen seçenekleri belirler.

Aşağıdaki tabloda, MFC ve [iletişim kutusu düzenleyicisinde](../windows/dialog-editor.md)desteklenen tüm iletişim kutusu denetim türleri açıklanmaktadır. Ayrıca, kullanılabilir türlerini ve değerlerini de görüntüler.

|Denetim|Denetim türü|Denetim değişkeni türü|Değer değişken türü|Min/Max değerleri (yalnızca değer türü)|
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|
|Animasyon denetimi|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Seçim yalnızca denetim|YOK|
|Düğme|Bu|[CButton](../mfc/reference/cbutton-class.md)|Seçim yalnızca denetim|YOK|
|Onay kutusu|DENETLEMEZ|[CButton](../mfc/reference/cbutton-class.md)|`BOOL`|En düşük değer/en büyük değer|
|Açılır kutu|Öğesı|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|En fazla karakter|
|Tarih saat seçici denetimi|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|En düşük değer/en büyük değer|
|Düzenleme kutusu|DÜZENLE|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, Long, DWORD, float, Double, BYTE, Short, BOOL, `COleDateTime` veya `COleCurrency`|En küçük değer/en büyük değer; bazı destek en fazla karakter|
|Kısayol denetimi|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Seçim yalnızca denetim|YOK|
|Liste kutusu|KUTUSUNA|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|En fazla karakter|
|Liste denetimi|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Seçim yalnızca denetim|YOK|
|Aylık Takvim denetimi|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|En düşük değer/en büyük değer|
|İlerleme denetimi|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Seçim yalnızca denetim|YOK|
|Zengin düzenleme 2 denetimi|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|En fazla karakter|
|Zengin düzenleme denetimi|RICHEDIT|`CRichEditCtrl`|`CString`|En fazla karakter|
|Kaydırma çubuğu (dikey veya yatay|KAYDıRMA çubuğu|[CScrollBar](../mfc/reference/cscrollbar-class.md)|**`int`**|En düşük değer/en büyük değer|
|Kaydırıcı denetimi|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|**`int`**|En düşük değer/en büyük değer|
|Döndürme denetimi|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Seçim yalnızca denetim|YOK|
|Sekme denetimi|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Seçim yalnızca denetim|YOK|
|Ağaç denetimi|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Seçim yalnızca denetim|YOK|
