---
title: Özelleştirme Bildirimlerini İşleme
ms.date: 11/04/2016
f1_keywords:
- TBN_CUSTHELP
- TBN_QUERYINSERT
- TBNOTIFY
- NMHDR
- TBN_TOOLBARCHANGE
- TBN_ENDDRAG
- NM_SETFOCUS
- TBN_RESET
- NM_RETURN
- NM_ENDWAIT
- NM_STARTWAIT
- TBN_BEGINDRAG
- NM_OUTOFMEMORY
- TBN_QUERYDELETE
- NM_DBLCLK
- TBN_ENDADJUST
- NM_KILLFOCUS
- NM_RCLICK
- TBN_BEGINADJUST
- NM_CLICK
helpviewer_keywords:
- TBN_ENDADJUST notification [MFC]
- TBNOTIFY notification [MFC]
- TBN_BEGINDRAG notification [MFC]
- TBN_TOOLBARCHANGE notification [MFC]
- NM_CLICK notification [MFC]
- NM_RETURN notification [MFC]
- NM_RCLICK notification [MFC]
- TBN_ENDDRAG notification [MFC]
- TBN_BEGINADJUST notification [MFC]
- NM_ENDWAIT notification [MFC]
- NM_KILLFOCUS notification [MFC]
- NM_SETFOCUS notification [MFC]
- NM_OUTOFMEMORY notification [MFC]
- TBN_QUERYINSERT notification [MFC]
- NMHDR [MFC]
- NM_STARTWAIT notification [MFC]
- CToolBarCtrl class [MFC], handling notifications
- TBN_CUSTHELP notification [MFC]
- TBN_RESET notification [MFC]
- NM_DBLCLK notification [MFC]
- TBN_QUERYDELETE notification [MFC]
- NM_RDBLCLK notification [MFC]
- TBN_GETBUTTONINFO notification [MFC]
ms.assetid: 219ea08e-7515-4b98-85cb-47120f08c0a2
ms.openlocfilehash: 67f40d0dc50a853a39cb9b60a938d8eafe8293c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370483"
---
# <a name="handling-customization-notifications"></a>Özelleştirme Bildirimlerini İşleme

Windows araç çubuğu ortak denetimi, kullanıcının araç çubuğu düğmelerini eklemesine, silmesine veya yeniden düzenlemesine olanak tanıyan sistem tanımlı özelleştirme iletişim kutusu da dahil olmak üzere yerleşik özelleştirme özelliklerine sahiptir. Uygulama özelleştirme özelliklerinin kullanılabilir olup olmadığını belirler ve kullanıcının araç çubuğunu ne ölçüde özelleştirebileceğini denetler.

