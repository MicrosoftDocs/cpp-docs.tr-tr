---
description: 'Daha fazla bilgi edinin: CReBar sınıfı'
title: CReBar sınıfı
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 138add510b76f21f5776f809b1551eb35d554d68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343133"
---
# <a name="crebar-class"></a>CReBar sınıfı

Rebar denetimleri için düzen, kalıcılık ve durum bilgilerini sağlayan bir denetim çubuğu.

## <a name="syntax"></a>Syntax

```
class CReBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CReBar:: AddBar](#addbar)|Bir yeniden çubuğa bir bant ekler.|
|[CReBar:: Create](#create)|Yeniden çubuk denetimini oluşturur ve `CReBar` nesneye ekler.|
|[CReBar:: GetReBarCtrl](#getrebarctrl)|Temel alınan ortak denetime doğrudan erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir Rebar nesnesi, düzenleme kutuları, araç çubukları ve liste kutuları dahil olmak üzere çeşitli alt Windows, genellikle diğer denetimleri içerebilir. Bir Rebar nesnesi, alt pencerelerini belirtilen bir bit eşlem üzerinde görüntüleyebilir. Uygulamanız otomatik olarak yeniden boyutlandırabilir veya Kullanıcı kavrayıcı çubuğunu tıklayarak veya sürükleyerek yeniden boyutlandırabilir.

![RebarMenu örneği](../../mfc/reference/media/vc4sc61.gif "RebarMenu örneği")

## <a name="rebar-control"></a>Rebar denetimi

Bir çubuk nesnesi, bir araç çubuğu nesnesine benzer şekilde davranır. Bir yeniden çubuk, bantlarını yeniden boyutlandırmak için tıklama ve sürükleme mekanizmasını kullanır. Bir Rebar denetimi, her bantın bir kavrayıcı çubuğu, bir bit eşlem, bir metin etiketi ve bir alt pencere ile herhangi bir birleşimini içeren bir veya daha fazla bant içerebilir. Ancak bantların birden fazla alt penceresi olamaz.

`CReBar` , uygulamasını sağlamak için [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) sınıfını kullanır. Denetimin özelleştirme seçeneklerinin avantajlarından yararlanmak için [GetReBarCtrl](#getrebarctrl) aracılığıyla Rebar denetimine erişebilirsiniz. Rebar denetimleri hakkında daha fazla bilgi için bkz `CReBarCtrl` .. Rebar denetimleri kullanma hakkında daha fazla bilgi için bkz. [CReBarCtrl kullanma](../../mfc/using-crebarctrl.md).

> [!CAUTION]
> Rebar ve Rebar denetim nesneleri MFC denetim çubuğunu yerleştirmeyi desteklemez. `CRebar::EnableDocking`Çağrılırsa, uygulamanız onay olacaktır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="crebaraddbar"></a><a name="addbar"></a> CReBar:: AddBar

Yeniden çubuğa bir bant eklemek için bu üye işlevini çağırın.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
`CWnd`Yeniden çubuğuna eklenecek alt pencere olan nesneye yönelik bir işaretçi. Başvurulan nesne bir WS_CHILD sahip olmalıdır.

*lpszText*<br/>
Yeniden çubukta görünecek metni içeren bir dize işaretçisi. Varsayılan olarak NULL. *LpszText* içinde bulunan metin, alt pencerenin bir parçası değildir; Bu, yeniden çubuğun kendisidir.

*PBMP*<br/>
`CBitmap`Yeniden çubuk arka planında görüntülenecek bir nesne işaretçisi. Varsayılan olarak NULL.

*dwStyle*<br/>
Yeniden çubuğuna uygulanacak stili içeren bir DWORD. `fStyle`Bant stillerinin tamamı listesi Için Win32 yapısı [Rebarbanınfo](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) içindeki işlev açıklamasına bakın.

*Clrön*<br/>
Yeniden çubuğun ön plan rengini temsil eden bir COLORREF değeri.

*clrBack*<br/>
Rebar 'in arka plan rengini temsil eden bir COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a> CReBar:: Create

Bir yeniden çubuk oluşturmak için bu üye işlevini çağırın.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
`CWnd`Windows penceresi durum çubuğunun üst öğesi olan nesneye yönelik işaretçi. Normalde çerçeve pencereniz.

*dwCtrlStyle*<br/>
Rebar denetim stili. Varsayılan olarak, ardışık bantları yeniden çubuk denetimi içinde ayırmak için dar çizgileri görüntüleyen RBS_BANDBORDERS. Stil listesi için Windows SDK yer içindeki [Rebar denetim stillerine](/windows/win32/Controls/rebar-control-styles) bakın.

*dwStyle*<br/>
Yeniden çubuk pencere stilleri.

*NID*<br/>
Rebar 'in alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CReBar:: AddBar](#addbar)örneğine bakın.

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a> CReBar:: GetReBarCtrl

Bu üye işlevi, temel alınan ortak denetime doğrudan erişim sağlar.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Yeniden çubuğunuzu özelleştirirken Windows Rebar ortak denetiminin işlevselliğinden faydalanmak için bu üye işlevi çağırın. `GetReBarCtrl`' İ çağırdığınızda, `CReBarCtrl` üye işlevleri kümesini kullanabilmeniz için nesnesine bir başvuru nesnesi döndürür.

Yeniden çubuğunuzu özelleştirmek için kullanma hakkında daha fazla bilgi için `CReBarCtrl` bkz. [CReBarCtrl kullanma](../../mfc/using-crebarctrl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCıE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
