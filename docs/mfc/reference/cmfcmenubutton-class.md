---
title: CMFCMenuButton Sınıfı
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
ms.openlocfilehash: 929fc1c8166f249fe3babc724b2c0bcd9cb99676
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369678"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton Sınıfı

Açılır menüyü görüntüleyen ve kullanıcının menü seçimlerinde rapor veren bir düğme.

## <a name="syntax"></a>Sözdizimi

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Bir `CMFCMenuButton` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Pencere iletilerini gönderilmeden önce çevirmek için çerçeve tarafından çağrılır. (Geçersiz `CMFCButton::PreTranslateMessage`kılar .)|
|[CMFCMenuButton::SizetoContent](#sizetocontent)|Düğmenin boyutunu metin ve görüntü boyutuna göre değiştirir.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Varsayılan sistem açılır menüsünü mi yoksa [CContextMenuManager::TrackPopUpMenu'yi](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)mi kullanacağımı belirtir.|
|[CMFCMenü Düğmesi::m_bRightArrow](#m_brightarrow)|Açılır menünün düğmenin altında mı yoksa sağında mı görüneceğini belirtir.|
|[CMFCMenü Düğmesi::m_bStayPressed](#m_bstaypressed)|Kullanıcı düğmeyi serbest bıraktıktan sonra menü düğmesinin durumunu değiştirip değiştirmediğini belirtir.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ekli Windows menüsüne bir tanıtıcı.|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Açılan menüden seçilen kullanıcının hangi öğeyi seçtiğini gösteren bir tanımlayıcı.|
|[CMFCMenü Düğmesi::m_bDefaultClick](#m_bdefaultclick)| Varsayılan (düğme metin/resim) işlemeizin verin.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCMenuButton` sırayla [CButton Sınıfından](../../mfc/reference/cbutton-class.md)türetilen [CMFCButton Sınıfından](../../mfc/reference/cmfcbutton-class.md) türetilmiştir. Bu nedenle, `CMFCMenuButton` kodunuzda kullanacağınız şekilde kullanabilirsiniz. `CButton`

Bir `CMFCMenuButton`, tutamaç içinde ilişkili açılır menüsüne geçmek gerekir oluşturduğunuzda. Sonra, işlevi `CMFCMenuButton::SizeToContent`arayın. `CMFCMenuButton::SizeToContent`düğme boyutunun açılır pencerenin görüneceği konuma işaret eden bir ok eklemek için yeterli olduğunu denetler - yani, düğmenin altında veya sağında.

## <a name="example"></a>Örnek

Aşağıdaki örnek, düğmeye bağlı menünün tutamacını nasıl ayarleyeceğinizi, düğmeyi metin ve resim boyutuna göre nasıl yeniden boyutlandırılacağını ve çerçeve tarafından görüntülenen açılır menüyü nasıl ayarladığını gösterir. Bu kod snippet [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[CMFCDüğmesi](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenubutton.h

## <a name="cmfcmenubuttoncmfcmenubutton"></a><a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton

Yeni bir [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) nesnesi oluşturuyor.

```
CMFCMenuButton();
```

## <a name="cmfcmenubuttonm_bosmenu"></a><a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu

Çerçevenin hangi açılır menüde görüntülandığını gösteren bir Boolean üye değişkeni.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Açıklamalar

TRUE `m_bOSMenu` ise, çerçeve bu nesne `TrackPopupMenu` için devralınan yöntemi çağırır. Aksi takdirde, çerçeve [CContextMenuManager çağırır::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

## <a name="cmfcmenubuttonm_brightarrow"></a><a name="m_brightarrow"></a>CMFCMenü Düğmesi::m_bRightArrow

Açılır menünün konumunu gösteren bir Boolean üye değişkeni.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı menü düğmesine bastığında, uygulama açılır menü gösterir. Çerçeve açılır menüyü düğmenin altında veya düğmenin sağında görüntüler. Düğmede açılır menünerede görüneceğini gösteren küçük bir ok da bulunur. TRUE `m_bRightArrow` ise, çerçeve açılan menüyü düğmenin sağında görüntüler. Aksi takdirde, düğmenin altında açılır menü görüntüler.

## <a name="cmfcmenubuttonm_bstaypressed"></a><a name="m_bstaypressed"></a>CMFCMenü Düğmesi::m_bStayPressed

Kullanıcı açılır menüden seçim yaparken menü düğmesine basılı görünüp görünmediğini belirten bir Boolean üye değişkeni.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Açıklamalar

`m_bStayPressed` Üye FALSE ise, kullanımlar düğmeye tıkladığında menü düğmesine basıldığında olmaz. Bu durumda, çerçeve yalnızca açılır menüyü görüntüler.

`m_bStayPressed` Üye DOĞRU ise, kullanıcı düğmeyi tıklattığında menü düğmesine basılır. Kullanıcı açılır menüyü kapatana kadar, seçim yaparak veya iptal ederek basılı kalır.

## <a name="cmfcmenubuttonm_hmenu"></a><a name="m_hmenu"></a>CMFCMenuButton::m_hMenu

Ekli menünün tutamacı.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı menü düğmesini tıklattığında çerçeve, bu üye değişkentarafından belirtilen menüyü görüntüler.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult

Açılan menüden kullanıcının hangi öğeyi seçtiğini gösteren bir sonsalık.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı seçim yapmadan menüyü iptal ederse veya bir hata oluşursa, bu üye değişkenin değeri sıfırdır.

## <a name="cmfcmenubuttonm_bdefaultclick"></a><a name="m_bdefaultclick"></a>CMFCMenü Düğmesi::m_bDefaultClick

Düğmedeki metin veya görüntülerin varsayılan olarak işlenmesine izin verir.

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>Açıklamalar

m_bDefaultClick yanlışa ayarlamak, düğmenin herhangi bir yerine tıkladığınızda düğmenin menüye gösterilmesine neden olur.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult

Açılan menüden kullanıcının hangi öğeyi seçtiğini gösteren bir sonsalık.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubuttonpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage

Pencere iletilerini gönderilmeden önce çevirmek için çerçeve tarafından çağrılır.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
[içinde] İşleme iletiyi içeren bir [MSG](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

İleti çevrilmişse ve gönderilmemesi gerekiyorsa sıfıra inmez; İleti çevrilmediyse ve gönderilmeliyse 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCMenuButton::SizetoContent

Düğmenin boyutunu metin boyutuna ve görüntü boyutuna göre değiştirir.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcSadece*<br/>
[içinde] Bu yöntemin düğmeyi yeniden boyutlandırıp boyutlandırmadığını gösteren bir Boolean parametresi.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin yeni boyutunu belirten bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırırsanız ve *bCalcOnly* TRUE ise, `SizeToContent` düğmenin yalnızca yeni boyutunu hesaplar.

Düğmenin yeni boyutu, düğme metnine, görüntüye ve oka uyacak şekilde hesaplanır. Çerçeve ayrıca yatay kenar için 10 piksel ve dikey kenar için 5 piksel önceden tanımlanmış kenar boşlukları ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
