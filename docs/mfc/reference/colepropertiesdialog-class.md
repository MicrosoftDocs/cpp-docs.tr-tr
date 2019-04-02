---
title: COlePropertiesDialog sınıfı
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
ms.openlocfilehash: e574f535609ec9401bd76badf11fa7e05cc0c619
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781867"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog sınıfı

Windows ortak OLE nesne özelliği iletişim kutusunu kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Oluşturur bir `COlePropertiesDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmanıza izin verir.|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Belge öğesi ölçeklendirme değiştiğinde framework tarafından çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|"Genel" sayfasını başlatmak için kullanılan bir yapının bir `COlePropertiesDialog` nesne.|
|[COlePropertiesDialog::m_lp](#m_lp)|"Bağlantı" sayfasının başlatmak için kullanılan bir yapının bir `COlePropertiesDialog` nesne.|
|[COlePropertiesDialog::m_op](#m_op)|Başlatmak için kullanılan bir yapının `COlePropertiesDialog` nesne.|
|[COlePropertiesDialog::m_psh](#m_psh)|Ek özel özellik sayfaları eklemek için kullanılan bir yapının.|
|[COlePropertiesDialog::m_vp](#m_vp)|"View" sayfasının özelleştirmek için kullanılan bir yapının bir `COlePropertiesDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

Ortak OLE nesne özelliği iletişim kutusu görüntülemek ve bir OLE belge öğesi Windows standartları ile tutarlı şekilde özelliklerini değiştirmek için kolay bir yol sağlar. Bu özellikler, diğerleriyle birlikte, belge öğesi, (öğe bağlı değilse) simgesini ve görüntü ölçeklendirme ve bilgilerini öğenin bağlantısında görüntüleme seçenekleri tarafından temsil edilen dosyası hakkında bilgi içerir.

Kullanılacak bir `COlePropertiesDialog` nesne, ilk nesnesini kullanarak oluşturun `COlePropertiesDialog` Oluşturucusu. İletişim kutusu oluşturulmuş sonra çağırma `DoModal` iletişim kutusunu görüntülemek ve kullanıcının herhangi bir öğenin özelliklerini değiştirmek izin vermek için üye işlevi. `DoModal` Kullanıcı (IDOK) Tamam veya iptal edin (IDCANCEL) düğmesini seçip seçmediğini döndürür. Tamam ve İptal düğmeleri ek olarak, bir Uygula düğmesi yoktur. Kullanıcı Uygula seçtiğinde belge öğeyi özelliklerine yapılan değişiklikler öğesine uygulanır ve görüntüsünü otomatik olarak güncelleştirilir ancak etkin kalır.

