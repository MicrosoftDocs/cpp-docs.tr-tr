---
title: CStatusBarCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: 7a594fdb2d3a35ce905b7790026f7418b7435f3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366025"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl Sınıfı

Windows ortak durum çubuğu denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Bir `CStatusBarCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStatusBarCtrl::Oluştur](#create)|Durum çubuğu denetimi oluşturur ve nesneye `CStatusBarCtrl` bağlar.|
|[CStatusBarCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir durum çubuğu denetimi oluşturur `CStatusBarCtrl` ve bir nesneye bağlar.|
|[CStatusBarCtrl::DrawItem](#drawitem)|Sahibi-beraberlik durum çubuğu denetiminin görsel bir yönü değiştiğinde çağrılır.|
|[CStatusBarCtrl::GetBorders](#getborders)|Durum çubuğu denetiminin yatay ve dikey kenarlıklarının geçerli genişliklerini alır.|
|[CStatusBarCtrl::GetIcon](#geticon)|Geçerli durum çubuğu denetiminde bir parça (bölme olarak da bilinir) için simgeyi alır.|
|[CStatusBarCtrl::GetParts](#getparts)|Durum çubuğu denetimindeki parçaların sayısını alır.|
|[CStatusBarCtrl::GetRect](#getrect)|Durum çubuğu denetiminde bir parçanın sınırlayıcı dikdörtgenini alır.|
|[CStatusBarCtrl::GetText](#gettext)|Durumu çubuğu denetiminin verilen bölümünden metni alır.|
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Durum çubuğu denetiminin verilen bölümünden metnin karakter olarak uzunluğunu alın.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|Durum çubuğundaki bölmenin araç ipucu metnini alır.|
|[CStatusBarCtrl::Basit](#issimple)|Basit modda olup olmadığını belirlemek için durum penceresi denetimini denetler.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Durum çubuğunda arka plan rengini ayarlar.|
|[CStatusBarCtrl::SetIcon](#seticon)|Durum çubuğundaki bölme simgesini ayarlar.|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Durum çubuğu denetiminin çizim alanının minimum yüksekliğini ayarlar.|
|[CStatusBarCtrl::SetParts](#setparts)|Durum çubuğu denetimindeki parça sayısını ve her parçanın sağ kenarının koordinatını ayarlar.|
|[CStatusBarCtrl::SetSimple](#setsimple)|Durum çubuğu denetiminin basit bir metni gösterip görüntülemediğini veya önceki `SetParts`bir arama tarafından ayarlanan tüm denetim parçalarını gösterip görüntülemediğini belirtir.|
|[CStatusBarCtrl::SetText](#settext)|Durum çubuğu denetiminin verilen bölümündeki metni ayarlar.|
|[CStatusBarCtrl::SetTipText](#settiptext)|Durum çubuğundaki bir bölme için araç ipucu metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Durum çubuğu denetimi", genellikle bir uygulamanın çeşitli durum bilgilerini görüntüleyebildiği bir üst pencerenin alt kısmında görüntülenen yatay bir penceredir. Durum çubuğu denetimi, birden fazla bilgi türünü görüntülemek için parçalara ayrılabilir.

Bu denetim (ve `CStatusBarCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kullanma `CStatusBarCtrl`hakkında daha fazla bilgi [Using CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::Oluştur

Durum çubuğu denetimi oluşturur ve nesneye `CStatusBarCtrl` bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Windows SDK'da [Ortak Denetim Stilleri'nde](/windows/win32/Controls/common-control-styles) listelenen durum çubuğu denetim stillerinin herhangi bir birleşimini uygulayın. Bu parametre WS_CHILD stili içermelidir. Ayrıca WS_VISIBLE tarzı içermelidir.

*Rect*<br/>
Durum çubuğu denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
Durum çubuğu denetiminin üst penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Durum çubuğu denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CStatusBarCtrl` yapı inşa e. Önce oluşturucuyu çağırın, `Create`ardından durum çubuğu denetimini oluşturan ve `CStatusBarCtrl` nesneye iliştiren , çağırın.

Durum penceresinin varsayılan konumu üst pencerenin alt kısmındadır, ancak üst pencerenin istemci alanının üst kısmında görünmesini sağlamak için CCS_TOP stili belirtebilirsiniz. Durum penceresinin sağ ucunda boyutlandırma kavrama eklemek için SBARS_SIZEGRIP stilini belirtebilirsiniz. Sistem durum penceresinde çizse bile ortaya çıkan boyutlandırma kavrama işlevsel olmadığından, CCS_TOP ve SBARS_SIZEGRIP stilleri nin birleştirilmesi önerilmez.

Genişletilmiş pencere stillerine sahip bir durum çubuğu oluşturmak için [CStatusBarCtrl::CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CStatusBarCtrl` nesneyle ilişkilendirir.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Windows SDK'da [Ortak Denetim Stilleri'nde](/windows/win32/Controls/common-control-styles) listelenen durum çubuğu denetim stillerinin herhangi bir birleşimini uygulayın. Bu parametre WS_CHILD stili içermelidir. Ayrıca WS_VISIBLE tarzı içermelidir.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl

