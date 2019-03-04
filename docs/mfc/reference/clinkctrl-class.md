---
title: CLinkCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: 38f529f46623bc7095879b29fba09427626073ec
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260415"
---
# <a name="clinkctrl-class"></a>CLinkCtrl sınıfı

Windows SysLink denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Oluşturur bir `CLinkCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLinkCtrl::Create](#create)|Bir bağlantı denetimi oluşturur ve ona bağlanan bir `CLinkCtrl` nesne.|
|[CLinkCtrl::CreateEx](#createex)|Genişletilmiş stilleriyle bir bağlantı denetimi oluşturur ve ona ekler bir `CLinkCtrl` nesne.|
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Bağlantı denetimi ideal yüksekliğini alır.|
|[CLinkCtrl::GetIdealSize](#getidealsize)|Bağlantı metni belirtilen genişlik bağlantının bağlı olarak geçerli bağlantı denetimi için tercih edilen yüksekliğini hesaplar.|
|[CLinkCtrl::GetItem](#getitem)|Durumları ve bir bağlantı denetim öğesi özniteliklerini alır.|
|[CLinkCtrl::GetItemID](#getitemid)|Bir bağlantı denetim öğesi Kimliğini alır.|
|[CLinkCtrl::GetItemState](#getitemstate)|Bağlantı Denetim öğesi durumunu alır.|
|[CLinkCtrl::GetItemUrl](#getitemurl)|Bağlantı Denetim öğesi tarafından temsil edilen URL'sini alır.|
|[CLinkCtrl::HitTest](#hittest)|Kullanıcının belirtilen bağlantıya tıkladığını olup olmadığını belirler.|
|[CLinkCtrl::SetItem](#setitem)|Bir bağlantı denetim öğesi özniteliklerini ve durumlarını ayarlar.|
|[CLinkCtrl::SetItemID](#setitemid)|Bir bağlantı denetim öğesi Kimliğini ayarlar.|
|[CLinkCtrl::SetItemState](#setitemstate)|Bağlantı Denetim öğesi durumunu ayarlar.|
|[CLinkCtrl::SetItemUrl](#setitemurl)|Bağlantı Denetim öğesi tarafından temsil edilen URL'sini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir "bağlantı denetimi" bir pencere içinde köprü metin bağlantılarından katıştırmak için kullanışlı bir yol sağlar. Gerçek denetim işaretlenmiş metin işler ve kullanıcı bir katıştırılmış bağlantısına tıkladığında ilgili uygulamaları başlatan bir penceredir. Birden çok bağlantı ve sıfır tabanlı bir dizin tarafından erişilebilen bir denetim içinde desteklenir.

Bu denetimi (ve bu nedenle `CLinkCtrl` sınıfı) yalnızca Windows XP ve sonraki sürümlerde çalışan programlar kullanılabilir.

Daha fazla bilgi için [SysLink denetimi](/windows/desktop/Controls/syslink-overview) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl

Oluşturur bir `CLinkCtrl` nesne.

```
CLinkCtrl();
```

##  <a name="create"></a>  CLinkCtrl::Create

Bir bağlantı denetimi oluşturur ve ona bağlanan bir `CLinkCtrl` nesne.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszLinkMarkup*<br/>
İşaretli görüntülenecek metni içeren sıfır ile sonlandırılmış bir dize işaretçisi. Daha fazla bilgi için ' % s'bölümüne "Biçimlendirme ve bağlantı erişim" konusunda bakın [SysLink denetimleri genel bakış](/windows/desktop/Controls/syslink-overview).

*dwStyle*<br/>
Bağlantı denetiminin stilini belirtir. Denetim stilleri herhangi bir bileşimini uygulayın. Bkz: [ortak denetim stilleri](/windows/desktop/Controls/common-control-styles) içinde `Windows SDK` daha fazla bilgi için.

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresine belirtir. NULL olmamalıdır.

*nID*<br/>
Bağlantı denetimin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CLinkCtrl` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, bağlantı denetimi oluşturur ve ona ekler `CLinkCtrl` nesne. Genişletilmiş windows stilleri ile denetiminizi kullanmak istiyorsanız, çağrı [CLinkCtrl::CreateEx](#createex) yerine `Create`.

İkinci form, `Create` metodu kullanım dışı bırakılmıştır. Belirten ilk formu *lpszLinkMarkup* parametresi.

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde adlı iki değişken tanımlar `m_Link1` ve `m_Link2`, iki bağlantı denetimlerini erişmek için kullanılır.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, başka bir bağlantı denetimi konumunu temel alarak bir bağlantı denetimi oluşturur. Uygulama başlatıldığında ilk bağlantı denetimi kaynak yükleyicisi oluşturur. Uygulamanızı OnInitDialog yöntemi girdiğinde, ikinci bir bağlantı denetimi ilk bağlantı denetimi konumuna göre oluşturun. Ardından görüntüler metin sığdırmak için ikinci bağlantı denetimi yeniden boyutlandırın.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

##  <a name="createex"></a>  CLinkCtrl::CreateEx

Genişletilmiş stilleriyle bir bağlantı denetimi oluşturur ve ona ekler bir `CLinkCtrl` nesne.

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>Parametreler

*lpszLinkMarkup*<br/>
İşaretli görüntülenecek metni içeren sıfır ile sonlandırılmış bir dize işaretçisi. Daha fazla bilgi için ' % s'bölümüne "Biçimlendirme ve bağlantı erişim" konusunda bakın [SysLink denetimleri genel bakış](/windows/desktop/Controls/syslink-overview).

*dwExStyle*<br/>
Genişletilmiş bağlantı denetiminin stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Bağlantı denetiminin stilini belirtir. Denetim stilleri herhangi bir bileşimini uygulayın. Daha fazla bilgi için [ortak denetim stilleri](/windows/desktop/Controls/common-control-styles) Windows SDK.

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresine belirtir. NULL olmamalıdır.

*nID*<br/>
Bağlantı denetimin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) genişletilmiş Windows stili sabitleri uygulamak için.