[M_psh](#m_psh) veri üyesi olan bir işaretçi bir `PROPSHEETHEADER` yapısı ve çoğu durumda, zorunda kalmadan açıkça erişim. Varsayılan Genel Görünüm ve bağlantı sayfaları ötesinde ek özellik sayfaları gerektiğinde bir özel durumdur. Bu durumda, değiştirebileceğiniz `m_psh` özel sayfalarınızı çağırmadan önce içerecek şekilde veri üyesi `DoModal` üye işlevi.

OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="colepropertiesdialog"></a>  COlePropertiesDialog::COlePropertiesDialog

Oluşturur bir `COlePropertiesDialog` nesne.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Özellikleri erişilen bir belge öğesinin işaretçisi.

*nScaleMin*<br/>
En az yüzde belge öğesi resmi için ölçeklendirme.

*nScaleMax*<br/>
En fazla belge öğesi resmi yüzdesi ölçeklendirme.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahibi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ortak OLE nesne özelliği iletişim sınıfından türetilir `COlePropertiesDialog` belge öğelerinizi ölçeklendirme uygulamak için. Bu sınıfın bir örneği tarafından uygulanan herhangi bir iletişim kutusu belge öğesi ölçeklendirme desteklemez.

Varsayılan olarak, ortak bir OLE nesne özelliği iletişim kutusu, üç varsayılan sayfası vardır:

- Genel

   Bu sayfa seçilen belge öğesi tarafından temsil edilen dosya sistem bilgilerini içerir. Bu sayfadan kullanıcı seçili öğe başka bir türe dönüştürme yapabilirsiniz.

- Görüntüle

   Bu sayfa görüntüsü ölçeklendirmesinin değişmesi öğesi görüntüleme ve simgesini değiştirme seçenekleri içerir.

- Bağlantı

   Bu sayfa, bağlantılı öğe konumunu değiştirme ve bağlantılı öğeyi güncelleştirmek için seçenekleri içerir. Bu sayfadan kullanıcı seçili öğenin bağlantısını kesebilirsiniz.

Varsayılan olarak sağlananların sayfalar eklemek için değiştirme [m_psh](#m_psh) oluşturucusunun çıkmadan önce üye değişkeni, `COlePropertiesDialog`-türetilmiş sınıf. Bu gelişmiş uygulamasıdır `COlePropertiesDialog` Oluşturucusu.

##  <a name="domodal"></a>  COlePropertiesDialog::DoModal

Windows ortak OLE nesne özelliği iletişim kutusu görüntüler ve kullanıcının görüntülemek ve/veya belge öğesi çeşitli özelliklerini değiştirmek izin vermek için bu üye işlevini çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL başarılıysa; Aksi durumda 0. IDOK ve IDCANCEL kullanıcı Tamam'ı veya iptal düğmesi seçili olup olmadığını gösteren sabittir.

IDCANCEL döndürülürse, Windows çağırabilirsiniz [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) hata oluşup oluşmadığını belirlemek için işlevi.

##  <a name="m_gp"></a>  COlePropertiesDialog::m_gp

Türünden bir yapıyı [OLEUIGNRLPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuignrlpropsa)OLE nesne özelliği iletişim kutusu, genel sayfayı başlatmak için kullanılır.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfada gömme boyutunu ve türünü gösterir ve Dönüştürme iletişim kutusu kullanıcının erişmesini sağlar. Bu sayfa ayrıca bağlantı hedef nesnenin bir bağlantı olup olmadığını gösterir.

Daha fazla bilgi için `OLEUIGNRLPROPS` yapısı, Windows SDK'sı bakın.

##  <a name="m_lp"></a>  COlePropertiesDialog::m_lp

Türünden bir yapıyı [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa)OLE nesne özelliği iletişim kutusunun bağlantı sayfayı başlatmak için kullanılır.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, bağlantılı öğe konumunu gösterir ve güncelleştirme veya öğenin bağlantısını kesen izin verir.

Daha fazla bilgi için `OLEUILINKPROPS` yapısı, Windows SDK'sı bakın.

##  <a name="m_op"></a>  COlePropertiesDialog::m_op

Türünden bir yapıyı [OLEUIOBJECTPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiobjectpropsa)ortak OLE nesne özelliği iletişim kutusunu başlatmak için kullanılır.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Açıklamalar

Bu yapı, genel, bağlantı ve görünüm sayfa başlatmak için kullanılan üyeler içerir.

Daha fazla bilgi için bkz: OLEUIOBJECTPROPS ve [OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa) yapıları, Windows SDK'sı.

##  <a name="m_psh"></a>  COlePropertiesDialog::m_psh

Türünden bir yapıyı [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2), üyeleri iletişim nesnesinin özelliklerini depolayın.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `COlePropertiesDialog` nesne kullanabileceğiniz `m_psh` çeşitli yönlerini çağırmadan önce iletişim kutusunda ayarlanacak `DoModal` üye işlevi.

Değiştirirseniz `m_psh` veri üyesi doğrudan, hiçbir varsayılan davranışı geçersiz kılar.

Daha fazla bilgi için `PROPSHEETHEADER` yapısı, Windows SDK'sı bakın.

##  <a name="m_vp"></a>  COlePropertiesDialog::m_vp

Türünden bir yapıyı [OLEUIVIEWPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiviewpropsa)OLE nesne özelliği iletişim kutusunun görünümü sayfayı başlatmak için kullanılır.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, "içerik" ve nesnenin "icon" görünümler arasında geçiş yapma ve kapsayıcı içinde ölçeklendirme değiştirmek kullanıcı sağlar. Nesne simge olarak görüntülendiğinde de Change Icon iletişim kutusu için kullanıcı erişim sağlar.

Daha fazla bilgi için `OLEUIVIEWPROPS` yapısı, Windows SDK'sı bakın.

##  <a name="onapplyscale"></a>  COlePropertiesDialog::OnApplyScale

Ölçeklendirme değeri değiştirildi ve Tamam'ı veya Uygula seçilmiş framework tarafından çağırılır.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Özellikleri erişilen bir belge öğesinin işaretçisi.

*nCurrentScale*<br/>
İletişim ölçeğin sayısal değer.

*bRelativeToOrig*<br/>
Ölçeklendirme belge öğesi özgün boyutu için geçerli olup olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlenen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz. Ölçeklendirme denetimlerini etkinleştirmek için bu işlevi geçersiz kılmanız gerekir.

> [!NOTE]
>  Ortak OLE nesne özelliği iletişim kutusu görüntülenmeden önce bu işlev için NULL ile framework çağırır *pItem* için - 1 *nCurrentScale*. Bu, ölçeklendirme denetimler etkin olmadığını belirlemek için gerçekleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DAİ](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage Sınıfı](../../mfc/reference/cpropertypage-class.md)
