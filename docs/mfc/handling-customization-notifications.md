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
ms.openlocfilehash: f73e6ef070177f39bdf2e0736660f8eb963727ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462740"
---
# <a name="handling-customization-notifications"></a>Özelleştirme Bildirimlerini İşleme

Windows araç çubuğu ortak denetim eklemek, silmek veya yeniden düzenleme araç çubuğu düğmeleri kullanıcıya izin veren bir sistem tarafından tanımlanan özelleştirme iletişim kutusunda da dahil olmak üzere yerleşik özelleştirme özelliklerine sahiptir. Uygulamayı özelleştirme özellikleri mevcuttur ve kullanıcı araç çubuğunu özelleştirme uzantı denetimlerini belirler.

Bu özelleştirme özellikleri kullanılabilir kullanıcıya araç vererek yapabileceğiniz **CCS_ADJUSTABLE** stili. Özelleştirme özellikleri, kullanıcının bir düğmeyi yeni bir konuma sürükleyin ya da düğme araç çubuğundan sürükleyerek kaldırmak için verin. Ayrıca, kullanıcının görüntülemek için araç çubuğunda çift tıklayabilirsiniz **araç çubuğunu Özelleştir** iletişim kutusunu eklemek, silmek ve araç çubuğu düğmeleri yeniden izin verir. Uygulamayı kullanarak iletişim kutusunu görüntüleyebilirsiniz [Özelleştir](../mfc/reference/ctoolbarctrl-class.md#customize) üye işlevi.

Araç çubuğu denetimi bildirim iletilerini özelleştirme işlemi her bir adımı üst penceresine gönderir. Kullanıcı tutan SHIFT tuşunu ve bir düğmeyi sürükleyip başlar, araç sürükleme işlemi otomatik olarak işler. Araç gönderir **TBN_QUERYDELETE** düğmenin silinmiş olabileceğini belirlemek için bildirim iletisi üst pencere. Sürükleme işlemi sonlandırır üst pencere döndürürse **FALSE**. Aksi takdirde, araç fare girişi yakalar ve kullanıcının fare düğmesini serbest bırakmak bekler.

Kullanıcı fare düğmesini bıraktığında araç çubuğu denetimi fare imlecini konumunu belirler. İmleç bir araç çubuğu ise, düğmeyi silinir. İmleç başka bir araç çubuğu düğmesini ise, araç gönderir **tbn_queryınsert** belirtilen düğmenin soluna bir düğme eklenen olmadığını belirlemek için bildirim iletisi üst pencere. Üst pencere döndürürse düğme eklenir **TRUE**; Aksi takdirde, bu değildir. Araç gönderir **TBN_TOOLBARCHANGE** sürükleme işlemi sonuna belirten uyarı iletisi.

Kullanıcı bir sürükleme işlemi SHIFT tuşunu basılı tutulmadan başlıyorsa, araç çubuğu denetimi gönderir **tbn_begındrag** sahip penceresine bir bildirim iletisi. Düğme sürükleyerek kendi kod uygulayan bir uygulama bu iletiyi bir sürükleme işlemi başlatmak için bir sinyal kullanabilirsiniz. Araç gönderir **TBN_ENDDRAG** sürükleme işlemi sonuna belirten uyarı iletisi.

Kullanıcı bir araç kullanarak özelleştirir araç çubuğu denetimi bildirim iletilerini gönderir **araç çubuğunu Özelleştir** iletişim kutusu. Araç gönderir **tbn_begınadjust** araç çubuğu kullanıcı çift tıkladığında, ancak önce iletişim kutusu oluşturulduktan sonra bildirim iletisi. Ardından, bir dizi gönderme araç başlar **tbn_queryınsert** araç çubuğu düğmeleri eklenecek izin verip vermeyeceğini belirlemek için bildirim iletileri. Üst pencere döndürdüğünde **TRUE**, araç durdurur gönderme **tbn_queryınsert** bildirim iletileri. Üst pencere oluşmazsa **TRUE** herhangi bir düğmesini araç çubuğu iletişim kutusunu yok eder.

Ardından, herhangi bir düğme araç çubuğundan bir göndererek silinebilir, araç çubuğu denetimi belirler **TBN_QUERYDELETE** araç çubuğunda her düğme için bildirim iletisi. Üst pencereyi döndürür **TRUE** bir düğme olabileceğini Silinen; aksi takdirde belirtmek için döndürdüğü **FALSE**. Araç çubuğu iletişim kutusuna tüm araç çubuğu düğmeleri ekler, ancak silinemez o gri görüntüler.

Araç çubuğu denetimi araç çubuğu özelleştirme iletişim kutusunda bir düğme hakkında bilgi gerektiğinde, gönderdiği **tbn_getbuttonınfo** bilgi ihtiyaç düğmesi dizinini belirten bir bildirim iletisi ve adresini bir **TBNOTIFY** yapısı. Üst pencere yapısıyla ilgili bilgileri doldurmanız gerekir.

**Araç çubuğunu Özelleştir** iletişim kutusunda Yardım düğmesine ve Sıfırla düğmesi içerir. Kullanıcı Yardım düğmesini seçtiğinde, araç çubuğu denetimi gönderir **TBN_CUSTHELP** bildirim iletisi. Üst pencere Yardım bilgilerini görüntüleyerek yanıt vermesi gerekir. İletişim kutusu gönderir **TBN_RESET** kullanıcı Sıfırla düğmesini seçtiğinde bildirim iletisi. Bu ileti hakkında iletişim kutusunu başlatmak için araç olduğunu bildirir.

Bu iletiler tüm **wm_notıfy** iletileri ve işlenebilir sahibi pencerenizde sahibi pencerenin ileti eşlemesi için ileti eşlemesi girişleri aşağıdaki biçimde ekleyerek:

```cpp
ON_NOTIFY( wNotifyCode, idControl, memberFxn )
```

- **wNotifyCode**

   Bildirim iletisi tanımlayıcı kod gibi **tbn_begınadjust**.

- **idControl**

   Bildirim göndererek denetim tanımlayıcısı.

- **memberFxn**

   Bu bildirim alındığında çağrılacak üye işlevi.

Aşağıdaki prototip ile üye işlevi bildirilmesi:

```cpp
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );
```

Bildirim ileti işleyicisi bir değer döndürüyorsa, bunu, koymak **LRESULT** işaret ettiği *sonucu*.

Her ileti için `pNotifyStruct` işaret ya da bir **NMHDR** yapısı veya **TBNOTIFY** yapısı. Bu yapılar, aşağıda açıklanmıştır:

**NMHDR** yapısı aşağıdaki üyeleri içerir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;  // handle of control sending message
    UINT idFrom;// identifier of control sending message
    UINT code;  // notification code; see below
} NMHDR;
```

- **hwndFrom**

   Bildirim göndererek denetim pencere tanıtıcısı. Bu tanıtıcıya dönüştürmek için bir `CWnd` işaretçisi, kullanım [CWnd::FromHandle](../mfc/reference/cwnd-class.md#fromhandle).

- **idFrom**

   Bildirim göndererek denetim tanımlayıcısı.

- **Kod**

   Uyarı kodu. Bu üye gibi bir denetim türü için belirli bir değer olabilir **tbn_begınadjust** veya **TTN_NEEDTEXT**, aşağıda listelenen yaygın bildirim değerlerden biri olabilir:

   - **Nm_clıck** kullanıcı denetiminde farenin sol düğmesine tıkladı.

   - **NM_DBLCLK** kullanıcı denetiminde farenin sol düğmesine çift tıklandığında.

   - **Nm_kıllfocus** denetim, giriş odağını kaybetmiş.

   - **NM_OUTOFMEMORY** denetimi yeterli bellek olmadığından bir işlem tamamlanamadı.

   - **Nm_rclıck** kullanıcı denetiminde sağ fare düğmesine tıkladı.

   - **NM_RDBLCLK** kullanıcı denetiminde sağ fare düğmesine çift tıklandığında.

   - **NM_RETURN** denetimin Girintiyi aldığını ve kullanıcının ENTER tuşuna bastığını.

   - **NM_SETFOCUS** denetimin Girintiyi aldı.

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

- **HDR**

   Tüm ortak bilgiler **wm_notıfy** iletileri.

- **iItem**

   Bildirim ile ilişkilendirilmiş düğmesi dizini.

- **tbButton**

   **TBBUTTON** araç çubuğu düğmesini hakkında bilgi içeren yapı bildirim ile ilişkili.

- **cchText**

   Düğme metnini karakter sayısı.

- **lpszText**

   Düğme metnini işaretçisi.

Araç gönderir bildirimleri aşağıdaki gibidir:

- **TBN_BEGINADJUST**

   Kullanıcı bir araç çubuğu denetimini özelleştirme başladığında gönderilir. İşaretçi işaret bir **NMHDR** bildirim hakkında bilgi içeren yapısı. İşleyicinin belirli bir değer gerektirmez.

- **TBN_BEGINDRAG**

   Kullanıcı bir düğmeyi bir araç çubuğu denetiminde sürükleme başladığında gönderilir. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren sürüklenen düğmesi sıfır tabanlı dizini. İşleyicinin belirli bir değer gerektirmez.

- **TBN_CUSTHELP**

   Kullanıcı araç çubuğunu Özelleştir iletişim kutusundaki Yardım düğmesini seçtiğinde gönderilir. Dönüş değeri yok. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değer gerektirmez.

- **TBN_ENDADJUST**

   Kullanıcı bir araç çubuğu denetimini özelleştirme durduğunda gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değer gerektirmez.

- **TBN_ENDDRAG**

   Kullanıcı bir düğmeyi bir araç çubuğu denetiminde sürükleme durduğunda gönderilir. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren sürüklenen düğmesi sıfır tabanlı dizini. İşleyicinin belirli bir değer gerektirmez.

- **TBN_GETBUTTONINFO**

   Kullanıcı bir araç çubuğu denetiminin özelleştirirken gönderilir. Araç çubuğu araç çubuğunu Özelleştir iletişim kutusu tarafından gerekli bilgileri almak için bu bildirim iletisi kullanır. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üye bir düğme sıfır tabanlı dizini belirtir. **PszText** ve **cchText** üyeleri, geçerli düğme metnini karakter uzunluğu ve adresi belirtin. Uygulama düğmesi hakkında bilgi içeren yapı doldurmanız gerekir. Dönüş **TRUE** düğme bilgisi yapısına kopyalanmadıysa veya **FALSE** Aksi takdirde.

- **TBN_QUERYDELETE**

   Kullanıcı bir düğmeyi bir araç çubuğu denetimi silinebilir olup olmadığını belirlemek için bir araç çubuğunu özelleştiriyorken gönderilir. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren silinecek düğmenin sıfır tabanlı dizini. Dönüş **TRUE** silinmesi için düğmesine izin vermek veya **FALSE** düğme silinmesini önlemek için.

- **TBN_QUERYINSERT**

   Kullanıcı, belirtilen düğmenin soluna bir düğme takılı olup olmadığını belirlemek için bir araç çubuğu denetimi özelleştirme Gönder. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren düğmeye eklenecek sıfır tabanlı dizini. Dönüş **TRUE** önüne belirli düğmesi eklenecek bir düğme izin vermek veya **FALSE** düğme önlemek için.

- **TBN_RESET**

   Kullanıcı araç çubuğunu Özelleştir iletişim kutusu içeriği sıfırlandıktan sonra gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değer gerektirmez.

- **TBN_TOOLBARCHANGE**

   Kullanıcı bir araç çubuğu denetiminin özelleştirdi sonra gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değer gerektirmez.

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

