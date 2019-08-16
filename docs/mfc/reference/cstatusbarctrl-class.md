---
title: CStatusBarCtrl sınıfı
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
ms.openlocfilehash: 8c33aa4d77eeeeca69e50dc63982ff4d7e8bd505
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502317"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl sınıfı

Windows ortak durum çubuğu denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBarCtrl:: CStatusBarCtrl](#cstatusbarctrl)|Bir `CStatusBarCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBarCtrl:: Create](#create)|Bir durum çubuğu denetimi oluşturur ve bunu bir `CStatusBarCtrl` nesneye ekler.|
|[CStatusBarCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir durum çubuğu denetimi oluşturur ve bunu bir `CStatusBarCtrl` nesneye ekler.|
|[CStatusBarCtrl::D rawItem](#drawitem)|Sahip çizimi bir durum çubuğu denetiminin görsel bir yönü değiştiğinde çağırılır.|
|[CStatusBarCtrl:: Getkenarlýklar](#getborders)|Durum çubuğu denetiminin yatay ve dikey kenarlıklarının geçerli genişliklerini alır.|
|[CStatusBarCtrl:: GetIcon](#geticon)|Geçerli durum çubuğu denetimindeki bir bölümün (bölme olarak da bilinir) simgesini alır.|
|[CStatusBarCtrl:: GetParts](#getparts)|Durum çubuğu denetimindeki parçaların sayısını alır.|
|[CStatusBarCtrl:: GetRect](#getrect)|Durum çubuğu denetimindeki bir parçanın sınırlayıcı dikdörtgenini alır.|
|[CStatusBarCtrl:: GetText](#gettext)|Durum çubuğu denetiminin verilen bölümünün metnini alır.|
|[CStatusBarCtrl:: GetTextLength](#gettextlength)|Durum çubuğu denetiminin verilen bölümündeki metnin karakter cinsinden uzunluğunu alın.|
|[CStatusBarCtrl:: GetTipText](#gettiptext)|Durum çubuğundaki bir bölme için araç ipucu metnini alır.|
|[CStatusBarCtrl:: IsSimple](#issimple)|Basit modda olup olmadığını anlamak için durum penceresi denetimini denetler.|
|[CStatusBarCtrl:: SetBkColor](#setbkcolor)|Durum çubuğundaki arka plan rengini ayarlar.|
|[CStatusBarCtrl:: SetIcon](#seticon)|Durum çubuğundaki bir bölmenin simgesini ayarlar.|
|[CStatusBarCtrl:: SetMinHeight](#setminheight)|Bir durum çubuğu denetiminin çizim alanının minimum yüksekliğini ayarlar.|
|[CStatusBarCtrl:: SetParts](#setparts)|Bir durum çubuğu denetimindeki parça sayısını ve her parçanın sağ kenarının koordinatını belirler.|
|[CStatusBarCtrl:: SetSimple](#setsimple)|Bir durum çubuğu denetiminin basit metin görüntüleyip görüntülemediğini veya önceki bir çağrısıyla `SetParts`ayarlanan tüm denetim parçalarını görüntülediğini belirtir.|
|[CStatusBarCtrl:: SetText](#settext)|Durum çubuğu denetiminin verilen bölümündeki metni ayarlar.|
|[CStatusBarCtrl:: SetTipText](#settiptext)|Durum çubuğundaki bir bölme için araç ipucu metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir "durum çubuğu denetimi", genellikle bir üst pencerenin altında görüntülenen ve bir uygulamanın çeşitli durum bilgilerini görüntüleyebilen bir yatay penceredir. Durum çubuğu denetimi, birden fazla bilgi türü göstermek için parçalara ayrılabilir.

Bu denetim (ve bu nedenle `CStatusBarCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kullanma `CStatusBarCtrl`hakkında daha fazla bilgi için bkz. [denetimler](../../mfc/controls-mfc.md) ve [CStatusBarCtrl kullanma](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="create"></a>CStatusBarCtrl:: Create

Bir durum çubuğu denetimi oluşturur ve bunu bir `CStatusBarCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Windows SDK [ortak denetim stillerinde](/windows/win32/Controls/common-control-styles) listelenen durum çubuğu denetim stillerinin herhangi bir birleşimini uygulayın. Bu parametre WS_CHILD stilini içermelidir. Ayrıca, WS_VISIBLE stilini de içermelidir.

*Rect*<br/>
Durum çubuğu denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
Durum çubuğu denetiminin üst penceresini (genellikle a `CDialog`) belirtir. NULL olmaması gerekir.

*NID*<br/>
Durum çubuğu denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

İki adımda oluşturursunuz `CStatusBarCtrl` . İlk olarak, oluşturucuyu çağırın ve sonra durum çubuğu `Create`denetimini oluşturan ve bunu `CStatusBarCtrl` nesnesine ekleyen çağırın.

Bir durum penceresinin varsayılan konumu üst pencerenin en altında bulunur, ancak üst pencerenin istemci alanının en üstünde görünmesini sağlamak için CCS_TOP stilini de belirtebilirsiniz. Durum penceresinin sağ ucuna bir boyutlandırma tutamacı eklemek için SBARS_SIZEGRIP stilini belirtebilirsiniz. CCS_TOP ve SBARS_SIZEGRIP stillerinin birleştirilmesi önerilmez, çünkü bu durum, sistem durumu penceresinde çizse bile, ortaya çıkan boyutlandırma tutamacı işlevsel değildir.

Genişletilmiş pencere stilleriyle bir durum çubuğu oluşturmak için yerine `Create` [CStatusBarCtrl:: CreateEx](#createex) çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

##  <a name="createex"></a>CStatusBarCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CStatusBarCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Windows SDK [ortak denetim stillerinde](/windows/win32/Controls/common-control-styles) listelenen durum çubuğu denetim stillerinin herhangi bir birleşimini uygulayın. Bu parametre WS_CHILD stilini içermelidir. Ayrıca, WS_VISIBLE stilini de içermelidir.

*Rect*<br/>
*PParentWnd*istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stili önsöz **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

##  <a name="cstatusbarctrl"></a>CStatusBarCtrl:: CStatusBarCtrl

Bir `CStatusBarCtrl` nesnesi oluşturur.

```
CStatusBarCtrl();
```

##  <a name="drawitem"></a>CStatusBarCtrl::D rawItem

Sahip çizimi bir durum çubuğu denetiminin görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`DRAWITEMSTRUCT` Yapının üyesi gerçekleştirilecek çizim eylemini tanımlar. `itemAction`

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim `CStatusBarCtrl` nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın.

Uygulamanın, bu üye işlevi sonlandırılmadan önce *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

##  <a name="getborders"></a>CStatusBarCtrl:: Getkenarlýklar

Durum çubuğu denetiminin yatay ve dikey kenarlıkların geçerli genişliklerini ve dikdörtgenler arasındaki boşluğu alır.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Parametreler

*Pkenarlýklar*<br/>
Üç öğeye sahip bir tamsayı dizisinin adresi. İlk öğe yatay kenarlığın genişliğini alır, ikincisi dikey kenarlığın genişliğini alır ve üçüncüsü, dikdörtgenler arasındaki kenarlığın genişliğini alır.

*nHorz*<br/>
Yatay kenarlığın genişliğini alan bir tamsayıya başvuru.

*Dönüştü*<br/>
Dikey kenarlığın genişliğini alan bir tamsayıya başvuru.

*nSpacing*<br/>
Dikdörtgenler arasındaki kenarlığın genişliğini alan bir tamsayıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu kenarlıklar, denetimin dış kenarı ve metin içeren denetim içindeki dikdörtgenler arasındaki boşluğu belirler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

##  <a name="geticon"></a>CStatusBarCtrl:: GetIcon

Geçerli durum çubuğu denetimindeki bir bölümün (bölme olarak da bilinir) simgesini alır.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ıpart*|'ndaki Alınacak simgeyi içeren parçanın sıfır tabanlı dizini. Bu parametre-1 ise, durum çubuğunun bir basit mod durum çubuğu olduğu varsayılır.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa simgenin tutamacı. Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [SB_GETICON](/windows/win32/Controls/sb-geticon) iletisini gönderir.

Durum çubuğu denetimi, parçalar olarak da bilinen metin çıkış bölmelerinin bir satırından oluşur. Durum çubuğu hakkında daha fazla bilgi için bkz. [MFC 'de durum çubuğu uygulama](../../mfc/status-bar-implementation-in-mfc.md) ve [CStatusBarCtrl nesnesinin modunu ayarlama](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli durum çubuğu denetimine `m_statusBar`erişmek için kullanılan bir değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir simgeyi geçerli durum çubuğu denetiminin iki bölmesine kopyalar. Kod örneğinde daha önceki bir bölümde, üç bölmeden oluşan bir durum çubuğu denetimi oluşturdunuz ve ardından ilk bölmeye bir simge ekledik. Bu örnek, ilk bölmeden simgesini alır ve sonra ikinci ve üçüncü bölmeye ekler.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

##  <a name="getparts"></a>CStatusBarCtrl:: GetParts

Durum çubuğu denetimindeki parçaların sayısını alır.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Parametreler

*Nparçalar*<br/>
Koordinatları alınacak parça sayısı. Bu parametre denetimdeki parçaların sayısından büyükse ileti yalnızca varolan parçaların koordinatlarını alır.

*pParts 'lar*<br/>
*NParts*tarafından belirtilen parça sayısıyla aynı sayıda öğeye sahip bir tamsayı dizisinin adresi. Dizideki her öğe, ilgili bölümün sağ kenarının istemci koordinatını alır. Bir öğe-1 olarak ayarlandıysa, bu bölüm için sağ kenarın konumu durum çubuğunun sağ kenarına genişletilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa denetimdeki parçaların sayısı veya yoksa sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, verilen parça sayısının sağ kenarının koordinatını de alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

##  <a name="getrect"></a>CStatusBarCtrl:: GetRect

Durum çubuğu denetimindeki bir parçanın sınırlayıcı dikdörtgenini alır.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Sınırlayıcı dikdörtgeni alınacak olan bölümün sıfır tabanlı dizini.

*lpRect*<br/>
Sınırlayıcı dikdörtgeni alan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısının adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

##  <a name="gettext"></a>CStatusBarCtrl:: GetText

Durum çubuğu denetiminin verilen bölümünün metnini alır.

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

*lpszText*<br/>
Metni alan arabelleğin adresi. Bu parametre, null ile sonlandırılmış bir dizedir.

*nPane*<br/>
Metnin alınacağı bölümün sıfır tabanlı dizini.

*pType*<br/>
Tür bilgilerini alan tamsayı işaretçisi. Tür şu değerlerden biri olabilir:

- **0** metin, durum çubuğunun düzleminden daha düşük görünmesi için bir kenarlıkla çizilir.

- SBT_NOBORDERS metin kenarlıklar olmadan çizilir.

- SBT_POPOUT metin, durum çubuğunun düzleminden daha yüksek görünmesi için bir kenarlıkla çizilir.

- SBT_OWNERDRAW metin SBT_OWNERDRAW çizim türüne sahipse, *pType* bu iletiyi alır ve uzunluğu ve işlem türü yerine metinle ilişkili 32 bitlik değeri döndürür.

### <a name="return-value"></a>Dönüş Değeri

Metnin veya geçerli metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) uzunluğu (karakter).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

##  <a name="gettextlength"></a>CStatusBarCtrl:: GetTextLength

Durum çubuğu denetiminin verilen bölümündeki metnin uzunluğunu karakter olarak alır.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Metnin alınacağı bölümün sıfır tabanlı dizini.

*pType*<br/>
Tür bilgilerini alan tamsayı işaretçisi. Tür şu değerlerden biri olabilir:

- **0** metin, durum çubuğunun düzleminden daha düşük görünmesi için bir kenarlıkla çizilir.

- SBT_NOBORDERS metin kenarlıklar olmadan çizilir.

- SBT_OWNERDRAW metin üst pencere tarafından çizilir.

- SBT_POPOUT metin, durum çubuğunun düzleminden daha yüksek görünmesi için bir kenarlıkla çizilir.

### <a name="return-value"></a>Dönüş Değeri

Metnin karakter cinsinden uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

##  <a name="gettiptext"></a>CStatusBarCtrl:: GetTipText

Durum çubuğundaki bir bölme için araç ipucu metnini alır.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Araç ipucu metnini almak için durum çubuğu bölmesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Araç ipucunda kullanılacak metni içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [SB_GETTIPTEXT](/windows/win32/Controls/sb-gettiptext)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

##  <a name="issimple"></a>CStatusBarCtrl:: IsSimple

Basit modda olup olmadığını anlamak için durum penceresi denetimini denetler.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum penceresi denetimi basit modda ise sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [SB_ISSIMPLE](/windows/win32/Controls/sb-issimple)davranışını uygular.

##  <a name="setbkcolor"></a>CStatusBarCtrl:: SetBkColor

Durum çubuğundaki arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*Return*<br/>
Yeni arka plan rengini belirten COLORREF değeri. Durum çubuğunun varsayılan arka plan rengini kullanmasını sağlamak için CLR_DEFAULT değerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Önceki varsayılan arka plan rengini temsil eden bir [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [SB_SETBKCOLOR](/windows/win32/Controls/sb-setbkcolor)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

##  <a name="seticon"></a>CStatusBarCtrl:: SetIcon

Durum çubuğundaki bir bölmenin simgesini ayarlar.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Simgeyi alacak olan bölmenin sıfır tabanlı dizini. Bu parametre-1 ise, durum çubuğunun bir basit durum çubuğu olduğu varsayılır.

*HICON*<br/>
Ayarlanacak simgeye yönelik işleyici. Bu değer NULL ise, simge bölümden kaldırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [SB_SETICON](/windows/win32/Controls/sb-seticon)davranışını uygular.

### <a name="example"></a>Örnek

  [CStatusBarCtrl:: SetBkColor](#setbkcolor)örneğine bakın.

##  <a name="setminheight"></a>CStatusBarCtrl:: SetMinHeight

Bir durum çubuğu denetiminin çizim alanının minimum yüksekliğini ayarlar.

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
Denetimin piksel cinsinden minimum yüksekliği.

### <a name="remarks"></a>Açıklamalar

En küçük yükseklik, durum çubuğu denetiminin dikey kenarlığının piksel cinsinden, *nMin* toplamı ve genişliğinin iki katından oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

##  <a name="setparts"></a>CStatusBarCtrl:: SetParts

Bir durum çubuğu denetimindeki parça sayısını ve her parçanın sağ kenarının koordinatını belirler.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Parametreler

*Nparçalar*<br/>
Ayarlanacak bölüm sayısı. Parça sayısı 255 ' den büyük olamaz.

*Pgenişlikleri*<br/>
*NParts*tarafından belirtilen parçalar ile aynı sayıda öğeye sahip bir tamsayı dizisinin adresi. Dizideki her öğe, ilgili bölümün sağ kenarının istemci koordinatlarındaki konumu belirtir. Bir öğe-1 ise, bu bölüm için sağ kenarın konumu denetimin sağ kenarına genişletilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

##  <a name="setsimple"></a>CStatusBarCtrl:: SetSimple

Bir durum çubuğu denetiminin basit metin görüntüleyip görüntülemediğini veya önceki bir [SetParts](#setparts)çağrısıyla ayarlanan tüm denetim parçalarını görüntülediğini belirtir.

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSimple*<br/>
'ndaki Görüntüleme türü bayrağı. Bu parametre TRUE ise, denetim basit metin görüntüler; YANLıŞ ise, birden çok parça görüntüler.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanız durum çubuğu denetimini basit olmayan veya basit dışında bir şekilde değiştirirse, sistem denetimi hemen yeniden çizer.

##  <a name="settext"></a>CStatusBarCtrl:: SetText

Durum çubuğu denetiminin verilen bölümündeki metni ayarlar.

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Ayarlanacak metni belirten null ile sonlandırılmış bir dizenin adresi. *NType* SBT_OWNERDRAW Ise, *lpszText* 32 bitlik verileri temsil eder.

*nPane*<br/>
Ayarlanacak bölümün sıfır tabanlı dizini. Bu değer 255 ise, durum çubuğu denetiminin yalnızca bir bölümü olan basit bir denetim olduğu varsayılır.

*nTür*<br/>
Çizim işleminin türü. Olası değerler listesi için bkz. [SB_SETTEXT Message](/windows/win32/Controls/sb-settext) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

İleti, denetimin bir sonraki WM_PAINT iletisini aldığında yeni metni görüntülemesine neden olan denetimin bölümünü geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

##  <a name="settiptext"></a>CStatusBarCtrl:: SetTipText

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
Araç ipucu metnini içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [SB_SETTIPTEXT](/windows/win32/Controls/sb-settiptext)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)