Bir `CStatusBarCtrl` nesne inşa eder.

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::DrawItem

Bir sahibi-beraberlik durum çubuğu denetiminin görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bir sahip çizim `CStatusBarCtrl` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın.

Uygulama, bu üye işlev sona erdirilmeden önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl::GetBorders

Durum çubuğu denetiminin yatay ve dikey kenarlıkların ve dikdörtgenler arasındaki boşluğun geçerli genişliklerini alır.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Parametreler

*pBorders*<br/>
Üç öğeye sahip bir bir sonda dizisinin adresi. İlk öğe yatay kenarlık genişliğini alır, ikinci dikey kenarlık genişliğini alır ve üçüncü dikdörtgenler arasındaki kenarlık genişliğini alır.

*nHorz*<br/>
Yatay kenarlık genişliğini alan bir karşıcıya başvuru.

*nVert*<br/>
Dikey kenarlık genişliğini alan bir karşıcıya başvuru.

*nSpacing*<br/>
Dikdörtgenler arasındaki kenarlık genişliğini alan bir karşıcıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu kenarlıklar, denetimin dış kenarı ile metin içeren denetim içindeki dikdörtgenler arasındaki aralığı belirler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon

Geçerli durum çubuğu denetiminde bir parça (bölme olarak da bilinir) için simgeyi alır.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iPart*|[içinde] Alınacak simgeyi içeren parçanın sıfır tabanlı dizin. Bu parametre -1 ise, durum çubuğu basit bir mod durum çubuğu olarak kabul edilir.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa simgenin tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [SB_GETICON](/windows/win32/Controls/sb-geticon) iletisini gönderir.

