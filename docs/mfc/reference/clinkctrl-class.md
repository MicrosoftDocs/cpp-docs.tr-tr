---
title: CLinkCtrl Sınıfı
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
ms.openlocfilehash: aa1f630b448c60a0eeb6a905ed6eef6f84a2ff8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372252"
---
# <a name="clinkctrl-class"></a>CLinkCtrl Sınıfı

Windows ortak SysLink denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Bir `CLinkCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CLinkCtrl::Oluştur](#create)|Bir bağlantı denetimi oluşturur ve bir `CLinkCtrl` nesneye bağlar.|
|[CLinkCtrl::CreateEx](#createex)|Genişletilmiş stiller içeren bir bağlantı denetimi oluşturur `CLinkCtrl` ve bir nesneye bağlar.|
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Bağlantı denetiminin ideal yüksekliğini alır.|
|[CLinkCtrl::GetIdealSize](#getidealsize)|Bağlantının belirtilen genişliğine bağlı olarak, geçerli bağlantı denetimi için bağlantı metninin tercih edilen yüksekliğini hesaplar.|
|[CLinkCtrl::GetItem](#getitem)|Bağlantı denetim öğesinin durumlarını ve özniteliklerini alır.|
|[CLinkCtrl::GetItemID](#getitemid)|Bağlantı denetim öğesinin kimliğini alır.|
|[CLinkCtrl::GetItemState](#getitemstate)|Bağlantı denetim öğesinin durumunu alır.|
|[CLinkCtrl::GetItemUrl](#getitemurl)|Bağlantı denetim öğesi tarafından temsil edilen URL'yi alır.|
|[CLinkCtrl::HitTest](#hittest)|Kullanıcının belirtilen bağlantıyı tıklayıp tıklatmadığını belirler.|
|[CLinkCtrl::SetItem](#setitem)|Bağlantı denetim öğesinin durumlarını ve özniteliklerini ayarlar.|
|[CLinkCtrl::SetItemID](#setitemid)|Bağlantı denetim öğesinin kimliğini ayarlar.|
|[CLinkCtrl::SetItemState](#setitemstate)|Bağlantı denetim öğesinin durumunu ayarlar.|
|[CLinkCtrl::SetItemUrl](#setitemurl)|Bağlantı denetim öğesi tarafından temsil edilen URL'yi ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Bağlantı denetimi" bir pencereye hipermetin bağlantılarını yerleştirmek için kullanışlı bir yol sağlar. Gerçek denetim, işaretlenmiş metni işleyen ve kullanıcı katıştırılmış bir bağlantıyı tıklattığında uygun uygulamaları başlatan bir penceredir. Birden çok bağlantı tek bir denetim içinde desteklenir ve sıfır tabanlı bir dizin tarafından erişilebilir.

Bu denetim (ve `CLinkCtrl` bu nedenle sınıf) yalnızca Windows XP altında çalışan programlar ve daha sonra kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [SysLink Denetimi'ne](/windows/win32/Controls/syslink-overview) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl

Bir `CLinkCtrl` nesne inşa eder.

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a>CLinkCtrl::Oluştur

Bir bağlantı denetimi oluşturur ve bir `CLinkCtrl` nesneye bağlar.

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
Görüntülenecek işaretli metni içeren sıfır sonlandırılmış bir dize işaretçi. Daha fazla bilgi için, [sysLink denetimlerine genel bakış](/windows/win32/Controls/syslink-overview)konusu "Biçimlendirme ve Bağlantı Erişimi" bölümüne bakın.

*Dwstyle*<br/>
Bağlantı denetiminin stilini belirtir. Kontrol stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi `Windows SDK` için Ortak Denetim [Stilleri'ne](/windows/win32/Controls/common-control-styles) bakın.

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresini belirtir. NULL olmamalıdır.

*Nıd*<br/>
Bağlantı denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlangıç başarılı olduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CLinkCtrl` iki adımda inşa ee. Önce oluşturucuyu çağırın `Create`ve ardından bağlantı denetimini oluşturan ve `CLinkCtrl` nesneye iliştiren , çağırın. Denetiminizle genişletilmiş windows stillerini kullanmak istiyorsanız, [CLinkCtrl::CreateEx](#createex) yerine `Create`.

Yöntemin `Create` ikinci formu amortismana sokuldu. *lpszLinkMarkup* parametresini belirten ilk formu kullanın.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, iki bağlantı `m_Link1` denetimine erişmek için kullanılan adlandırılmış ve `m_Link2`iki değişken ilerler.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, başka bir bağlantı denetiminin konumuna göre bir bağlantı denetimi oluşturur. Kaynak yükleyici, uygulamanız başladığında ilk bağlantı denetimini oluşturur. Uygulamanız OnInitDialog yöntemine girdiğinde, ilk bağlantı denetiminin konumuna göre ikinci bağlantı denetimini oluşturursunuz. Ardından, ikinci bağlantı denetimini görüntülediğiniz metne uyacak şekilde yeniden boyutlandırırsınız.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a>CLinkCtrl::CreateEx

Genişletilmiş stiller içeren bir bağlantı denetimi oluşturur `CLinkCtrl` ve bir nesneye bağlar.

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
Görüntülenecek işaretli metni içeren sıfır sonlandırılmış bir dize işaretçi. Daha fazla bilgi için, [sysLink denetimlerine genel bakış](/windows/win32/Controls/syslink-overview)konusu "Biçimlendirme ve Bağlantı Erişimi" bölümüne bakın.

*dwExStyle*<br/>
Bağlantı denetiminin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Bağlantı denetiminin stilini belirtir. Kontrol stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için Windows SDK'daki [Ortak Denetim Stilleri'ne](/windows/win32/Controls/common-control-styles) bakın.

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresini belirtir. NULL olmamalıdır.

