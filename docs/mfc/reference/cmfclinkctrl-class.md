---
title: CMFCLinkCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 79edff8be6e2c37baa938fc5b624253932609e17
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754252"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl Sınıfı

Sınıf `CMFCLinkCtrl` bir düğmeyi köprü olarak görüntüler ve düğme tıklatıldığında bağlantının hedefini çağırır.

## <a name="syntax"></a>Sözdizimi

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl::SetURL](#seturl)|Düğme metni olarak belirtilen bir URL'yi görüntüler.|
|[CMFCLinkCtrl::SetURLÖnek](#seturlprefix)|URL'nin örtük protokolünü (örneğin, "http:") ayarlar.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Düğme metnini veya bit eşlemi içerecek şekilde düğmeyi yeniden boyutlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Düğmenin odak dikdörtgeni çizilmeden önce çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

`CMFCLinkCtrl` Sınıftan türetilen bir düğmeyi tıklattığınızda, çerçeve yönteme parametre olarak `ShellExecute` düğmenin URL'sini geçirir. Daha `ShellExecute` sonra yöntem URL'nin hedefini açar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCLinkCtrl` nesnenin boyutunun nasıl ayarlanır ve bir `CMFCLinkCtrl` nesnede url ve araç ipucunun nasıl ayarlanır gösteriş gösterir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[CMFCDüğmesi](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlinkctrl.h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect

Düğmenin odak dikdörtgeni çizilmeden önce çerçeve tarafından çağrılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectClient*<br/>
[içinde] Bağlantı denetimini sınırlayan bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Düğmenin odak dikdörtgenini çizmek için kendi kodunuzu kullanmak istediğinizde bu yöntemi geçersiz kılın.

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl::SetURL

Düğme metni olarak belirtilen bir URL'yi görüntüler.

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
[içinde] Görüntülenecek düğme metni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl::SetURLÖnek

URL'nin örtük protokolünü (örneğin, "http:") ayarlar.

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Parametreler

*lpszÖnek*<br/>
[içinde] URL protokolünün öneki.

### <a name="remarks"></a>Açıklamalar

URL önekini ayarlamak için bu yöntemi kullanın. Önek düğmenin yüzünde görüntülenmez, ancak URL'nin hedefine göz atmaya yardımcı olmak için kullanabilirsiniz.

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent

Düğme metnini veya bit eşlemi içerecek şekilde düğmeyi yeniden boyutlandırır.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Parametreler

*bVCenter*<br/>
[içinde] Düğme metnini ve bit eşleminin bağlantı denetiminin üst ve alt kısmı arasında dikey olarak ortalamak için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer FALSE'dur.

*bHCenter*<br/>
[içinde] Düğme metnini ve bit eşlemini bağlantı denetiminin sol ve sağ tarafları arasında yatay olarak ortalamak için DOĞRU; aksi takdirde, YANLIŞ. Varsayılan değer FALSE'dur.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı denetiminin yeni boyutunu içeren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl Sınıfı](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