Durum çubuğu denetimi, parçalar olarak da bilinen bir metin çıktısı bölmeleri satırından oluşur. Durum çubuğu hakkında daha fazla bilgi için, [MFC'de Durum Çubuğu Uygulaması](../../mfc/status-bar-implementation-in-mfc.md) ve [CStatusBarCtrl Nesnesinin Modunu Ayarlama](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)bölümüne bakın.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_statusBar`geçerli durum çubuğu denetimine erişmek için kullanılan bir değişken tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli durum çubuğu denetiminin iki bölmesine bir simge kopyalar. Kod örneğinin önceki bir bölümünde üç bölmeli bir durum çubuğu denetimi oluşturduk ve ardından ilk bölmeye bir simge ekledik. Bu örnek, simgeyi ilk bölmeden alır ve ikinci ve üçüncü bölmeye ekler.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl::GetParts

Durum çubuğu denetimindeki parçaların sayısını alır.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Parametreler

*nParçalar*<br/>
Koordinatları almak için parça sayısı. Bu parametre denetimdeki parça sayısından büyükse, ileti yalnızca varolan parçaların koordinatlarını alır.

*pParts*<br/>
*nParts*tarafından belirtilen parça sayısı yla aynı sayıda öğeye sahip bir tamsayı dizisinin adresi. Dizideki her öğe, ilgili parçanın sağ kenarının istemci koordinatını alır. Bir öğe - 1 olarak ayarlanırsa, bu parçaiçin sağ kenarın konumu durum çubuğunun sağ kenarına kadar uzanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa denetimdeki parça sayısı veya aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev ayrıca verilen parça sayısının sağ kenarının koordinatını da alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl::GetRect

Durum çubuğu denetiminde bir parçanın sınırlayıcı dikdörtgenini alır.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Sınırlayıcı dikdörtgeni alınacak parçanın sıfır tabanlı dizin.

*Lprect*<br/>
Sınırlayıcı dikdörtgeni alan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısının adresi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText

Durumu çubuğu denetiminin verilen bölümünden metni alır.

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Metni alan arabelleğe ait adres. Bu parametre null-sonlandırılan dizedir.

*nPane*<br/>
Metin almak için hangi bölümün sıfır tabanlı dizin.

*pTipi*<br/>
Tür bilgilerini alan bir müslümede işaretçi. Tür şu değerlerden biri olabilir:

- **0** Metin, durum çubuğunun düzleminden daha düşük görünmesi için kenarlıkla çizilir.

- SBT_NOBORDERS Metin kenarlıksız çizilir.

- SBT_POPOUT Metin, durum çubuğunun düzleminden daha yüksek görünmesi için kenarlıkla çizilir.

- SBT_OWNERDRAW Metin SBT_OWNERDRAW çizim türüne sahipse, *pType* bu iletiyi alır ve uzunluk ve işlem türü yerine metinle ilişkili 32 bit değerini döndürür.

### <a name="return-value"></a>Dönüş Değeri

Karakter de, metnin veya geçerli metni içeren bir [CString'in](../../atl-mfc-shared/reference/cstringt-class.md) uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetTextLength

Durum çubuğu denetiminin verilen bölümünden metnin karakter olarak uzunluğunu alır.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Metin almak için hangi bölümün sıfır tabanlı dizin.

*pTipi*<br/>
Tür bilgilerini alan bir müslümede işaretçi. Tür şu değerlerden biri olabilir:

- **0** Metin, durum çubuğunun düzleminden daha düşük görünmesi için kenarlıkla çizilir.

- SBT_NOBORDERS Metin kenarlıksız çizilir.

- SBT_OWNERDRAW Metin üst pencere tarafından çizilir.

- SBT_POPOUT Metin, durum çubuğunun düzleminden daha yüksek görünmesi için kenarlıkla çizilir.

### <a name="return-value"></a>Dönüş Değeri

Metnin karakter uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText

Durum çubuğundaki bölmenin araç ipucu metnini alır.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Araç ipucu metnini almak için durum çubuğu bölmesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Araç uçlarında kullanılacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [SB_GETTIPTEXT](/windows/win32/Controls/sb-gettiptext)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::Basit

Basit modda olup olmadığını belirlemek için durum penceresi denetimini denetler.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum penceresi denetimi basit moddaysa sıfıra inme; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [SB_ISSIMPLE](/windows/win32/Controls/sb-issimple)davranışını uygular.

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor

Durum çubuğunda arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*Cr*<br/>
Yeni arka plan rengini belirten COLORREF değeri. Durum çubuğunun varsayılan arka plan rengini kullanmasına neden olacak CLR_DEFAULT değerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Önceki varsayılan arka plan rengini temsil eden bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [SB_SETBKCOLOR](/windows/win32/Controls/sb-setbkcolor)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::SetIcon

Durum çubuğundaki bölme simgesini ayarlar.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Simgeyi alacak bölmenin sıfır tabanlı dizin. Bu parametre -1 ise, durum çubuğu basit bir durum çubuğu olarak kabul edilir.

*Hıcon*<br/>
Ayarlanacak simgeye işleyin. Bu değer NULL ise, simge parçadan kaldırılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [SB_SETICON](/windows/win32/Controls/sb-seticon)davranışını uygular.

### <a name="example"></a>Örnek

  [CStatusBarCtrl::SetBkColor](#setbkcolor)için örneğe bakın.

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl::SetMinHeight

Durum çubuğu denetiminin çizim alanının minimum yüksekliğini ayarlar.

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Minimum yükseklik, piksel, kontrol.

### <a name="remarks"></a>Açıklamalar

Minimum yükseklik *nMin* toplamı ve iki kat genişlik, piksel, durum çubuğu denetiminin dikey kenarlığı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::SetParts

Durum çubuğu denetimindeki parça sayısını ve her parçanın sağ kenarının koordinatını ayarlar.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Parametreler

*nParçalar*<br/>
Ayarlanacak parça sayısı. Parça sayısı 255'ten büyük olamaz.

*p Genişlikler*<br/>
*nParts*tarafından belirtilen parçalarla aynı sayıda öğeye sahip bir tamsayı dizisinin adresi. Dizideki her öğe, istemci koordinatlarında, ilgili parçanın sağ kenarının konumunu belirtir. Bir öğe - 1 ise, o parça için sağ kenarın konumu denetimin sağ kenarına kadar uzanır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::SetSimple

Durum çubuğu denetiminin basit bir metni gösterip görüntülemediğini veya [SetParts'a](#setparts)önceki bir çağrıyla ayarlanan tüm denetim parçalarını gösterip görüntülemediğini belirtir.

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Parametreler

*bBasit*<br/>
[içinde] Görüntü tipi bayrak. Bu parametre TRUE ise, denetim basit metni görüntüler; FALSE ise, birden çok parça görüntüler.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanız durum çubuğu denetimini basit olmayandan basite veya tam tersi olarak değiştirirse, sistem denetimi hemen yeniden çizer.

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a>CStatusBarCtrl::SetText

Durum çubuğu denetiminin verilen bölümündeki metni ayarlar.

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Ayarlanması gereken metni belirten null-sonlandırılan bir dize adresi. *nType* SBT_OWNERDRAW ise, *lpszText* 32 bit veri temsil eder.

*nPane*<br/>
Ayarlanan parçanın sıfır tabanlı dizin. Bu değer 255 ise, durum çubuğu denetimi nin yalnızca bir bölüme sahip basit bir denetim olduğu varsayılır.

*nTipi*<br/>
Çizim işlemi türü. Olası değerlerin listesi için [SB_SETTEXT iletiye](/windows/win32/Controls/sb-settext) bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

İleti, denetimin değiştirilen bölümünü geçersiz kıldığında, denetim sonraki WM_PAINT iletisi aldığında yeni metni görüntülemesine neden olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a>CStatusBarCtrl::SetTipText

Durum çubuğundaki bir bölme için araç ipucu metnini ayarlar.

```
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Araç ipucu metnini almak için durum çubuğu bölmesinin sıfır tabanlı dizini.

*pszTipText*<br/>
Araç ipucu metnini içeren bir dize için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [SB_SETTIPTEXT](/windows/win32/Controls/sb-settiptext)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)
