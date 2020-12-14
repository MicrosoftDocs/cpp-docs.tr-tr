---
description: 'Daha fazla bilgi edinin: Cotapropertiesdialog sınıfı'
title: Cotapropertiesdialog sınıfı
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
ms.openlocfilehash: f0c102412f422ff0eabc9f1ff8e19901845905e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226772"
---
# <a name="colepropertiesdialog-class"></a>Cotapropertiesdialog sınıfı

Windows ortak OLE nesne özellikleri iletişim kutusunu kapsüller.

## <a name="syntax"></a>Syntax

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotapropertiesdialog:: Cotapropertiesdialog](#colepropertiesdialog)|Bir `COlePropertiesDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotapropertiesdialog::D oModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[Cotapropertiesdialog:: OnApplyScale](#onapplyscale)|Belge öğesinin ölçeklendirilmesi değiştiğinde Framework tarafından çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet Propertiesdialog:: m_gp](#m_gp)|Bir nesnenin "genel" sayfasını başlatmak için kullanılan bir yapı `COlePropertiesDialog` .|
|[Colet Propertiesdialog:: m_lp](#m_lp)|Bir nesnenin "bağlantı" sayfasını başlatmak için kullanılan bir yapı `COlePropertiesDialog` .|
|[Colet Propertiesdialog:: m_op](#m_op)|Nesneyi başlatmak için kullanılan bir yapı `COlePropertiesDialog` .|
|[Colet Propertiesdialog:: m_psh](#m_psh)|Ek özel özellik sayfaları eklemek için kullanılan bir yapı.|
|[Colet Propertiesdialog:: m_vp](#m_vp)|Bir nesnenin "Görünüm" sayfasını özelleştirmek için kullanılan bir yapı `COlePropertiesDialog` .|

## <a name="remarks"></a>Açıklamalar

Ortak OLE nesne özellikleri iletişim kutuları, bir OLE belge öğesinin özelliklerini Windows standartlarıyla tutarlı bir şekilde görüntülemenin ve değiştiremenin kolay bir yolunu sunar. Bu özellikler arasında, diğerlerinin yanı sıra belge öğesiyle temsil edilen dosya hakkındaki bilgiler, simge ve görüntü ölçeklendirmeyi görüntüleme seçenekleri ve öğenin bağlantısı (öğe bağlantılıysa) hakkında bilgiler yer alır.

Bir nesnesi kullanmak için `COlePropertiesDialog` , önce oluşturucuyu kullanarak nesnesini oluşturun `COlePropertiesDialog` . İletişim kutusu oluşturulduktan sonra, `DoModal` iletişim kutusunu göstermek ve kullanıcının öğenin herhangi bir özelliğini değiştirmesine izin vermek için üye işlevini çağırın. `DoModal` kullanıcının Tamam (IDOK) mi yoksa Iptal (ıDCANCEL) düğmesini mi seçmediğini döndürür. Tamam ve Iptal düğmelerine ek olarak, bir Uygula düğmesi vardır. Kullanıcı Uygula ' yı seçtiğinde, belge öğesinin özelliklerinde yapılan tüm değişiklikler öğeye uygulanır ve görüntüsü otomatik olarak güncelleştirilir, ancak etkin kalır.

[M_psh](#m_psh) veri üyesi bir yapıya yönelik bir işaretçidir `PROPSHEETHEADER` ve çoğu durumda açıkça erişmeniz gerekmez. Bir özel durum, varsayılan genel, görünüm ve bağlantı sayfalarının ötesinde ek özellik sayfalarına ihtiyacınız olduğunda olur. Bu durumda, `m_psh` üye işlevini çağırmadan önce, veri üyesini özel sayfalarınızı içerecek şekilde değiştirebilirsiniz `DoModal` .

OLE iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a> Cotapropertiesdialog:: Cotapropertiesdialog

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
Özelliklerine erişilmekte olan belge öğesine yönelik işaretçi.

*nScaleMin*<br/>
Belge öğesi görüntüsü için minimum ölçekleme yüzdesi.

*nScaleMax*<br/>
Belge öğesi görüntüsü için ölçek yüzdesi üst sınırı.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahibine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

`COlePropertiesDialog`Belge öğelerinize yönelik ölçeklendirmeyi uygulamak için ortak OLE nesne özellikleri iletişim sınıfınızı ' dan türetirsiniz. Bu sınıfın bir örneği tarafından uygulanan iletişim kutuları, belge öğesinin ölçeklendirilmesini desteklemez.

Varsayılan olarak, ortak OLE nesne özellikleri iletişim kutusunda üç varsayılan sayfa bulunur:

- Genel

   Bu sayfa, seçilen belge öğesiyle temsil edilen dosya için sistem bilgilerini içerir. Bu sayfadan, Kullanıcı seçili öğeyi başka bir türe dönüştürebilir.

- Görüntüle

   Bu sayfa, öğeyi görüntüleme, simgeyi değiştirme ve görüntünün ölçeklendirilmesini değiştirme seçeneklerini içerir.

- Bağlantı

   Bu sayfa, bağlantılı öğenin konumunu değiştirme ve bağlantılı öğeyi güncelleştirme seçeneklerini içerir. Bu sayfadan, Kullanıcı seçili öğenin bağlantısını kesebilir.

Varsayılan olarak sağlananlardan daha fazla sayfa eklemek için, türetilmiş sınıfınızın oluşturucusundan çıkmadan önce [m_psh](#m_psh) üye değişkenini değiştirin `COlePropertiesDialog` . Bu, oluşturucunun gelişmiş bir uygulamasıdır `COlePropertiesDialog` .

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a> Cotapropertiesdialog::D oModal

Windows ortak OLE nesne özellikleri iletişim kutusunu görüntülemek ve kullanıcının belge öğesinin çeşitli özelliklerini görüntülemesine ve/veya değiştirmesine izin vermek için bu üye işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ıDOK veya ıDCANCEL; Aksi takdirde 0. IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını anlamak için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırabilirsiniz.

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a> Colet Propertiesdialog:: m_gp

OLE nesne özellikleri iletişim kutusunun Genel sayfasını başlatmak için kullanılan [Oleumenrlprops](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw)türünde bir yapı.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfada bir katıştırma türü ve boyutu gösterilir ve kullanıcının Dönüştür iletişim kutusuna erişimine izin verir. Bu sayfa, nesne bir bağlantıdır bağlantı hedefini de gösterir.

Yapı hakkında daha fazla bilgi için `OLEUIGNRLPROPS` Windows SDK bakın.

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a> Colet Propertiesdialog:: m_lp

OLE nesne özellikleri iletişim kutusunun Bağlantı sayfasını başlatmak için kullanılan [Oleuilınkprops](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)türünde bir yapı.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, bağlantılı öğenin konumunu gösterir ve kullanıcının öğenin bağlantısını güncelleştirmesine veya kesmesine izin verir.

Yapı hakkında daha fazla bilgi için `OLEUILINKPROPS` Windows SDK bakın.

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a> Colet Propertiesdialog:: m_op

Ortak OLE nesne özellikleri iletişim kutusunu başlatmak için kullanılan [OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw)türünde bir yapı.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Açıklamalar

Bu yapı, genel, bağlantı ve görünüm sayfalarını başlatmak için kullanılan üyeleri içerir.

Daha fazla bilgi için Windows SDK OLEUıOBJECTPROPS ve [Oleuilınkprops](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw) yapılarına bakın.

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a> Colet Propertiesdialog:: m_psh

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan [propsheetheader](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)türünde bir yapı.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `COlePropertiesDialog` , `m_psh` üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz `DoModal` .

`m_psh`Veri üyesini doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

Yapı hakkında daha fazla bilgi için `PROPSHEETHEADER` Windows SDK bakın.

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a> Colet Propertiesdialog:: m_vp

OLE nesne özellikleri iletişim kutusunun Görünüm sayfasını başlatmak için kullanılan [Oleuıviewprops](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)türünde bir yapı.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Açıklamalar

Bu sayfa, kullanıcının nesnenin "içerik" ve "ıfer" görünümleri arasında geçiş yapmasına ve kapsayıcının içindeki ölçeklendirmeyi değiştirmesine olanak tanır. Ayrıca, nesne bir simge olarak görüntülenirken kullanıcının simge Değiştir iletişim kutusuna erişimine izin verir.

Yapı hakkında daha fazla bilgi için `OLEUIVIEWPROPS` Windows SDK bakın.

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a> Cotapropertiesdialog:: OnApplyScale

Ölçeklendirme değeri değiştiği ve Tamam ya da Uygula seçili olduğunda Framework tarafından çağırılır.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Özelliklerine erişilmekte olan belge öğesine yönelik işaretçi.

*nCurrentScale*<br/>
İletişim kutusu ölçeğinin sayısal değeri.

*Brelativetocumg*<br/>
Ölçeklendirmenin belge öğesinin özgün boyutuna uygulanıp uygulanmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Ölçeklendirme denetimlerini etkinleştirmek için bu işlevi geçersiz kılmanız gerekir.

> [!NOTE]
> Ortak OLE nesne özellikleri iletişim kutusu görüntülenmeden önce, çerçeve bu işlevi *pItem* için null ve *nCurrentScale* için-1 ile çağırır. Bu, ölçeklendirme denetimlerinin etkinleştirilip etkinleştirilmeyeceğini tespit etmek için yapılır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CIRC](../../overview/visual-cpp-samples.md)<br/>
[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage sınıfı](../../mfc/reference/cpropertypage-class.md)