İkinci form, `CreateEx` metodu kullanım dışı bırakılmıştır. Belirten ilk formu *lpszLinkMarkup* parametresi.

##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight

Bağlantı denetimi ideal yüksekliğini alır.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin piksel cinsinden ideal yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [LM_GETIDEALHEIGHT](/windows/desktop/Controls/lm-getidealheight)Windows SDK içinde açıklandığı gibi.

##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize

Bağlantı metni belirtilen genişlik bağlantının bağlı olarak geçerli bağlantı denetimi için tercih edilen yüksekliğini hesaplar.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*cxMaxWidth*|[in] Maksimum genişliğini piksel cinsinden bağlantı.|
|[out] \* *pSize*|Bir Windows işaretçisi [BOYUTU](/windows/desktop/api/windef/ns-windef-tagsize) yapısı. Bu yöntem döndürüldüğünde, *cy* üyesi `SIZE` yapısı tarafından belirtilen bağlantı metni genişliği için ideal bağlantı metni yükseklik içeren *cxMaxWidth*. *Cx* yapı üyesi için gerekli olan bağlantı metni genişliği içerir.|

### <a name="return-value"></a>Dönüş Değeri

Tercih edilen bağlantı metnini, piksel cinsinden yüksekliği. Dönüş değeri değeri ile aynıdır *cy* üyesi `SIZE` yapısı.

### <a name="remarks"></a>Açıklamalar

