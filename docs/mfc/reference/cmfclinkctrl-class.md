---
description: 'Daha fazla bilgi edinin: CMFCLinkCtrl sınıfı'
title: CMFCLinkCtrl sınıfı
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
ms.openlocfilehash: 6951f086ac99c4b8a8260a79ee08d54476694350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265226"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl sınıfı

`CMFCLinkCtrl`Sınıfı bir düğmeyi köprü olarak görüntüler ve düğmeye tıklandığında bağlantının hedefini çağırır.

## <a name="syntax"></a>Syntax

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl:: SetURL](#seturl)|Düğme metni olarak belirtilen bir URL 'YI görüntüler.|
|[CMFCLinkCtrl:: SetURLPrefix](#seturlprefix)|URL 'nin örtük protokolünü (örneğin, "http:") ayarlar.|
|[CMFCLinkCtrl:: SizeToContent](#sizetocontent)|Düğmeyi düğme metnini veya bit eşlemini içerecek şekilde yeniden boyutlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl:: OnDrawFocusRect](#ondrawfocusrect)|Düğmenin odak dikdörtgeni çizilmeden önce Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Sınıfından türetilmiş bir düğmeye tıkladığınızda `CMFCLinkCtrl` , çerçeve DÜĞMENIN URL 'sini yöntemine bir parametre olarak geçirir `ShellExecute` . Daha sonra `ShellExecute` yöntemi, URL 'nin hedefini açar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin boyutunun nasıl ayarlanacağını `CMFCLinkCtrl` ve bir nesnenin URL ve araç ipucunun nasıl ayarlanacağını gösterir `CMFCLinkCtrl` . Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlinkctrl. h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a> CMFCLinkCtrl:: OnDrawFocusRect

Düğmenin odak dikdörtgeni çizilmeden önce Framework tarafından çağırılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectClient*<br/>
'ndaki Bağlantı denetimini sınıralan dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Düğmenin odak dikdörtgenini çizmek için kendi kodunuzu kullanmak istediğinizde bu yöntemi geçersiz kılın.

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a> CMFCLinkCtrl:: SetURL

Düğme metni olarak belirtilen bir URL 'YI görüntüler.

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
'ndaki Görüntülenecek düğme metni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a> CMFCLinkCtrl:: SetURLPrefix

URL 'nin örtük protokolünü (örneğin, "http:") ayarlar.

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Parametreler

*lpszPrefix*<br/>
'ndaki URL protokolünün ön eki.

### <a name="remarks"></a>Açıklamalar

URL önekini ayarlamak için bu yöntemi kullanın. Ön ek düğmenin yüzinde gösterilmez, ancak URL 'nin hedefine gözatmanıza yardımcı olması için kullanabilirsiniz.

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a> CMFCLinkCtrl:: SizeToContent

Düğmeyi düğme metnini veya bit eşlemini içerecek şekilde yeniden boyutlandırır.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Parametreler

*bVCenter*<br/>
'ndaki Düğme metnini ve bit eşlemini bağlantı denetiminin üst ve alt arasında dikey olarak ortalamak için TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

*bHCenter*<br/>
'ndaki Düğme metnini ve bit eşlemini bağlantı denetiminin sol ve sağ kenarları arasında yatay olarak ortalamak için TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı denetiminin yeni boyutunu içeren [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl sınıfı](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md)
