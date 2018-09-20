---
title: CMFCMenuButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31f487267074af185b6393496823ac9965a4a6b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411501"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton sınıfı

Bir açılır menü görüntüleyen ve kullanıcı menüsü seçeneklerini raporlayan bir düğme.

## <a name="syntax"></a>Sözdizimi

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Oluşturur bir `CMFCMenuButton` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Pencere iletilerini dağıtılmadan önce çevirmek için framework tarafından çağırılır. (Geçersiz kılmaları `CMFCButton::PreTranslateMessage`.)|
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Düğme metin ve görüntü boyutuna göre boyutunu değiştirir.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Varsayılan sistem açılan menüyü görüntülemek mi kullanılacağını belirtir [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Açılan menü altında veya düğmenin sağındaki görüntülenip görüntülenmeyeceğini belirtir.|
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Kullanıcı düğmeyi yayımlandıktan sonra menü düğmesine durumuna değiştirilip değiştirilmediğini belirtir.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ekli Windows menüsüne tanıtıcı.|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Hangi öğeyi gösteren tanımlayıcı açılır menüden kullanıcı seçildi.|

## <a name="remarks"></a>Açıklamalar

`CMFCMenuButton` Sınıfı türetilen [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md) buna karşılık, türetilen [CButton sınıfı](../../mfc/reference/cbutton-class.md). Bu nedenle, kullanabileceğiniz `CMFCMenuButton` kodunuzda kullandığınız aynı şekilde `CButton`.

Oluştururken bir `CMFCMenuButton`, ilişkili açılır menüsüne bir tanıtıcıda geçmesi gerekir. Ardından, işlev çağrısı `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent` Düğme Boyutu açılır pencerede - yani altında veya düğmenin sağındaki görüneceği yeri konumu gösteren bir ok dahil etmek yeterli olup olmadığını denetler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, framework tarafından görüntülenen açılır menü düğmesine iliştirilmiş menü tanıtıcısı yapmak, düğme metin ve görüntü boyutuna göre yeniden boyutlandır ve gösterilmektedir. Bu kod parçacığı parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmenubutton.h

##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton

Yeni bir oluşturur [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) nesne.

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu

Açılan menüyü gösteren bir Boolean üye değişkeni framework görüntüler.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>Açıklamalar

Varsa `m_bOSMenu` doğru ise, framework devralınan çağırır `TrackPopupMenu` bu nesne için yöntemi. Aksi takdirde, framework çağırır [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).

##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow

Açılır menü konumunu belirten bir Boolean üye değişkeni.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı menü düğmesine bastığında uygulama açılır menü gösterir. Framework düğmesinin altındaki veya düğmenin sağındaki açılan menü görüntüler. Düğme, açılan menüyü nerede görüneceğini gösteren küçük bir ok de vardır. Varsa `m_bRightArrow` doğru ise, framework açılır menü düğmesinin sağında görüntülenir. Aksi takdirde, düğmesinin altındaki açılan menü görüntüler.

##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed

Menü düğmesine görüntülenip görüntülenmeyeceğini belirten bir Boolean üye değişkeni, kullanıcı açılır menüden seçim yaparken basılı.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>Açıklamalar

Varsa `m_bStayPressed` üye FALSE ise, menü düğmesine ne zaman basılmadı haline kullandığı düğmesine tıklar. Bu durumda, framework yalnızca açılır menü görüntüler.

Varsa `m_bStayPressed` üye ise TRUE, kullanıcı düğmeye tıkladığında menü düğmesine basıldığında olur. Kullanıcı açılır menüsünde, bir seçim yaparak veya iptal etme kapatıldıktan sonra kadar basılı kalır.

##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu

Ekli menüsüne tanıtıcısı.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>Açıklamalar

Framework kullanıcı menü düğmesine tıkladığında bu üye değişkeni tarafından belirtilen menü görüntüler.

##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult

Hangi öğeyi gösteren bir tam sayı, açılır menüden kullanıcı seçer.

```
int m_nMenuResult;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeninin değeri bir seçim yapmadan kullanıcı menü iptal ederse veya bir hata oluşursa sıfırdır.

##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage

Pencere iletilerini dağıtılmadan önce çevirmek için framework tarafından çağırılır.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
[in] İşaret eden bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için bir ileti içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İleti çevrilmiştir ve değil dağıtılması olursa sıfır dışı; 0 ileti değil çevrilmiştir ve dağıtılması.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent

Düğme, metin boyutu ve görüntü boyutuna göre boyutunu değiştirir.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcOnly*<br/>
[in] Bu yöntem düğmeyi yeniden boyutlandırıp boyutlandıramayacağını gösteren bir Boole parametresi.

### <a name="return-value"></a>Dönüş Değeri

A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesini düğme için yeni bir boyut belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağırırsanız ve *bCalcOnly* TRUE ise `SizeToContent` düğmesi yalnızca yeni boyutunu yeniden hesaplar.

Yeni boyut düğmenin düğme metin, görüntü ve ok uyacak şekilde hesaplanır. Framework ayrıca yatay edge için 10 piksel ve 5 piksel dikey edge için önceden tanımlanmış kenar boşluklarını ekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
