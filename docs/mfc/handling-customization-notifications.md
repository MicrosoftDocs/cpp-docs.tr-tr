---
title: Özelleştirme bildirimlerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b95af9c0562c4b3210cbcdd7b9ce6216a5d49fb
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930023"
---
# <a name="handling-customization-notifications"></a>Özelleştirme Bildirimlerini İşleme
Windows araç yaygın bir denetim eklemek, silmek veya araç çubuğu düğmeleri yeniden düzenlemek kullanıcı izin veren bir sistem tanımlı özelleştirme iletişim kutusu dahil olmak üzere yerleşik özelleştirme özelliklere sahiptir. Uygulama, özelleştirme özellikleri kullanılabilir olduğunu ve kullanıcının araç çubuğunu özelleştirebilirsiniz uzantı denetimlerini belirler.  
  
 Bu özelleştirme özellikleri kullanılabilir kullanıcıya araç vererek yapabileceğiniz **CCS_ADJUSTABLE** stili. Özelleştirme özelliklerini bir düğme yeni bir konuma sürükleyin ya da bir düğmeyi araç çubuğundan sürükleyerek kaldırmak için verin. Ayrıca, kullanıcı görüntülemek için araç çift tıklayarak **özelleştirme araç** ekleme, silme ve araç çubuğu düğmeleri yeniden düzenlemesine olanak tanır. iletişim kutusu. Uygulamayı kullanarak iletişim kutusunu görüntüleyebilir [Özelleştir](../mfc/reference/ctoolbarctrl-class.md#customize) üye işlevi.  
  
 Araç çubuğu denetimi bildirim iletilerini özelleştirme işlemi her adımda üst penceresine gönderir. Kullanıcı SHIFT tuşunu tutan ve bir düğme sürükleme başlar, araç sürükleme işlemi otomatik olarak yönetir. Araç gönderir **TBN_QUERYDELETE** düğmesi silinebilir olup olmadığını belirlemek için üst pencere bildirim iletisi. Sürükleme işlemi sonlandırır üst pencere döndürürse **FALSE**. Aksi takdirde, araç fare girdisi yakalar ve kullanıcının fare düğmesini serbest bırakmak bekler.  
  
 Kullanıcının fare düğmesini bıraktığında, araç çubuğu denetimi fare imlecini konumunu belirler. İmlecin dışında araç ise, düğme silinir. İmleç üzerinde başka bir araç çubuğu düğmesi ise, araç gönderir **tbn_queryınsert** verilen düğmesinin sola eklenebilir bir düğme belirlemek için üst pencere bildirim iletisi. Üst pencere döndürürse düğmesi eklenir **TRUE**; Aksi takdirde, bu değildir. Araç gönderir **TBN_TOOLBARCHANGE** bildirim iletisi sürükleme işlemi sonuna işaret eder.  
  
 Kullanıcı, SHIFT tuşunu basılı tutarak olmadan bir sürükleme işlemi başladığında, araç çubuğu denetimi gönderir **tbn_begındrag** sahibi pencere bildirim iletisi. Kendi düğmesi sürükleyerek kodu uygulayan bir uygulama bu iletiyi bir sürükleme işlemi başlamak için bir sinyal kullanın. Araç gönderir **TBN_ENDDRAG** bildirim iletisi sürükleme işlemi sonuna işaret eder.  
  
 Kullanıcı bir araç kullanarak özelleştirir zaman bir araç çubuğu denetimi bildirim iletileri gönderir **özelleştirme araç** iletişim kutusu. Araç gönderir **tbn_begınadjust** kullanıcı araç çift tıklamalar, ancak önce iletişim kutusu oluşturulduktan sonra bildirim iletisi. Ardından, bir dizi gönderme araç başlar **tbn_queryınsert** araç çubuğu düğmeleri eklenecek izin verip vermediğini belirlemek için bildirim iletileri. Üst pencere döndüğünde **TRUE**, araç durdurur gönderme **tbn_queryınsert** bildirim iletileri. Üst pencere oluşmazsa **TRUE** herhangi bir düğmesini araç iletişim kutusu yok eder.  
  
 Ardından, araç çubuğu denetimi düğmeleri araç çubuğundaki bir göndererek silinebilir varsa belirler **TBN_QUERYDELETE** her düğmesi için araç çubuğunda bildirim iletisi. Üst pencere döndürür **TRUE** bir düğme olabileceğini Silinen; aksi takdirde belirtmek için bunu döndürür **FALSE**. Araç çubuğu tüm araç çubuğu düğmelerini iletişim kutusuna ekler, ancak silinemez o gri görüntüler.  
  
 Araç çubuğu denetimi araç çubuğunu Özelleştir iletişim kutusunda bir düğme hakkında bilgi her gerektiğinde, gönderir **tbn_getbuttonınfo** kendisi için gereksinim duyduğu bilgileri düğmesinin dizin belirten uyarı iletisi ve adresini bir **TBNOTIFY** yapısı. Üst pencere ilgili bilgilerle yapısı doldurmanız gerekir.  
  
 **Özelleştirme araç** iletişim kutusu, bir Yardım düğmesi ve Sıfırla düğmesi içerir. Kullanıcı Yardım düğmesini seçtiğinde, araç çubuğu denetimi gönderir **TBN_CUSTHELP** bildirim iletisi. Üst pencere Yardım bilgileri görüntüleyerek yanıt vermesi gerekir. İletişim kutusu gönderir **TBN_RESET** kullanıcı Sıfırla düğmesini seçtiğinde bildirim iletisi. Bu ileti, araç hakkında iletişim kutusunu yeniden başlatmak için durumda olduğunu bildirir.  
  
 Bu iletiler tüm **wm_notıfy** iletileri ve işlenebilir sahibi pencerenizde sahibi pencerenin ileti eşlemesi için aşağıdaki formu ileti eşleme girişlerinin ekleyerek:  
  
 `ON_NOTIFY( wNotifyCode, idControl, memberFxn )`  
  
 `wNotifyCode`  
 Bildirim iletisi tanımlayıcı kod gibi **tbn_begınadjust**.  
  
 `idControl`  
 Bildirim göndererek denetim tanımlayıcısı.  
  
 `memberFxn`  
 Bu bildirim alındığında çağrılacak üye işlevi.  
  
 Üye işlevi ile aşağıdaki prototip bildirilmesi:  
  
 `afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );`  
  
 Bildirim ileti işleyicisi bir değer döndürürse, bunu koymak **LRESULT** gösterdiği *sonuç*.  
  
 Her ileti için `pNotifyStruct` ya da işaret eden bir **NMHDR** yapısı veya **TBNOTIFY** yapısı. Bu yapıları aşağıda açıklanmıştır:  
  
 **NMHDR** yapısı aşağıdaki üyeleri içerir:  
  
 `typedef struct tagNMHDR {`  
  
 `HWND hwndFrom;  // handle of control sending message`  
  
 `UINT idFrom;// identifier of control sending message`  
  
 `UINT code;  // notification code; see below`  
  
 `} NMHDR;`  
  
 **hwndFrom**  
 Bildirim göndererek denetimin pencere tanıtıcısı. Bu tanıtıcıyı dönüştürmek için bir `CWnd` işaretçi, kullanım [CWnd::FromHandle](../mfc/reference/cwnd-class.md#fromhandle).  
  
 **idFrom**  
 Bildirim göndererek denetim tanımlayıcısı.  
  
 **Kod**  
 Bildirim kodu. Bu üye denetim türü için belirli bir değer gibi olabilir **tbn_begınadjust** veya **TTN_NEEDTEXT**, veya aşağıda listelenen ortak bildirim değerlerden biri olabilir:  
  
-   **Nm_clıck** kullanıcı denetimi içinde sol fare düğmesini tıklamıştır.  
  
-   **NM_DBLCLK** kullanıcı denetimi içinde sol fare düğmesini çift.  
  
-   **Nm_kıllfocus** denetimi giriş odağını kaybetmiş.  
  
-   **NM_OUTOFMEMORY** denetimi kullanılabilir yeterli bellek olmadığından bir işlem tamamlanamadı.  
  
-   **Nm_rclıck** kullanıcı denetimi içinde sağ fare düğmesini tıklamıştır.  
  
-   **NM_RDBLCLK** kullanıcı denetimi içinde sağ fare düğmesini çift.  
  
-   **NM_RETURN** giriş odağı denetimi sahip ve kullanıcı ENTER tuşuna basıldığında.  
  
-   **NM_SETFOCUS** giriş odağı denetimi aldı.  
  
 **TBNOTIFY** yapısı aşağıdaki üyeleri içerir:  
  
 `typedef struct {`  
  
 `NMHDR hdr; // information common to all WM_NOTIFY messages`  
  
 `int iItem; // index of button associated with notification`  
  
 `TBBUTTON tbButton; // info about button associated withnotification`  
  
 `int cchText;   // count of characters in button text`  
  
 `LPSTR lpszText;// address of button text`  
  
 `} TBNOTIFY, FAR* LPTBNOTIFY;`  
  
## <a name="remarks"></a>Açıklamalar  
 **HDR**  
 Tüm ortak bilgiler **wm_notıfy** iletileri.  
  
 **iItem**  
 Bildirim ile ilişkilendirilmiş düğmesi dizini.  
  
 **tbButton**  
 **TBBUTTON** araç çubuğu düğmesi hakkında bilgi içeren yapısı bildirim ile ilişkilendirilmiş.  
  
 **cchText**  
 Düğme metni karakter sayısı.  
  
 **lpszText**  
 Düğme metni işaretçi.  
  
 Araç gönderir bildirimleri aşağıdaki gibidir:  
  
-   **Tbn_begınadjust** kullanıcı bir araç çubuğu denetimi özelleştirme başladığında gönderilir. İşaretçi işaret bir **NMHDR** bildirimi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **Tbn_begındrag** kullanıcı bir araç çubuğu denetiminde bir düğme sürükleme başladığında gönderilir. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren sürüklenen düğmesi sıfır tabanlı dizini. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **TBN_CUSTHELP** kullanıcı araç çubuğunu Özelleştir iletişim kutusunda Yardım düğmesini seçtiğinde gönderilir. Dönüş değeri yok. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **TBN_ENDADJUST** kullanıcı bir araç çubuğu denetimi özelleştirme durduğunda gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **TBN_ENDDRAG** kullanıcı bir araç çubuğu denetiminde bir düğme sürükleme durduğunda gönderilir. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren sürüklenen düğmesi sıfır tabanlı dizini. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **Tbn_getbuttonınfo** kullanıcı bir araç çubuğu denetimi özelleştirirken gönderilir. Araç çubuğu araç çubuğunu Özelleştir iletişim kutusu tarafından gerekli bilgileri almak için bu bildirim iletisi kullanır. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üye bir düğme sıfır tabanlı dizini belirtir. **PszText** ve **cchText** üyeleri, geçerli düğme metni karakter uzunluğu ve adresini belirtin. Bir uygulama yapısı düğmesi hakkında bilgi ile doldurmanız gerekir. Dönüş **TRUE** düğmesi bilgileri yapısına kopyaladıysanız veya **FALSE** Aksi takdirde.  
  
-   **TBN_QUERYDELETE** kullanıcı bir düğme araç denetimden silinmiş olup olmadığını belirlemek için bir araç çubuğunu özelleştirme gönderilen. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren silinecek düğmesi sıfır tabanlı dizini. Dönüş **TRUE** silinecek düğmesine izin vermek veya **FALSE** silinmesini düğmesi engellemek için.  
  
-   **Tbn_queryınsert** kullanıcı bir düğme verilen düğmesinin sola eklenmiş olup olmadığını belirlemek için bir araç çubuğu denetimi özelleştirme gönderilen. İşaretçi işaret bir **TBNOTIFY** yapısı. **İItem** üyeyi içeren düğmesi eklenecek sıfır tabanlı dizini. Dönüş **TRUE** önünde verilen düğmesi eklenecek bir düğme izin vermek veya **FALSE** eklenen gelen düğmesi engellemek için.  
  
-   **TBN_RESET** içeriği araç çubuğunu Özelleştir iletişim kutusu, kullanıcı sıfırlandıktan sonra gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
-   **TBN_TOOLBARCHANGE** kullanıcı bir araç çubuğu denetimi özelleştirildi sonra gönderilir. İşaretçi işaret bir **NMHDR** bildirim iletisi hakkında bilgi içeren yapısı. İşleyicinin belirli bir değeri döndürme gerekmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