Bu özelleştirme özelliklerini araç çubuğuna **CCS_ADJUSTABLE** stilini vererek kullanıcının kullanımına sunabilirsiniz. Özelleştirme özellikleri, kullanıcının düğmeyi yeni bir konuma sürüklemesine veya bir düğmeyi araç çubuğundan sürükleyerek kaldırmasına olanak sağlar. Ayrıca, kullanıcı araç çubuğu düğmelerini eklemesine, silmesine ve yeniden düzenlemesine olanak tanıyan Araç Çubuğu nu **Özelleştir** iletişim kutusunu görüntülemek için araç çubuğunu çift tıklatabilir. Uygulama, üye işlevini [Özelleştir'i](../mfc/reference/ctoolbarctrl-class.md#customize) kullanarak iletişim kutusunu görüntüleyebilir.

Araç çubuğu denetimi, özelleştirme işlemindeki her adımda üst pencereye bildirim iletileri gönderir. Kullanıcı SHIFT tuşunu basılı tutar ve bir düğmeyi sürüklemeye başlarsa, araç çubuğu sürükleme işlemini otomatik olarak işler. Araç çubuğu, düğmenin silinip silinmeyeceğini belirlemek için **TBN_QUERYDELETE** bildirim iletisini üst pencereye gönderir. Üst pencere **FALSE**döndürürse sürükleme işlemi sona erer. Aksi takdirde, araç çubuğu fare girişini yakalar ve kullanıcının fare düğmesini serbest bırakmasını bekler.

Kullanıcı fare düğmesini serbest bıraktığınızda, araç çubuğu denetimi fare imlecinin konumunu belirler. İmleç araç çubuğunun dışındaysa, düğme silinir. İmleç başka bir araç çubuğu düğmesiüzerindeyse, araç çubuğu **TBN_QUERYINSERT** bildirim iletisini üst pencereye gönderarak verilen düğmenin soluna bir düğme takılıp takılmayabileceğini belirler. Üst pencere **TRUE**döndürürse düğme eklenir; aksi takdirde, öyle değildir. Araç çubuğu, sürükleme işleminin sona erini bildirmek için **TBN_TOOLBARCHANGE** bildirim iletisi gönderir.

Kullanıcı SHIFT tuşunu basılı tutmadan bir sürükleme işlemine başlarsa, araç çubuğu denetimi **TBN_BEGINDRAG** bildirim iletisini sahibi penceresine gönderir. Kendi düğme sürükleme kodunu uygulayan bir uygulama, sürükleme işlemini başlatmak için bu iletiyi sinyal olarak kullanabilir. Araç çubuğu, sürükleme işleminin sona erini bildirmek için **TBN_ENDDRAG** bildirim iletisi gönderir.

Araç çubuğu denetimi, kullanıcı **Araç Çubuğunu Özelleştir** iletişim kutusunu kullanarak bir araç çubuğunu özelleştirdiğinde bildirim iletileri gönderir. Araç çubuğu, kullanıcı araç çubuğunu çift tıklattıktan sonra, ancak iletişim kutusu oluşturulmadan önce **TBN_BEGINADJUST** bildirim iletisini gönderir. Ardından, araç çubuğu, araç çubuğunun düğmelerin eklenmesine izin verip vermediğini belirlemek için bir dizi **TBN_QUERYINSERT** bildirim iletisi göndermeye başlar. Üst pencere **TRUE**döndürdüğünde, araç çubuğu **TBN_QUERYINSERT** bildirim iletileri göndermeyi durdurur. Ana pencere herhangi bir düğme için **TRUE** döndürmezse, araç çubuğu iletişim kutusunu yok eder.

Ardından, araç çubuğu denetimi, araç çubuğundaki her düğme için bir **TBN_QUERYDELETE** bildirim iletisi göndererek araç çubuğundan herhangi bir düğmenin silinip silinilmeyeceğini belirler. Üst pencere, bir düğmenin silinebileceğini belirtmek için **TRUE** döndürür; aksi takdirde, **FALSE**döndürür. Araç çubuğu iletişim kutusuna tüm araç çubuğu düğmelerini ekler, ancak silinmeyen düğmeleri griye ler.

Araç çubuğu denetimi, Araç Çubuğunu Özelleştir iletişim kutusundaki bir düğme hakkında bilgi gerektiğinde, bilgi ihtiyacı olan düğmenin dizinini ve **TBNOTIFY** yapısının adresini belirterek **TBN_GETBUTTONINFO** bildirim iletisini gönderir. Üst pencere, yapıyı ilgili bilgilerle doldurmalıdır.

**Araç Çubuğunu Özelleştir** iletişim kutusunda Yardım düğmesi ve Sıfırla düğmesi bulunmaktadır. Kullanıcı Yardım düğmesini seçtiğinde, araç çubuğu denetimi **TBN_CUSTHELP** bildirim iletisini gönderir. Üst pencere yardım bilgilerini görüntüleyerek yanıt vermelidir. Kullanıcı Sıfırla düğmesini seçtiğinde iletişim kutusu **TBN_RESET** bildirim iletisi gönderir. Bu ileti, araç çubuğunun iletişim kutusunu yeniden başlatmak üzere olduğunu bildirir.

Bu iletilerin tümü **WM_NOTIFY** iletilerdir ve sahibi pencerenizin ileti eşlemine aşağıdaki formun ileti eşlemi girişleri eklenerek sahibiniz penceresinde işlenebilir:

```cpp
ON_NOTIFY( wNotifyCode, idControl, memberFxn )
```

- **wNotifyCode**

   **TBN_BEGINADJUST**gibi bildirim ileti tanımlayıcı kodu.

- **idKontrol**

   Bildirimi gönderen denetimin tanımlayıcısı.

- **üyeFxn**

   Bu bildirim geldiğinde çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple bildirilir:

```cpp
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );
```

Bildirim iletisi işleyicisi bir değer döndürürse, *sonuç*olarak işaret edilen **LRESULT'a** koymalıdır.

Her ileti `pNotifyStruct` için bir **NMHDR** yapısına veya **TBNOTIFY** yapısına işaret ederiz. Bu yapılar aşağıda açıklanmıştır:

**NMHDR** yapısı aşağıdaki üyeleri içerir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;  // handle of control sending message
    UINT idFrom;// identifier of control sending message
    UINT code;  // notification code; see below
} NMHDR;
```

- **hwndFrom**

   Bildirimi gönderen denetimin pencere tutamacı. Bu tutamacı bir `CWnd` işaretçiye dönüştürmek için [CWnd::FromHandle'ı](../mfc/reference/cwnd-class.md#fromhandle)kullanın.

- **idKaynak**

   Bildirimi gönderen denetimin tanımlayıcısı.

- **Kod**

   Bildirim kodu. Bu üye, **TBN_BEGINADJUST** veya **TTN_NEEDTEXT**gibi bir denetim türüne özgü bir değer olabilir veya aşağıda listelenen ortak bildirim değerlerinden biri olabilir:

  - **NM_CLICK** Kullanıcı denetim içinde sol fare düğmesini tıklattı.

  - **NM_DBLCLK** Kullanıcı, denetim içinde sol fare düğmesini çift tıklattı.

  - **NM_KILLFOCUS** Denetim giriş odağı kaybetti.

  - **NM_OUTOFMEMORY** Yeterli bellek olmadığı için denetim işlemi tamamlayamadı.

  - **NM_RCLICK** Kullanıcı denetim içinde sağ fare düğmesini tıklattı.

  - **NM_RDBLCLK** Kullanıcı, denetim içinde sağ fare düğmesini çift tıklattı.

  - **NM_RETURN** Denetim giriş odağına sahiptir ve kullanıcı ENTER tuşuna basmıştır.

  - **NM_SETFOCUS** Denetim giriş odağı aldı.

**TBNOTIFY** yapısı aşağıdaki üyeleri içerir:

```cpp
typedef struct {
    NMHDR hdr; // information common to all WM_NOTIFY messages
    int iItem; // index of button associated with notification
    TBBUTTON tbButton; // info about button associated withnotification
    int cchText;   // count of characters in button text
    LPSTR lpszText;// address of button text
} TBNOTIFY, FAR* LPTBNOTIFY;
```

- **Hdr**

   Tüm **WM_NOTIFY** iletilerinde yaygın bilgiler.

- **iÖğe**

   Bildirimle ilişkili düğme dizini.

- **Tbbutton**

   Bildirimle ilişkili araç çubuğu düğmesi hakkında bilgi içeren **TBBUTTON** yapısı.

- **cchText**

   Düğme metnindeki karakter sayısı.

- **lpszMetin**

   Düğme metniiçin işaretçi.

Araç çubuğunun gönderdiği bildirimler aşağıdaki gibidir:

- **TBN_BEGINADJUST**

   Kullanıcı araç çubuğu denetimini özelleştirmeye başladığında gönderilir. İşaretçi, bildirim hakkında bilgi içeren bir **NMHDR** yapısını işaret eder. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_BEGINDRAG**

   Kullanıcı araç çubuğu denetiminde bir düğmeyi sürüklemeye başladığında gönderilir. İşaretçi bir **TBNOTIFY** yapısını işaret eder. **iItem** üyesi sürüklenen düğmenin sıfır tabanlı dizinini içerir. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_CUSTHELP**

   Kullanıcı Araç Çubuğunu Özelleştir iletişim kutusundaki Yardım düğmesini seçtiğinde gönderilir. İade değeri yok. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **NMHDR** yapısını işaret eder. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_ENDADJUST**

   Kullanıcı araç çubuğu denetimini özelleştirmeyi bıraktığında gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **NMHDR** yapısını işaret eder. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_ENDDRAG**

   Kullanıcı araç çubuğu denetiminde bir düğmeyi sürüklemeyi bıraktığında gönderilir. İşaretçi bir **TBNOTIFY** yapısını işaret eder. **iItem** üyesi sürüklenen düğmenin sıfır tabanlı dizinini içerir. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_GETBUTTONINFO**

   Kullanıcı araç çubuğu denetimini özelleştirirken gönderilir. Araç çubuğu, Araç Çubuğu'nu Özelleştir iletişim kutusunun gerektirdiği bilgileri almak için bu bildirim iletisini kullanır. İşaretçi bir **TBNOTIFY** yapısını işaret eder. **iItem** üyesi bir düğmenin sıfır tabanlı dizinini belirtir. **pszText** ve **cchText** üyeleri geçerli düğme metninin adresini ve uzunluğunu karakterlerde belirtir. Bir uygulama düğme hakkında bilgi ile yapı doldurması gerekir. Düğme bilgileri yapıya kopyalanmışsa **TRUE'yu** döndürün veya başka bir şekilde **FALSE** döndürül.

- **TBN_QUERYDELETE**

   Kullanıcı bir araç çubuğu denetiminden bir düğmenin silinip silinmeyeceğini belirlemek için bir araç çubuğunu özelleştirirken gönderilir. İşaretçi bir **TBNOTIFY** yapısını işaret eder. **iItem** üyesi silinecek düğmenin sıfır tabanlı dizinini içerir. Düğmenin silinmesini önlemek için düğmenin silinmesine veya **YANLIŞ'a** izin vermek için **TRUE'yu** döndürün.

- **TBN_QUERYINSERT**

   Kullanıcı, verilen düğmenin soluna bir düğme takılıp takılmadığını belirlemek için bir araç çubuğu denetimini özelleştirirken gönderilir. İşaretçi bir **TBNOTIFY** yapısını işaret eder. **iItem** üyesi eklenecek düğmenin sıfır tabanlı dizinini içerir. Verilen düğmenin önüne bir düğme nin takılmasına izin vermek için **TRUE'yu** döndürün veya düğmenin takılmasını önlemek için **FALSE'u** ekleyin.

- **TBN_RESET**

   Kullanıcı Araç Çubuğu'nu Özelleştir iletişim kutusunun içeriğini sıfırladığında gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **NMHDR** yapısını işaret eder. Işleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_TOOLBARCHANGE**

   Kullanıcı bir araç çubuğu denetimini özelleştirdikten sonra gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **NMHDR** yapısını işaret eder. Işleyicinin belirli bir değeri döndürmesi gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
