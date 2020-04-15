---
title: CReBar Sınıfı
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
ms.openlocfilehash: c1379d1ef8effea0df564da1b43769bb9a11435d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363939"
---
# <a name="crebar-class"></a>CReBar Sınıfı

Rebar denetimleri için düzen, kalıcılık ve durum bilgilerini sağlayan bir denetim çubuğu.

## <a name="syntax"></a>Sözdizimi

```
class CReBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Crebar::Addbar](#addbar)|Bir çubuk için bir bant ekler.|
|[Crebar::Oluştur](#create)|Demir çubuğu denetimini oluşturur ve `CReBar` nesneye bağlar.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|Altta yatan ortak denetime doğrudan erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir demir çubuğu nesnesi, düzenleme kutuları, araç çubukları ve liste kutuları da dahil olmak üzere genellikle diğer denetimler, çeşitli alt pencereler içerebilir. Bir çubuk nesnesi alt pencerelerini belirli bir bit eşlemi üzerinde görüntüleyebilir. Uygulamanız demir çubuğuotomatik olarak yeniden boyutlandırabilir veya kullanıcı tutucu çubuğunu tıklatarak veya sürükleyerek çubuğu el ile yeniden boyutlandırabilir.

![RebarMenu örneği](../../mfc/reference/media/vc4sc61.gif "RebarMenu örneği")

## <a name="rebar-control"></a>Demir Kontrolü

Bir çubuk nesnesi araç çubuğu nesnesine benzer şekilde tepki ritmiş olur. Bir çubuk, bantlarını yeniden boyutlandırmak için tıkla ve sürükley mekanizmasını kullanır. Bir çubuk denetimi, her bandın bir kavrayıcı çubuğu, bitmap, metin etiketi ve alt pencerenin herhangi bir kombinasyonuna sahip olduğu bir veya daha fazla bant içerebilir. Ancak, bantlar birden fazla alt pencere içeremez.

`CReBar`uygulanmasını sağlamak için [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) sınıfını kullanır. Denetimin özelleştirme seçeneklerinden yararlanmak için [GetReBarCtrl](#getrebarctrl) aracılığıyla çubuk denetimine erişebilirsiniz. Demir çubuğu denetimleri hakkında `CReBarCtrl`daha fazla bilgi için bkz. Çubuk denetimleri kullanma hakkında daha fazla bilgi için [Bkz. CReBarCtrl'ı kullanma.](../../mfc/using-crebarctrl.md)

> [!CAUTION]
> Demir ve demir kontrol nesneleri MFC denetim çubuğu yerleştirmeyi desteklemez. `CRebar::EnableDocking` Çağrılsa, uygulamanız ileri sürecektir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="crebaraddbar"></a><a name="addbar"></a>Crebar::Addbar

Çubuk'a bir bant eklemek için bu üye işlevini arayın.

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
Çubuk'a `CWnd` eklenecek alt pencere olan bir nesneye işaretçi. Başvurulan nesnenin bir WS_CHILD olmalıdır.

*lpszMetin*<br/>
Çubukta görünecek metni içeren bir dize işaretçisi. Varsayılan olarak NULL. *lpszText'te* yer alan metin alt pencerenin bir parçası değildir; demirin kendisindedir.

*pbmp*<br/>
Demir çubuğu `CBitmap` arka planında görüntülenecek bir nesneye işaretçi. Varsayılan olarak NULL.

*Dwstyle*<br/>
Demir çubuğuna uygulanacak stili içeren bir DWORD. Grup `fStyle` stillerinin tam listesi için Win32 yapısı [REBARBANDINFO'daki](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) işlev açıklamasına bakın.

*clrFore*<br/>
Demir çubuğunun ön plan rengini temsil eden bir COLORREF değeri.

*clrGeri*<br/>
Demir çubuğunun arka plan rengini temsil eden bir COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a>Crebar::Oluştur

Bir çubuk oluşturmak için bu üye işlevi arayın.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Windows penceresi `CWnd` durum çubuğunun üst öğesi olan nesneye işaretçi. Normalde çerçeve pencereniz.

*dwCtrlStyle*<br/>
Demir kontrol stili. Varsayılan olarak, RBS_BANDBORDERS, hangi çubuk denetimi içinde bitişik bantları ayırmak için dar çizgiler görüntüler. Stil listesi için Windows SDK'daki [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

*Dwstyle*<br/>
Demir pencere stilleri.

*Nıd*<br/>
Demirçubuğun çocuk penceresi kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  CReBar örneğine [bakın:AddBar](#addbar).

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a>CReBar::GetReBarCtrl

Bu üye işlev, temel ortak denetime doğrudan erişim sağlar.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CReBarCtrl](../../mfc/reference/crebarctrl-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini arayarak, çubuğunuzu özelleştirmede Windows demiri ortak denetiminin işlevselliğinden yararlanın. Aradiğinizde, `GetReBarCtrl`bir başvuru nesnesini `CReBarCtrl` nesneye döndürür, böylece her iki üye işlev kümesini de kullanabilirsiniz.

Demir çubuğunuzu `CReBarCtrl` özelleştirmek için kullanma hakkında daha fazla bilgi için [Bkz. CReBarCtrl'ı kullanma.](../../mfc/using-crebarctrl.md)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