*Nıd*<br/>
Bağlantı denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlangıç başarılı olduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş `CreateEx` Windows stil sabitlerini uygulamak için [Oluştur](#create) yerine kullanın.

Yöntemin `CreateEx` ikinci formu amortismana sokuldu. *lpszLinkMarkup* parametresini belirten ilk formu kullanın.

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a>CLinkCtrl::GetIdealHeight

Bağlantı denetiminin ideal yüksekliğini alır.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel olarak kontrolün ideal yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/lm-getidealheight)iletisinin LM_GETIDEALHEIGHT davranışını uygular.

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a>CLinkCtrl::GetIdealSize

Bağlantının belirtilen genişliğine bağlı olarak, geçerli bağlantı denetimi için bağlantı metninin tercih edilen yüksekliğini hesaplar.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*cxMaxGenişlik*|[içinde] Piksellerde bağlantının maksimum genişliği.|
|[çıkış] \* *pSize*|Windows [SIZE](/windows/win32/api/windef/ns-windef-size) yapısına işaretçi. Bu yöntem döndüğünde, *cy* yapının `SIZE` cy üyesi *cxMaxWidth*tarafından belirtilen bağlantı metin genişliği için ideal bağlantı metin yüksekliği içerir. Yapının *cx* üyesi, gerçekte gerekli olan bağlantı metin genişliğini içerir.|

### <a name="return-value"></a>Dönüş Değeri

Bağlantı metninin piksel olarak tercih edilen yüksekliği. İade değeri, `SIZE` yapının *cy* üyesinin değeriyle aynıdır.

### <a name="remarks"></a>Açıklamalar

