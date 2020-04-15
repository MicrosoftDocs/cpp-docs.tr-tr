---
title: COlePropertiesDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: f065894ff49af755ab4020f71b0213b19db49054
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374891"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog Sınıfı

Windows ortak OLE Nesne Özellikleri iletişim kutusunu kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Bir `COlePropertiesDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Belge öğesinin ölçekleme değişti framework tarafından çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|Bir nesnenin "Genel" sayfasını başlatmada `COlePropertiesDialog` kullanılan bir yapı.|
|[COlePropertiesDialog::m_lp](#m_lp)|Bir nesnenin "Bağlantı" sayfasını başlatmada `COlePropertiesDialog` kullanılan bir yapı.|
|[COlePropertiesDialog::m_op](#m_op)|Nesneyi başlatmada kullanılan `COlePropertiesDialog` bir yapı.|
|[COlePropertiesDialog::m_psh](#m_psh)|Ek özel özellik sayfaları eklemek için kullanılan bir yapı.|
|[COlePropertiesDialog::m_vp](#m_vp)|Bir nesnenin "Görünüm" sayfasını özelleştirmek `COlePropertiesDialog` için kullanılan yapı.|

## <a name="remarks"></a>Açıklamalar

Yaygın OLE Nesne Özellikleri iletişim kutuları, Bir OLE belge öğesinin özelliklerini Windows standartlarına uygun bir şekilde görüntülemenin ve değiştirmenin kolay bir yolunu sağlar. Bu özellikler arasında, diğerlerinin yanı sıra, belge öğesi tarafından temsil edilen dosyadaki bilgiler, simge ve görüntü ölçeklemegörüntüleme seçenekleri ve öğenin bağlantısındaki bilgiler (öğe bağlıysa) yer almaktadır.

Bir `COlePropertiesDialog` nesneyi kullanmak için önce `COlePropertiesDialog` oluşturucuyu kullanarak nesneyi oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim `DoModal` kutusunu görüntülemek için üye işlevi arayın ve kullanıcının öğenin özelliklerini değiştirmesine izin verin. `DoModal`kullanıcıok (IDOK) veya İptal (IDCANCEL) düğmesini seçip seçmediğini döndürür. Tamam ve İptal düğmelerine ek olarak bir Uygula düğmesi de vardır. Kullanıcı Uygula'yı seçtiğinde, belge öğesinin özelliklerinde yapılan değişiklikler öğeye uygulanır ve görüntüsü otomatik olarak güncelleştirilir, ancak etkin kalır.

[m_psh](#m_psh) veri üyesi bir `PROPSHEETHEADER` yapıiçin bir işaretçidir ve çoğu durumda bu yapıya açıkça erişmeniz gerekmez. Özel bir durum, varsayılan Genel, Görünüm ve Bağlantı sayfalarının ötesinde ek özellik sayfalarına ihtiyaç duymanızdır. Bu durumda, `m_psh` `DoModal` üye işlevini aramadan önce veri üyesini özel sayfalarınızı içerecek şekilde değiştirebilirsiniz.

OLE iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog

Bir `COlePropertiesDialog` nesnesi oluşturur.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Özelliklerine erişilen belge öğesiiçin işaretçi.

*nScaleMin*<br/>
Belge öğesi görüntüsü için minimum ölçekleme yüzdesi.

*nScaleMax*<br/>
Belge öğesi görüntüsü için maksimum ölçekleme yüzdesi.

*pParentWnd*<br/>
İletişim kutusunun üst öğesine veya sahibine işaretçi.

### <a name="remarks"></a>Açıklamalar

Belge öğeleriniz için ölçekleme uygulamak `COlePropertiesDialog` için ortak OLE Nesne Özellikleri iletişim sınıfınızı türetin. Bu sınıfın bir örneği tarafından uygulanan tüm iletişim kutuları belge öğesinin ölçeklemesini desteklemez.

Varsayılan olarak, ortak OLE Nesne Özellikleri iletişim kutusunda üç varsayılan sayfa vardır:

- Genel

   Bu sayfa, seçili belge öğesi tarafından temsil edilen dosyanın sistem bilgilerini içerir. Bu sayfadan, kullanıcı seçili öğeyi başka bir türe dönüştürebilir.

- Görünüm

   Bu sayfa, öğeyi görüntülemek, simgeyi değiştirmek ve görüntünün ölçeklemesini değiştirmek için seçenekler içerir.

- Bağlantı

   Bu sayfa, bağlı öğenin konumunu değiştirmek ve bağlı öğeyi güncelleştirmek için seçenekler içerir. Bu sayfadan, kullanıcı seçili öğenin bağlantısını kırabilir.

Varsayılan olarak sağlananların ötesine sayfa [m_psh](#m_psh) eklemek için, türetilmiş sınıfınızın `COlePropertiesDialog`oluşturucusundan çıkmadan önce m_psh üye değişkenini değiştirin. Bu `COlePropertiesDialog` yapıcı gelişmiş bir uygulamadır.

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a>COlePropertiesDialog::DoModal

Windows ortak OLE Nesne Özellikleri iletişim kutusunu görüntülemek ve kullanıcının belge öğesinin çeşitli özelliklerini görüntülemesine ve/veya değiştirmesine izin vermek için bu üye işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa İDOK veya IDCANCEL; aksi takdirde 0. IDOK ve IDCANCEL, kullanıcının Ok veya İptal düğmesini seçip seçmediğini gösteren sabitlerdir.

IDCANCEL döndürülürse, bir hata nın oluşup oluşmadığını belirlemek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini arayabilirsiniz.

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp

OLE Object Properties iletişim kutusunun Genel sayfasını açmak için kullanılan [OLEUIGNRLPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw)türünden bir yapı.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, gömme işleminin türünü ve boyutunu gösterir ve kullanıcının Dönüştür iletişim kutusuna erişmesine izin verir. Bu sayfa, nesne bir bağlantı ysa bağlantı hedefini de gösterir.

`OLEUIGNRLPROPS` Yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp

OLE Object Properties iletişim kutusunun Bağlantı sayfasını açmak için kullanılan [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)türünden bir yapı.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, bağlı öğenin konumunu gösterir ve kullanıcının öğeye olan bağlantıyı güncelleştirmesine veya kesmesine olanak tanır.

`OLEUILINKPROPS` Yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a>COlePropertiesDialog::m_op

Ortak OLE Object Properties iletişim kutusunu açmak için kullanılan [OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw)türünden bir yapı.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Açıklamalar

Bu yapı, Genel, Bağlantı ve Görünüm sayfalarını başlatmada kullanılan üyeleri içerir.

Daha fazla bilgi için Windows SDK'daki [OLEUIOBJECTPROPS ve OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw) yapılarına bakın.

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh

Üyeleri iletişim nesnesinin özelliklerini depolayan [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)türünden bir yapı.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Açıklamalar

Bir `COlePropertiesDialog` nesne yaptıktan sonra, `m_psh` `DoModal` üye işlevi aramadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz.

Veri üyesini `m_psh` doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

`PROPSHEETHEADER` Yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp

OLE Object Properties iletişim kutusunun Görünüm sayfasını açmak için kullanılan [OLEUIVIEWPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)türünden bir yapı.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, kullanıcının nesnenin "içerik" ve "ikonik" görünümleri arasında geçiş yapmasına ve kapsayıcı içindeki ölçeklemasını değiştirmesine olanak tanır. Ayrıca, nesne simge olarak görüntülendiğinde kullanıcının Simgedeğiştir iletişim kutusuna erişmesine de izin verir.

`OLEUIVIEWPROPS` Yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale

Ölçekleme değeri değiştiğinde ve Tamam veya Uygula seçildiğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Özelliklerine erişilen belge öğesiiçin işaretçi.

*nCurrentScale*<br/>
İletişim ölçeğinin sayısal değeri.

*bRelativeToOrig*<br/>
Ölçeklemenin belge öğesinin özgün boyutuna uygulanıp uygulanmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Ele alınırsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Ölçekleme denetimlerini etkinleştirmek için bu işlevi geçersiz kılmanız gerekir.

> [!NOTE]
> Ortak OLE Nesne Özellikleri iletişim kutusu görüntülenmeden önce, çerçeve bu işlevi *pItem* için NULL ve *nCurrentScale*için 1 ile çağırır. Bu, ölçekleme denetimlerinin etkin olup olmadığını belirlemek için yapılır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CIRC](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage Sınıfı](../../mfc/reference/cpropertypage-class.md)
