---
title: Cmfcmenubtan sınıfı
ms.date: 07/15/2019
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
- AFXMENUBUTTON/CMFCMenuButton::m_bDefaultClick
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
- CMFCMenuButton [MFC], m_bDefaultClick
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: d7c23cbda0a5af4dc3fa6b2d9f59497acc9bf5ff
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505205"
---
# <a name="cmfcmenubutton-class"></a>Cmfcmenubtan sınıfı

Açılır menüyü ve kullanıcının menü seçimleriyle ilgili raporları görüntüleyen bir düğme.

## <a name="syntax"></a>Sözdizimi

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcmenubtan:: Cmfcmenubtan](#cmfcmenubutton)|Bir `CMFCMenuButton` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcmenubtan::P reTranslateMessage](#pretranslatemessage)|Dağıtılmadan önce pencere iletilerini çevirmek için Framework tarafından çağırılır. (Geçersiz `CMFCButton::PreTranslateMessage`kılmalar.)|
|[Cmfcmenubtan:: SizeToContent](#sizetocontent)|Düğmenin boyutunu metin ve görüntü boyutuna göre değiştirir.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcmenubtan:: m_bOSMenu](#m_bosmenu)|Varsayılan sistem açılır menüsünü mi yoksa [CContextMenuManager:: TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)mi kullanacağınızı belirtir.|
|[Cmfcmenubtan:: m_bRightArrow](#m_brightarrow)|Açılır menünün düğmenin altında mi yoksa sağ tarafında mı görüneceğini belirtir.|
|[Cmfcmenubtan:: m_bStayPressed](#m_bstaypressed)|Kullanıcı düğmeyi güncelleştirdikten sonra menü düğmesinin durumunu değiştirmeyeceğini belirtir.|
|[Cmfcmenubtan:: m_hMenu](#m_hmenu)|Ekli Windows menüsüne yönelik bir tanıtıcı.|
|[Cmfcmenubtan:: m_nMenuResult](#m_nmenuresult)|Kullanıcının açılır menüden hangi öğeyi seçdiğini belirten bir tanımlayıcı.|
|[Cmfcmenubtan:: m_bDefaultClick](#m_bdefaultclick)| Varsayılana izin ver (düğme metin/görüntü üzerinde) işleme.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, [CButton sınıfından](../../mfc/reference/cbutton-class.md)türetilen [CMFCButton sınıfından](../../mfc/reference/cmfcbutton-class.md) türetilir. `CMFCMenuButton` Bu nedenle, kodunuzda kullandığınız `CMFCMenuButton` şekilde `CButton`kullanabilirsiniz.

Bir `CMFCMenuButton`oluşturduğunuzda, ilişkili açılır menüye bir tanıtıcı geçirmeniz gerekir. Sonra, işlevini `CMFCMenuButton::SizeToContent`çağırın. `CMFCMenuButton::SizeToContent`düğme boyutunun, açılır pencerenin göründüğü konuma işaret eden bir ok eklemek için yeterli olup olmadığını denetler (yani, düğmenin altında veya sağında).

## <a name="example"></a>Örnek

Aşağıdaki örnek, düğmesine eklenen menünün tanıtıcısını ayarlamayı, metni metin ve görüntü boyutuna göre yeniden boyutlandırmayı ve Framework tarafından görüntülenen açılır menüyü ayarlamayı gösterir. Bu kod parçacığı, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[Cmfcmenubtan](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenubtan. h

##  <a name="cmfcmenubutton"></a>Cmfcmenubtan:: Cmfcmenubtan

Yeni bir [Cmfcmenubtan](../../mfc/reference/cmfcmenubutton-class.md) nesnesi oluşturur.

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>Cmfcmenubtan:: m_bOSMenu

Çerçevenin görüntülediği açılan menüyü gösteren bir Boolean üye değişkeni.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, çerçeve bu nesne için devralınmış `TrackPopupMenu` yöntemi çağırır. `m_bOSMenu` Aksi halde Framework [CContextMenuManager:: TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)öğesini çağırır.

##  <a name="m_brightarrow"></a>Cmfcmenubtan:: m_bRightArrow

Açılır menünün konumunu gösteren bir Boolean üye değişkeni.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı menü düğmesine bastığında, uygulama bir açılan menü gösterir. Çerçeve, açılır menüyü düğme altında veya düğmenin sağında görüntüler. Düğme, açılan menünün nerede görüneceğini belirten küçük bir oka de sahiptir. TRUE `m_bRightArrow` ise, çerçeve düğmenin sağındaki açılır menüyü görüntüler. Aksi takdirde, düğme altındaki açılır menüyü görüntüler.

##  <a name="m_bstaypressed"></a>Cmfcmenubtan:: m_bStayPressed

Kullanıcı açılır menüden seçim yaptığında menü düğmesinin basılı görünüp başlatılmayacağını gösteren bir Boolean üye değişkeni.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Açıklamalar

`m_bStayPressed` Üye false ise, kullanımları düğme tıkladığı zaman menü düğmesine basmaz. Bu durumda, çerçeve yalnızca açılan menüyü görüntüler.

`m_bStayPressed` Üye true ise, Kullanıcı düğmeye tıkladığında menü düğmesi basılı hale gelir. Kullanıcı, bir seçim yaparak veya iptal ederek, açılır menüyü kapatana kadar basılı kalır.

##  <a name="m_hmenu"></a>Cmfcmenubtan:: m_hMenu

Eklenen menünün tanıtıcısı.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, Kullanıcı menü düğmesine tıkladığında bu üye değişkeni tarafından belirtilen menüyü görüntüler.

##  <a name="m_nmenuresult"></a>Cmfcmenubtan:: m_nMenuResult

Kullanıcının açılır menüden seçtiği öğeyi gösteren bir tamsayı.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir seçim yapmadan veya bir hata oluşursa, bu üye değişkeninin değeri sıfır olur.

##  <a name="m_bdefaultclick"></a>Cmfcmenubtan:: m_bDefaultClick

Düğme üzerinde metin veya görüntülerin varsayılan işlemesine izin verir.

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>Açıklamalar

M_bDefaultClick ayarının false olarak ayarlanması, düğme üzerinde herhangi bir yere tıkladığınızda düğmenin menüyü göstermesini sağlar.

##  <a name="m_nmenuresult"></a>Cmfcmenubtan:: m_nMenuResult

Kullanıcının açılır menüden seçtiği öğeyi gösteren bir tamsayı.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="pretranslatemessage"></a>Cmfcmenubtan::P reTranslateMessage

Dağıtılmadan önce pencere iletilerini çevirmek için Framework tarafından çağırılır.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
'ndaki İşlenecek iletiyi içeren bir [msg](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İleti çevrilmişse ve dağıtılması gerekiyorsa sıfır dışında; ileti çevrilmişse ve dağıtılması gerekiyorsa 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizetocontent"></a>Cmfcmenubtan:: SizeToContent

Düğmenin boyutunu metin boyutuna ve görüntü boyutuna göre değiştirir.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcOnly*<br/>
'ndaki Bu yöntemin düğmeyi yeniden boyutlandırdığını belirten bir Boole parametresi.

### <a name="return-value"></a>Dönüş Değeri

Düğme için yeni boyutu belirten [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırırsanız ve *bCalcOnly* değeri true ise, `SizeToContent` yalnızca düğmenin yeni boyutunu hesaplar.

Düğmenin yeni boyutu düğme metin, resim ve oka uyacak şekilde hesaplanır. Framework Ayrıca dikey kenar için yatay kenar ve 5 piksel için 10 pikselin önceden tanımlanmış kenar boşluklarına de ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
