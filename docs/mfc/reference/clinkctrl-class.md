---
description: 'Daha fazla bilgi edinin: CLinkCtrl sınıfı'
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
ms.openlocfilehash: a9a106d7511757fac0abfd19194081729a7d4977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236769"
---
# <a name="clinkctrl-class"></a>CLinkCtrl sınıfı

Windows ortak SysLink denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLinkCtrl:: CLinkCtrl](#clinkctrl)|Bir `CLinkCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLinkCtrl:: Create](#create)|Bir bağlantı denetimi oluşturur ve bunu bir nesneye ekler `CLinkCtrl` .|
|[CLinkCtrl:: CreateEx](#createex)|Genişletilmiş stillerle bir bağlantı denetimi oluşturur ve bunu bir `CLinkCtrl` nesneye ekler.|
|[CLinkCtrl:: Getıfheight yüksekliği](#getidealheight)|Bağlantı denetiminin ideal yüksekliğini alır.|
|[CLinkCtrl:: Getısatıcıboyutu](#getidealsize)|Bağlantının belirtilen genişliğine bağlı olarak, geçerli bağlantı denetimi için bağlantı metninin tercih edilen yüksekliğini hesaplar.|
|[CLinkCtrl:: GetItem](#getitem)|Bir bağlantı denetim öğesinin durumlarını ve özniteliklerini alır.|
|[CLinkCtrl:: GetItemID](#getitemid)|Bir bağlantı denetimi öğesinin KIMLIĞINI alır.|
|[CLinkCtrl:: GetItemState](#getitemstate)|Bağlantı denetimi öğesinin durumunu alır.|
|[CLinkCtrl:: Getıtemurl 'Si](#getitemurl)|Bağlantı denetim öğesi tarafından temsil edilen URL 'YI alır.|
|[CLinkCtrl:: HitTest](#hittest)|Kullanıcının belirtilen bağlantıyı tıkladığını belirler.|
|[CLinkCtrl:: SetItem](#setitem)|Bir bağlantı denetim öğesinin durumlarını ve özniteliklerini ayarlar.|
|[CLinkCtrl:: Setıtemıd](#setitemid)|Bir bağlantı denetimi öğesinin KIMLIĞINI ayarlar.|
|[CLinkCtrl:: SetItemState](#setitemstate)|Bağlantı denetimi öğesinin durumunu ayarlar.|
|[CLinkCtrl:: Setıtemurl](#setitemurl)|Bağlantı denetim öğesiyle temsil edilen URL 'YI ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Bağlantı denetimi", bir pencereye hypertext bağlantıları eklemek için kullanışlı bir yol sağlar. Gerçek denetim, işaretlenmiş metni işleyen ve Kullanıcı katıştırılmış bir bağlantıyı tıklattığında uygun uygulamaları başlatan bir penceredir. Birden çok bağlantı tek denetimde desteklenir ve sıfır tabanlı bir dizin tarafından erişilebilir.

Bu denetim (ve bu nedenle `CLinkCtrl` sınıfı) yalnızca WINDOWS XP ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Daha fazla bilgi için Windows SDK [Syslink Control](/windows/win32/Controls/syslink-overview) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a> CLinkCtrl:: CLinkCtrl

Bir `CLinkCtrl` nesnesi oluşturur.

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a> CLinkCtrl:: Create

Bir bağlantı denetimi oluşturur ve bunu bir nesneye ekler `CLinkCtrl` .

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
Görüntülenecek işaretli metni içeren sıfır ile sonlandırılmış bir dize işaretçisi. Daha fazla bilgi için [SysLink denetimlerine genel bakış](/windows/win32/Controls/syslink-overview)konusundaki "biçimlendirme ve bağlantı erişimi" bölümüne bakın.

*dwStyle*<br/>
Bağlantı denetiminin stilini belirtir. Denetim stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için bkz. içindeki [ortak denetim stilleri](/windows/win32/Controls/common-control-styles) `Windows SDK` .

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresini belirtir. NULL olmaması gerekir.

*NID*<br/>
Bağlantı denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`CLinkCtrl`İki adımda bir nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` bağlantı denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CLinkCtrl` . Denetimi ile genişletilmiş Windows stilleri kullanmak istiyorsanız, yerine [CLinkCtrl:: CreateEx](#createex) çağırın `Create` .

Yöntemin ikinci biçimi `Create` kullanım dışıdır. *LpszLinkMarkup* parametresini belirten ilk formu kullanın.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_Link1` `m_Link2` iki bağlantı denetimine erişmek için kullanılan ve adlı iki değişkeni tanımlar.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, başka bir bağlantı denetiminin konumunu temel alan bir bağlantı denetimi oluşturur. Kaynak yükleyicisi, uygulamanız başlatıldığında ilk bağlantı denetimini oluşturur. Uygulamanız OnInitDialog yöntemine girdiğinde, ilk bağlantı denetiminin konumuyla ilişkili ikinci bağlantı denetimini oluşturursunuz. Daha sonra ikinci bağlantı denetimini gösterdiği metne sığacak şekilde yeniden boyutlandırın.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a> CLinkCtrl:: CreateEx

Genişletilmiş stillerle bir bağlantı denetimi oluşturur ve bunu bir `CLinkCtrl` nesneye ekler.

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
Görüntülenecek işaretli metni içeren sıfır ile sonlandırılmış bir dize işaretçisi. Daha fazla bilgi için [SysLink denetimlerine genel bakış](/windows/win32/Controls/syslink-overview)konusundaki "biçimlendirme ve bağlantı erişimi" bölümüne bakın.

*dwExStyle*<br/>
Bağlantı denetiminin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Bağlantı denetiminin stilini belirtir. Denetim stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için, bkz. Windows SDK [ortak denetim stilleri](/windows/win32/Controls/common-control-styles) .

*Rect*<br/>
Bağlantı denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Bağlantı denetiminin üst penceresini belirtir. NULL olmaması gerekir.

*NID*<br/>
Bağlantı denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Genişletilmiş Windows stili sabitleri uygulamak Için [Oluştur](#create) yerine kullanın.

Yöntemin ikinci biçimi `CreateEx` kullanım dışıdır. *LpszLinkMarkup* parametresini belirten ilk formu kullanın.

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a> CLinkCtrl:: Getıfheight yüksekliği

Bağlantı denetiminin ideal yüksekliğini alır.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin piksel cinsinden ideal yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [LM_GETIDEALHEIGHT](/windows/win32/Controls/lm-getidealheight)davranışını uygular.

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a> CLinkCtrl:: Getısatıcıboyutu

Bağlantının belirtilen genişliğine bağlı olarak, geçerli bağlantı denetimi için bağlantı metninin tercih edilen yüksekliğini hesaplar.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Parametreler

*cxMaxWidth*\
'ndaki En fazla bağlantının genişliği (piksel cinsinden).

*Psıze*\
dışı Windows [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına yönelik bir işaretçi. Bu yöntem döndüğünde, yapının *Cy* üyesi, `SIZE` *cxMaxWidth* tarafından belirtilen bağlantı metni genişliği için ideal bağlantı metin yüksekliğini içerir. Yapının *CX* üyesi, gerçekten gerekli olan bağlantı metni genişliğini içerir.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı metninin tercih edilen yüksekliği (piksel cinsinden). Dönüş değeri, yapının *Cy* üyesinin değeri ile aynıdır `SIZE` .

### <a name="remarks"></a>Açıklamalar

`GetIdealSize`Yöntemine örnek olarak, [CLinkCtrl:: Create](#create)içindeki örneğe bakın.

Bu yöntem, Windows SDK açıklanan [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) iletisini gönderir.

## <a name="clinkctrlgetitem"></a><a name="getitem"></a> CLinkCtrl:: GetItem

Bir bağlantı denetim öğesinin durumlarını ve özniteliklerini alır.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Öğe bilgilerini almak için bir [Lidıtem](/windows/win32/api/commctrl/ns-commctrl-litem) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [LM_GETITEM](/windows/win32/Controls/lm-getitem)davranışını uygular.

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a> CLinkCtrl:: GetItemID

Bir bağlantı denetimi öğesinin KIMLIĞINI alır.

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

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*strID*<br/>
Belirtilen öğenin KIMLIĞINI içeren bir [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

*szID*<br/>
Belirtilen öğenin KIMLIĞINI içeren null ile sonlandırılmış bir dize.

*Cchıd*<br/>
*SzID* arabelleğinin karakter cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

> [!NOTE]
> Bu işlev, *szID veya Çabad* arabelleği MAX_LINKID_TEXT daha KÜÇÜKSE de false döndürür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetimi öğesinin KIMLIĞINI alır. Daha fazla bilgi için Windows SDK Win32 ileti [LM_GETITEM](/windows/win32/Controls/lm-getitem) bakın.

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a> CLinkCtrl:: GetItemState

Bağlantı denetimi öğesinin durumunu alır.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Parametreler

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*pnState*<br/>
Belirtilen durum öğesinin değeri.

*stateMask*<br/>
Hangi durum öğesinin alınacağını açıklayan bayrakların birleşimi. Değerlerin listesi için, `state` [lidıtem](/windows/win32/api/commctrl/ns-commctrl-litem) yapısındaki üyenin açıklamasına bakın. İzin verilen öğeler, içinde izin verilen olanlarla aynıdır `state` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin belirtilen durum öğesinin değerini alır. Daha fazla bilgi için Windows SDK Win32 ileti [LM_GETITEM](/windows/win32/Controls/lm-getitem) bakın.

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a> CLinkCtrl:: Getıtemurl 'Si

Bağlantı denetim öğesi tarafından temsil edilen URL 'YI alır.

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

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*strUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL 'YI içeren bir [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL 'YI içeren null ile sonlandırılmış bir dize

*cchUrl*<br/>
*SzUrl* arabelleğinin karakter cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

> [!NOTE]
> *SzUrl veya strUrl* arabelleği MAX_LINKID_TEXT daha küçükse bu Işlev de false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesi tarafından temsil edilen URL 'YI alır. Daha fazla bilgi için Windows SDK Win32 ileti [LM_GETITEM](/windows/win32/Controls/lm-getitem) bakın.

## <a name="clinkctrlhittest"></a><a name="hittest"></a> CLinkCtrl:: HitTest

Kullanıcının belirtilen bağlantıyı tıkladığını belirler.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Parametreler

*phtı*<br/>
`LHITTESTINFO`Kullanıcının tıklamadığı bağlantı hakkında herhangi bir bilgi içeren bir yapıya yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [LM_HITTEST](/windows/win32/Controls/lm-hittest)davranışını uygular.

## <a name="clinkctrlsetitem"></a><a name="setitem"></a> CLinkCtrl:: SetItem

Bir bağlantı denetim öğesinin durumlarını ve özniteliklerini ayarlar.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Ayarlanacak bilgileri içeren bir [Lidıtem](/windows/win32/api/commctrl/ns-commctrl-litem) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [LM_SETITEM](/windows/win32/Controls/lm-setitem)davranışını uygular.

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a> CLinkCtrl:: Setıtemıd

Bir bağlantı denetimi öğesinin KIMLIĞINI alır.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Parametreler

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*szID*<br/>
Belirtilen öğenin KIMLIĞINI içeren null ile sonlandırılmış bir dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetimi öğesinin KIMLIĞINI ayarlar. Daha fazla bilgi için Windows SDK Win32 ileti [LM_SETITEM](/windows/win32/Controls/lm-setitem) bakın.

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a> CLinkCtrl:: SetItemState

Bağlantı denetimi öğesinin durumunu alır.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Parametreler

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*pnState*<br/>
Ayarlanan belirtilen durum öğesinin değeri.

*stateMask*<br/>
Ayarlanmakta olan durum öğesini açıklayan bayrakların birleşimi. Değerlerin listesi için, `state` [lidıtem](/windows/win32/api/commctrl/ns-commctrl-litem) yapısındaki üyenin açıklamasına bakın. İzin verilen öğeler, içinde izin verilen olanlarla aynıdır `state` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirli bir bağlantı denetim öğesinin belirtilen durum öğesinin değerini ayarlar. Daha fazla bilgi için Windows SDK Win32 ileti [LM_SETITEM](/windows/win32/Controls/lm-setitem) bakın.

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a> CLinkCtrl:: Setıtemurl

Bağlantı denetim öğesiyle temsil edilen URL 'YI ayarlar.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*ILink*<br/>
Bir bağlantı denetimi öğesinin dizini.

*szUrl*<br/>
Belirtilen öğe tarafından temsil edilen URL 'YI içeren null ile sonlandırılmış bir dize

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Belirtilen bağlantı denetim öğesiyle temsil edilen URL 'YI ayarlar. Daha fazla bilgi için Windows SDK Win32 ileti [LM_SETITEM](/windows/win32/Controls/lm-setitem) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)