Yöntemin `GetIdealSize` bir örneği [için, CLinkCtrl'deki](#create)örneğe bakın:Oluştur .

Bu yöntem, Windows SDK'da açıklanan [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) iletisini gönderir.

## <a name="clinkctrlgetitem"></a><a name="getitem"></a>CLinkCtrl::GetItem

Bağlantı denetim öğesinin durumlarını ve özniteliklerini alır.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Madde bilgilerini almak için [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [LM_GETITEM](/windows/win32/Controls/lm-getitem)davranışını uygular.

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a>CLinkCtrl::GetItemID

Bağlantı denetim öğesinin kimliğini alır.

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

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*strID*<br/>
Belirtilen öğenin kimliğini içeren bir [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

*szID*<br/>
Belirtilen öğenin kimliğini içeren null-sonlandırılan dize.

*cchID*<br/>
*szID* arabelleği karakterlerindeki boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

> [!NOTE]
> *SzID veya strID* arabelleği MAX_LINKID_TEXT daha küçükse, bu işlev de FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin kimliğini alır. Daha fazla bilgi için Windows SDK'da [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 iletisi'ne bakın.

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a>CLinkCtrl::GetItemState

Bağlantı denetim öğesinin durumunu alır.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Parametreler

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*pnState*<br/>
Belirtilen durum öğesinin değeri.

*stateMask*<br/>
Hangi durum öğesinin alınabilmek için açıklayan bayrakların birleşimi. Değerler listesi için [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) yapısındaki `state` üyenin açıklamasına bakın. İzin verilen öğeler, izin `state`verilenöğelerle aynıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin belirtilen durum öğesinin değerini alır. Daha fazla bilgi için Windows SDK'da [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 iletisi'ne bakın.

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a>CLinkCtrl::GetItemUrl

Bağlantı denetim öğesi tarafından temsil edilen URL'yi alır.

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

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*strUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL'yi içeren bir [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL'yi içeren null-sonlandırılmış dize

*cchUrl*<br/>
*szURL* arabelleği karakterlerindeki boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

> [!NOTE]
> *SzUrl veya strUrl* arabelleği MAX_LINKID_TEXT daha küçükse, bu işlev de FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesi tarafından temsil edilen URL'yi alır. Daha fazla bilgi için Windows SDK'da [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 iletisi'ne bakın.

## <a name="clinkctrlhittest"></a><a name="hittest"></a>CLinkCtrl::HitTest

Kullanıcının belirtilen bağlantıyı tıklayıp tıklatmamasını belirler.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Parametreler

*phti*<br/>
Kullanıcının `LHITTESTINFO` tıklattığı bağlantı hakkinda herhangi bir bilgi içeren bir yapıya işleşme.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [LM_HITTEST](/windows/win32/Controls/lm-hittest)davranışını uygular.

## <a name="clinkctrlsetitem"></a><a name="setitem"></a>CLinkCtrl::SetItem

Bağlantı denetim öğesinin durumlarını ve özniteliklerini ayarlar.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Ayarlanan bilgileri içeren bir [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/lm-setitem)iletisinin LM_SETITEM davranışını uygular.

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a>CLinkCtrl::SetItemID

Bağlantı denetim öğesinin kimliğini alır.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Parametreler

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*szID*<br/>
Belirtilen öğenin kimliğini içeren null-sonlandırılan dize.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin kimliğini ayarlar. Daha fazla bilgi için Windows SDK'da [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 iletisi'ne bakın.

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a>CLinkCtrl::SetItemState

Bağlantı denetim öğesinin durumunu alır.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Parametreler

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*pnState*<br/>
Ayarlanan belirtilen durum öğesinin değeri.

*stateMask*<br/>
Ayarlanan durum öğesini açıklayan bayrakların birleşimi. Değerler listesi için [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) yapısındaki `state` üyenin açıklamasına bakın. İzin verilen öğeler, izin `state`verilenöğelerle aynıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin belirtilen durum öğesinin değerini ayarlar. Daha fazla bilgi için Windows SDK'da [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 iletisi'ne bakın.

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a>CLinkCtrl::SetItemUrl

Bağlantı denetim öğesi tarafından temsil edilen URL'yi ayarlar.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*Ilink*<br/>
Bağlantı denetim öğesinin dizini.

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL'yi içeren null-sonlandırılmış dize

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesi tarafından temsil edilen URL'yi ayarlar. Daha fazla bilgi için Windows SDK'da [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 iletisi'ne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
