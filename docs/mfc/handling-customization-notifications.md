---
description: 'Daha fazla bilgi edinin: özelleştirme bildirimlerini Işleme'
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
ms.openlocfilehash: b5e104f118ac0eeff96965692615ce9143c5c178
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254969"
---
# <a name="handling-customization-notifications"></a>Özelleştirme Bildirimlerini İşleme

Windows Toolbar ortak denetiminde, sistem tanımlı özelleştirme iletişim kutusu da dahil olmak üzere, kullanıcının araç çubuğu düğmelerine ekleme, silme veya yeniden düzenleme izni veren yerleşik özelleştirme özellikleri vardır. Uygulama, özelleştirme özelliklerinin kullanılabilir olup olmadığını belirler ve kullanıcının araç çubuğunu özelleştirebileceği kapsamı denetler.

Araç çubuğuna **CCS_ADJUSTABLE** stili vererek bu özelleştirme özelliklerini Kullanıcı için kullanılabilir hale getirebilirsiniz. Özelleştirme özellikleri, kullanıcının bir düğmeyi yeni bir konuma sürüklemeye veya bir düğmeyi araç çubuğundan sürükleyerek kaldırmasına izin verir. Buna ek olarak, Kullanıcı araç çubuğunu çift tıklatarak araç çubuğu düğmelerini ekleme, silme ve yeniden düzenleme olanağı sunan araç **çubuğunu özelleştirme** iletişim kutusunu görüntüleyebilir. Uygulama, [Özelleştir](reference/ctoolbarctrl-class.md#customize) member işlevini kullanarak iletişim kutusunu görüntüleyebilir.

Araç çubuğu denetimi, her adımda özelleştirme işlemindeki bildirim iletilerini ana pencereye gönderir. Kullanıcı SHIFT tuşunu basılı tutarken bir düğmeyi sürüklemeye başlarsa, araç çubuğu sürükleme işlemini otomatik olarak işler. Araç çubuğu, düğmenin silinip silinemeyeceğini anlamak için **tbn_querydelete** bildirim iletisini ana pencereye gönderir. Üst pencere **false** döndürürse sürükleme işlemi sona erer. Aksi takdirde, araç çubuğu fare girişini yakalar ve kullanıcının fare düğmesini serbest bırakmasını bekler.

Kullanıcı fare düğmesini bıraktığında, araç çubuğu denetimi fare imlecinin konumunu belirler. İmleç araç çubuğunun dışındaysa, düğme silinir. İmleç başka bir araç çubuğu düğesince, araç çubuğu **TBN_QUERYINSERT** bildirim iletisini ana pencereye gönderir ve bu düğmenin soluna bir düğme eklenebilir olup olmadığını tespit edebilir. Üst pencere **doğru** döndürürse düğme eklenir; Aksi takdirde, değildir. Araç çubuğu, sürükleme işleminin sonuna işaret etmek için **tbn_toolbarchange** bildirim iletisi gönderir.

Kullanıcı, SHIFT tuşunu basılı tutarak bir sürükleme işlemine başlarsa, araç çubuğu denetimi **TBN_BEGINDRAG** bildirim iletisini sahip penceresine gönderir. Kendi düğme-sürükleme kodu uygulayan bir uygulama, bir sürükleme işlemine başlamak için bu iletiyi bir sinyal olarak kullanabilir. Araç çubuğu, sürükleme işleminin sonuna işaret etmek için **tbn_enddrag** bildirim iletisi gönderir.

Bir araç çubuğu denetimi, Kullanıcı araç çubuğunu **Özelleştir** iletişim kutusunu kullanarak bir araç çubuğunu özelleştirdikten sonra bildirim iletileri gönderir. Araç çubuğu, Kullanıcı araç çubuğunu çift tıkladıktan sonra, ancak iletişim kutusu oluşturulmadan önce **TBN_BEGINADJUST** bildirim iletisi gönderir. Ardından araç çubuğu bir dizi **TBN_QUERYINSERT** bildirim iletisi göndererek araç çubuğunun düğmelerin eklenmesine izin verip içermediğini tespit etmek için başlar. Üst pencere **doğru** döndürdüğünde, araç çubuğu **TBN_QUERYINSERT** bildirim iletileri göndermeyi sonlandırır. Üst pencere herhangi bir düğme için **doğru** döndürmezse, araç çubuğu iletişim kutusunu yok eder.

Daha sonra, araç çubuğu denetimi araç çubuğundan her düğme için bir **tbn_querydelete** bildirim iletisi göndererek araç çubuğundan herhangi bir düğme silinip silinemeyeceğini belirler. Üst pencere, bir düğmenin silinemeyeceğini belirtmek için **true** değerini döndürür; Aksi takdirde, **false** döndürür. Araç çubuğu düğmeleri iletişim kutusuna ekler, ancak silinmeyebilir.

Araç çubuğu denetimine araç çubuğu iletişim kutusunda bir düğme hakkında bilgi gerektiğinde, bu, bilgi ihtiyacı olan düğmenin dizinini ve bir **Tbnotify** yapısının adresini belirterek **TBN_GETBUTTONINFO** bildirim iletisi gönderir. Üst pencere, yapıyı ilgili bilgilerle doldurmalıdır.

**Araç çubuğunu Özelleştir** iletişim kutusu, bir Yardım düğmesi ve bir sıfırlama düğmesi içerir. Kullanıcı Yardım düğmesini seçtiğinde, araç çubuğu denetimi **tbn_custhelp** bildirim iletisi gönderir. Üst pencere, yardım bilgilerini görüntüleyerek yanıt vermelidir. İletişim kutusu, Kullanıcı sıfırlama düğmesini seçtiğinde **tbn_reset** bildirim iletisi gönderir. Bu ileti, araç çubuğunun iletişim kutusunu yeniden başlatmak üzere olduğunu bildirir.

Bu iletiler tüm **WM_NOTIFY** iletilerdir ve sahip pencerenizde, sahip pencerenizin ileti eşlemesine aşağıdaki formun ileti eşleme girdilerini ekleyerek sahip penceresinde işlenebilir:

```cpp
ON_NOTIFY( wNotifyCode, idControl, memberFxn )
```

- **wNotifyCode**

   **TBN_BEGINADJUST** gibi bildirim iletisi tanımlayıcı kodu.

- **ıdcontrol**

   Bildirimi gönderen denetimin tanımlayıcısı.

- **memberFxn**

   Bu bildirim alındığında çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple bildirilebilecek:

```cpp
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );
```

Bildirim iletisi işleyicisi bir değer döndürürse, bunu *sonuca* göre Işaret eden **LRESULT** öğesine yerleştirmelidir.

Her ileti için, `pNotifyStruct` bir **nmhdr** yapısına veya bir **TBNOTIFY** yapısına işaret eder. Bu yapılar aşağıda açıklanmıştır:

**Nmhdr** yapısı aşağıdaki üyeleri içerir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;  // handle of control sending message
    UINT idFrom;// identifier of control sending message
    UINT code;  // notification code; see below
} NMHDR;
```

- **hwndFrom**

   Bildirimi gönderen denetimin pencere tutamacı. Bu tutamacı bir işaretçiye dönüştürmek için `CWnd` [CWnd:: FromHandle](reference/cwnd-class.md#fromhandle)kullanın.

- **ıdfrom**

   Bildirimi gönderen denetimin tanımlayıcısı.

- **kodudur**

   Bildirim kodu. Bu üye, **TBN_BEGINADJUST** veya **TTN_NEEDTEXT** gibi bir denetim türüne özgü bir değer olabilir veya aşağıda listelenen ortak bildirim değerlerinden biri olabilir:

  - **NM_CLICK** Kullanıcı, denetimin içindeki sol fare düğmesine tıkladı.

  - **NM_DBLCLK** Kullanıcı, denetimin içindeki sol fare düğmesine çift tıklamıştır.

  - **NM_KILLFOCUS** Denetim, giriş odağını kaybetti.

  - **NM_OUTOFMEMORY** Yeterli kullanılabilir bellek olmadığından denetim bir işlemi tamamlayamadı.

  - **NM_RCLICK** Kullanıcı, denetimin içindeki sağ fare düğmesine tıklamıştır.

  - **nm_rdblclk** Kullanıcı, denetimin içindeki sağ fare düğmesine çift tıklamıştır.

  - **NM_RETURN** Denetim, giriş odağa sahiptir ve Kullanıcı ENTER tuşuna basmıştır.

  - **NM_SETFOCUS** Denetim, giriş odağını aldı.

**Tbnotify** yapısı aşağıdaki üyeleri içerir:

```cpp
typedef struct {
    NMHDR hdr; // information common to all WM_NOTIFY messages
    int iItem; // index of button associated with notification
    TBBUTTON tbButton; // info about button associated withnotification
    int cchText;   // count of characters in button text
    LPSTR lpszText;// address of button text
} TBNOTIFY, FAR* LPTBNOTIFY;
```

- **görüntüsünde**

   Tüm **WM_NOTIFY** iletileriyle ortak bilgiler.

- **IItem**

   Bildirimle ilişkili düğme dizini.

- **tbButton**

   Bildirimle ilişkili araç çubuğu düğmesi hakkında bilgi içeren **TBBUTTON** yapısı.

- **cchText**

   Düğme metnindeki karakterlerin sayısı.

- **lpszText**

   Düğme metni işaretçisi.

Araç çubuğunun gönderdiği bildirimler aşağıdaki gibidir:

- **TBN_BEGINADJUST**

   Kullanıcı bir araç çubuğu denetimini özelleştirmeye başladığında gönderilir. İşaretçi, bildirim hakkında bilgi içeren bir **nmhdr** yapısına işaret eder. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_BEGINDRAG**

   Kullanıcı bir araç çubuğu denetimindeki bir düğmeyi sürüklemeye başladığında gönderilir. İşaretçi bir **TBNOTIFY** yapısına işaret eder. **IItem** üyesi, sürüklediğiniz düğmenin sıfır tabanlı dizinini içerir. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_CUSTHELP**

   Kullanıcı araç çubuğunu Özelleştir iletişim kutusunda Yardım düğmesini seçtiğinde gönderilir. Dönüş değeri yok. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **nmhdr** yapısına işaret eder. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_ENDADJUST**

   Kullanıcı bir araç çubuğu denetimini özelleştirmeyi durdurulduğunda gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **nmhdr** yapısına işaret eder. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_ENDDRAG**

   Kullanıcı bir araç çubuğu denetimindeki bir düğmeyi sürüklemeyi durdurduktan sonra gönderilir. İşaretçi bir **TBNOTIFY** yapısına işaret eder. **IItem** üyesi, sürüklediğiniz düğmenin sıfır tabanlı dizinini içerir. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_GETBUTTONINFO**

   Kullanıcı bir araç çubuğu denetimini özelleştirirken gönderilir. Araç çubuğu, özelleştirme araç çubuğu iletişim kutusu tarafından gereken bilgileri almak için bu bildirim iletisini kullanır. İşaretçi bir **TBNOTIFY** yapısına işaret eder. **IItem** üyesi bir düğmenin sıfır tabanlı dizinini belirtir. **PszText** ve **cchText** üyeleri, geçerli düğme metninin adresini ve uzunluğunu karakter olarak belirler. Bir uygulama, düğme hakkındaki bilgilerle yapıyı doldurmalıdır. Düğme bilgileri yapıya kopyalanmışsa **true** , aksi takdirde **false** döndürün.

- **TBN_QUERYDELETE**

   Kullanıcı bir araç çubuğunu özelleştirirken bir araç çubuğu denetiminden bir düğmenin silinip silinemeyeceğini tespit ederken gönderilir. İşaretçi bir **TBNOTIFY** yapısına işaret eder. **IItem** üyesi, silinecek düğmenin sıfır tabanlı dizinini içerir. Düğmenin silinmesine izin vermek için **true** , düğmenin silinmesini engellemek için **false** döndürün.

- **TBN_QUERYINSERT**

   Kullanıcı bir araç çubuğu denetimini özelleştirirken verilen düğmenin soluna bir düğme eklenip eklenemeyeceğini tespit ederken gönderilir. İşaretçi bir **TBNOTIFY** yapısına işaret eder. **IItem** üyesi eklenecek düğmenin sıfır tabanlı dizinini içerir. Düğmeye eklenen düğmenin önüne veya düğmenin eklenmesini engellemek için **false** **döndürün.**

- **TBN_RESET**

   Kullanıcı araç çubuğu özelleştirme iletişim kutusunun içeriğini sıfırladığında gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **nmhdr** yapısına işaret eder. İşleyicinin belirli bir değeri döndürmesi gerekmez.

- **TBN_TOOLBARCHANGE**

   Kullanıcı bir araç çubuğu denetimini özelleştirdikten sonra gönderilir. İşaretçi, bildirim iletisi hakkında bilgi içeren bir **nmhdr** yapısına işaret eder. İşleyicinin belirli bir değeri döndürmesi gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](using-ctoolbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