Bir örneği `GetIdealSize` yöntemi, örneğe bakın [CLinkCtrl::Create](#create).

Bu yöntem gönderir [LM_GETIDEALSIZE](/windows/desktop/Controls/lm-getidealsize) Windows SDK'da açıklanan ileti.

##  <a name="getitem"></a>  CLinkCtrl::GetItem

Durumları ve bir bağlantı denetim öğesi özniteliklerini alır.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Bir işaretçi bir [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) öğesi bilgilerini almak için yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [LM_GETITEM](/windows/desktop/Controls/lm-getitem)Windows SDK içinde açıklandığı gibi.

##  <a name="getitemid"></a>  CLinkCtrl::GetItemID

Bir bağlantı denetim öğesi Kimliğini alır.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*strID*<br/>
A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) belirtilen öğenin Kimliğini içeren nesne.

*szID*<br/>
Belirtilen öğenin Kimliğini içeren null ile sonlandırılmış bir dize.

*cchID*<br/>
Karakter cinsinden boyutu *szID* arabellek.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

> [!NOTE]
>  Bu işlev ayrıca değilse false değerini döndürür, arabellek *szID veya strID* MAX_LINKID_TEXT küçüktür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetimi öğesinin Kimliğini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK.

##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState

Bağlantı Denetim öğesi durumunu alır.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*pnState*<br/>
Belirtilen durum öğesinin değeri.

*stateMask*<br/>
Almak için hangi durumu öğesini açıklayan bayrakları birleşimi. Değerler listesi için açıklamasına bakın `state` üye [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) yapısı. Bu izin verilen öğeler aynıdır `state`.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesi belirtilen durum öğenin değerini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK.

##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl

Bağlantı Denetim öğesi tarafından temsil edilen URL'sini alır.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*strUrl*<br/>
A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) belirtilen öğe tarafından temsil edilen URL'sini içeren bir nesne

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL'sini içeren null ile sonlandırılmış bir dize

*cchUrl*<br/>
Karakter cinsinden boyutu *szURL* arabellek.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

> [!NOTE]
>  Bu işlev ayrıca değilse false değerini döndürür, arabellek *szUrl veya strUrl* MAX_LINKID_TEXT küçüktür.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesi tarafından temsil edilen URL'sini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](/windows/desktop/Controls/lm-getitem) Windows SDK.

##  <a name="hittest"></a>  CLinkCtrl::HitTest

Kullanıcı belirtilen bağlantı tıkladı olmadığını belirler.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Parametreler

*phti*<br/>
İşaretçi bir `LHITTESTINFO` kullanıcı tıkladı bağlantısıyla ilgili tüm bilgileri içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [LM_HITTEST](/windows/desktop/Controls/lm-hittest)Windows SDK içinde açıklandığı gibi.

##  <a name="setitem"></a>  CLinkCtrl::SetItem

Bir bağlantı denetim öğesi özniteliklerini ve durumlarını ayarlar.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Bir işaretçi bir [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) ayarlamak için bilgi içeren yapıya.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [LM_SETITEM](/windows/desktop/Controls/lm-setitem)Windows SDK içinde açıklandığı gibi.

##  <a name="setitemid"></a>  CLinkCtrl::SetItemID

Bir bağlantı denetim öğesi Kimliğini alır.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*szID*<br/>
Belirtilen öğenin Kimliğini içeren null ile sonlandırılmış bir dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesi Kimliğini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK.

##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState

Bağlantı Denetim öğesi durumunu alır.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*pnState*<br/>
Ayarlanan belirli durumda öğesinin değeri.

*stateMask*<br/>
Ayarlanan durumu öğesini açıklayan bayrakları birleşimi. Değerler listesi için açıklamasına bakın `state` üye [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) yapısı. Bu izin verilen öğeler aynıdır `state`.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesi belirtilen durum öğenin değerini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK.

##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl

Bağlantı Denetim öğesi tarafından temsil edilen URL'sini ayarlar.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*İ.Link*<br/>
Bir bağlantı denetim öğesi dizini.

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL'sini içeren null ile sonlandırılmış bir dize

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesi tarafından temsil edilen URL'sini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](/windows/desktop/Controls/lm-setitem) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
