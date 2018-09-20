---
title: CStatusBarCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc416c47634de522a20f81d7240cc1ea5797551
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392066"
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
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Oluşturur bir `CStatusBarCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStatusBarCtrl::Create](#create)|Durum çubuğu denetimi oluşturur ve ona bağlanan bir `CStatusBarCtrl` nesne.|
|[CStatusBarCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir durum çubuğu denetimi oluşturur ve ona bağlanan bir `CStatusBarCtrl` nesne.|
|[CStatusBarCtrl::DrawItem](#drawitem)|Görsel bir özelliği bir özelleştirilmiş çizimli durum çubuğu denetim değişikliklerinin çağrılır.|
|[CStatusBarCtrl::GetBorders](#getborders)|Geçerli bir durum çubuğu denetiminin yatay ve dikey kenarlık genişliğini alır.|
|[CStatusBarCtrl::GetIcon](#geticon)|Simge bir bölümü (bölme olarak da bilinir) için geçerli durum çubuğu denetimi alır.|
|[CStatusBarCtrl::GetParts](#getparts)|Durum çubuğu denetimi bölümlerini sayısını alır.|
|[CStatusBarCtrl::GetRect](#getrect)|Durum çubuğu denetimi içinde bir bölümü sınırlayıcı dikdörtgenini alır.|
|[CStatusBarCtrl::GetText](#gettext)|Metni belirtilen bir durum çubuğu denetimi kısmından alır.|
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Karakter, belirli bir durum çubuğu denetimi kısmından metnin uzunluğunu alır.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|Durum çubuğu bölmesinde araç ipucu metnini alır.|
|[CStatusBarCtrl::IsSimple](#issimple)|Bir durum pencere denetimi basit modda olup olmadığını belirlemek için denetler.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Durum çubuğunda arka plan rengini ayarlar.|
|[CStatusBarCtrl::SetIcon](#seticon)|Durum çubuğunda bir bölme simgesi ayarlar.|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|En küçük yüksekliğini bir durum denetiminin çizim alanının ayarlar.|
|[CStatusBarCtrl::SetParts](#setparts)|Durum çubuğu denetimi ve her parça öğenin sağ kenarı koordinatını bölümlerinin sayısını ayarlar.|
|[CStatusBarCtrl::SetSimple](#setsimple)|Durum çubuğu denetimi basit metin görüntüler veya önceki bir çağrı tarafından ayarlanan tüm denetim bölümlerini görüntüler belirtir `SetParts`.|
|[CStatusBarCtrl::SetText](#settext)|Metni belirtilen bir durum çubuğu denetimi kısmında ayarlar.|
|[CStatusBarCtrl::SetTipText](#settiptext)|Araç İpucu metni bölmesi için bir durum çubuğunda ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Durum çubuğu denetimi" genellikle bir uygulama çeşitli durum bilgilerini görüntüleyebilir, bir üst penceresinin en altında görüntülenen yatay bir penceredir. Durum çubuğu denetimi birden fazla tür bilgileri görüntülemek için parçalara ayrılabilir.

Bu denetimi (ve bu nedenle `CStatusBarCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CStatusBarCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="create"></a>  CStatusBarCtrl::Create

Durum çubuğu denetimi oluşturur ve ona bağlanan bir `CStatusBarCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir birleşimini uygulamak [ortak denetim stilleri](/windows/desktop/Controls/common-control-styles) Windows SDK. Bu parametre WS_CHILD stili içermelidir. Ws_vısıble stili de eklemeniz gerekir.

*Rect*<br/>
Durum çubuğu denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.

*pParentWnd*<br/>
Durum çubuğu denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Durum çubuğu denetimin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CStatusBarCtrl` iki adımda. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, durum çubuğu denetimi oluşturur ve ona ekler `CStatusBarCtrl` nesne.

Durum penceresi varsayılan konumu, pencerenin üst olmakla birlikte ana pencerenin istemci alanının üstünde görünen için CCS_TOP stili belirtebilirsiniz. Durum penceresi sonuna doğru boyutlandırma tutamacı içerecek şekilde SBARS_SIZEGRIP stili belirtebilirsiniz. Elde edilen boyutlandırma tutamacı işlevsel olmadığından, sistem durumu penceresinde çizer olsa bile CCS_TOP ve SBARS_SIZEGRIP stilleri birleştirme önerilmez.

Genişletilmiş pencere stilleri ile durum çubuğu oluşturmak için arama [CStatusBarCtrl::CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

##  <a name="createex"></a>  CStatusBarCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CStatusBarCtrl` nesne.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Durum çubuğu denetiminin stilini belirtir. Durum çubuğu denetim stilleri listelenen herhangi bir birleşimini uygulamak [ortak denetim stilleri](/windows/desktop/Controls/common-control-styles) Windows SDK. Bu parametre WS_CHILD stili içermelidir. Ws_vısıble stili de eklemeniz gerekir.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl

Oluşturur bir `CStatusBarCtrl` nesne.

```
CStatusBarCtrl();
```

##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem

Görsel bir özelliği bir özelleştirilmiş çizimli durum çubuğu denetimi değişiklikler olduğunda framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Uzun bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) gerekli çizim türü hakkında bilgi içeren yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CStatusBarCtrl` nesne.

Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* önce bu üye işlevi sonlandırır.

##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders

Durum çubuğu denetiminin geçerli genişlikleri yatay ve dikey kenarlıkların ve dikdörtgenler arasında yer alır.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Parametreler

*pBorders*<br/>
Üç öğeye sahip bir tamsayı dizisi adresi. İlk öğenin yatay kenarlığın genişliğini alır, ikincisi dikey kenarlığın genişliğini alır ve üçüncü dikdörtgenler arasındaki kenarlığın genişliğini alır.

*nHorz*<br/>
Yatay kenarlığın genişliğini alır bir tamsayı başvuru.

*Bırakırken*<br/>
Başvuru dikey kenarlığın genişliğini alır bir tamsayı.

*nSpacing*<br/>
Başvuru dikdörtgenler arasındaki kenarlığın genişliğini alır bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu Kenarlıklar denetimin dış kenarındaki ve metin içeren dikdörtgenler denetiminde aralığını belirler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon

Simge bir bölümü (bölme olarak da bilinir) için geçerli durum çubuğu denetimi alır.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iPart*|[in] Alınacak simge içeren bölümü sıfır tabanlı dizini. Bu parametreyi -1 olması durumunda, durum çubuğu basit mod durum çubuğu olduğu varsayılır.|

### <a name="return-value"></a>Dönüş Değeri

Simge tanıtıcı, başarılı; yöntemi Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [SB_GETICON](/windows/desktop/Controls/sb-geticon) Windows SDK'da açıklanan ileti.

Durum çubuğu denetimi olarak da bilinen bazı bölümleri metin çıkış bölmeleri oluşan bir satır içerir. Durum çubuğu hakkında daha fazla bilgi için bkz: [MFC'de durum çubuğu uygulaması](../../mfc/status-bar-implementation-in-mfc.md) ve [CStatusBarCtrl nesnesinin modunu ayarlama](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

### <a name="example"></a>Örnek

Aşağıdaki kod örneği bir değişkene tanımlar `m_statusBar`, geçerli durum çubuğu denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli durum çubuğu denetimi iki bölme için bir simge kopyalar. Kod örneği, bir önceki bölümdeki bir durum çubuğu denetimi ile üç bölme oluşturulur ve ardından simge ilk bölmesine eklenir. Bu örnek, ilk bölmesinden simgesini alır ve ardından ikinci ve üçüncü bölmesine ekler.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

##  <a name="getparts"></a>  CStatusBarCtrl::GetParts

Durum çubuğu denetimi bölümlerini sayısını alır.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Parametreler

*nParts*<br/>
Koordinatlarını almak istediğiniz bölümlerini sayısı. Bu parametre denetim bölümlerini sayısından büyükse, iletiyi yalnızca var olan bölümleri koordinatlarını alır.

*pParts*<br/>
Tarafından belirtilen parçaların sayısı olarak aynı sayıda öğe olan bir tamsayı dizisi adresini *nParts*. Dizideki her öğe için ilgili bölümü'nün sağ kenarı istemci koordinatını alır. -Bir öğe ayarlarsanız 1, durum çubuğunun sağ kenarı sağ kenarı için bu bölümü konumunu genişletir.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarılı olursa ya da sıfır değilse parçaların sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi ayrıca bölümleri belirli sayıda öğenin sağ kenarı koordinatını alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

##  <a name="getrect"></a>  CStatusBarCtrl::GetRect

Durum çubuğu denetimi içinde bir bölümü sınırlayıcı dikdörtgenini alır.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Alınacak olan sınırlayıcı bir dikdörtgen olduğu bölümü sıfır tabanlı dizini.

*lpRect*<br/>
Adresi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) dikdörtgen alan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

##  <a name="gettext"></a>  CStatusBarCtrl::GetText

Metni belirtilen bir durum çubuğu denetimi kısmından alır.

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
Metin alan arabellek adresi. Bu parametre null ile sonlandırılmış bir dizedir.

*nPane*<br/>
Metin alınacağı bölümü sıfır tabanlı dizini.

*pType*<br/>
Tür bilgileri alan bir tamsayı işaretçisi. Türü şu değerlerden biri olabilir:

- **0** metin durum çubuğunun düzlemi düşük görüntülenecek kenarlık ile çizilir.

- Metin SBT_NOBORDERS kenarlıktan çizilir.

- Durum çubuğunun düzlemi daha yukarıda görüntülenmesini kenarlıklı SBT_POPOUT metin çizilir.

- SBT_OWNERDRAW metin sahipse çizim türü, SBT_OWNERDRAW *pType* bu iletiyi alır ve metin yerine uzunluğu ve işlem türü ile ilişkili 32-bit değeri döndürür.

### <a name="return-value"></a>Dönüş Değeri

Metnin bir karakter uzunluğu veya [CString](../../atl-mfc-shared/reference/cstringt-class.md) geçerli metni içeren.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

##  <a name="gettextlength"></a>  CStatusBarCtrl::GetTextLength

Karakter, belirli bir durum çubuğu denetimi kısmından metnin uzunluğunu alır.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Metin alınacağı bölümü sıfır tabanlı dizini.

*pType*<br/>
Tür bilgileri alan bir tamsayı işaretçisi. Türü şu değerlerden biri olabilir:

- **0** metin durum çubuğunun düzlemi düşük görüntülenecek kenarlık ile çizilir.

- Metin SBT_NOBORDERS kenarlıktan çizilir.

- Ana pencere tarafından SBT_OWNERDRAW metin çizilir.

- Durum çubuğunun düzlemi daha yukarıda görüntülenmesini kenarlıklı SBT_POPOUT metin çizilir.

### <a name="return-value"></a>Dönüş Değeri

Karakter, metnin uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText

Durum çubuğu bölmesinde araç ipucu metnini alır.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Araç ipucu metnini almak için durum çubuğu bölmesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) ipucunda kullanılacak metni içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [SB_GETTIPTEXT](/windows/desktop/Controls/sb-gettiptext)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple

Bir durum pencere denetimi basit modda olup olmadığını belirlemek için denetler.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum pencere denetim basit modda ise sıfır olmayan; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [SB_ISSIMPLE](/windows/desktop/Controls/sb-issimple)Windows SDK içinde açıklandığı gibi.

##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor

Durum çubuğunda arka plan rengini ayarlar.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*CR*<br/>
Yeni arka plan rengini belirtir COLORREF değeri. Varsayılan arka plan rengini kullanmak için durum çubuğunu neden CLR_DEFAULT değeri belirtin.

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) önceki varsayılan arka plan rengini gösteren bir değer.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [SB_SETBKCOLOR](/windows/desktop/Controls/sb-setbkcolor)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon

Durum çubuğunda bir bölme simgesi ayarlar.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Simge alacak bölmesinde sıfır tabanlı dizini. Bu parametreyi -1 olması durumunda, durum çubuğu basit durum çubuğu olduğu varsayılır.

*hIcon*<br/>
Ayarlanacak simgeyi işleyin. Bu değer NULL ise, simge bölümünden kaldırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [SB_SETICON](/windows/desktop/Controls/sb-seticon)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

  Örneğin bakın [CStatusBarCtrl::SetBkColor](#setbkcolor).

##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight

En küçük yüksekliğini bir durum denetiminin çizim alanının ayarlar.

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Denetimin piksel cinsinden en küçük yükseklik.

### <a name="remarks"></a>Açıklamalar

Minimum yükseklik toplamıdır *nMin* ve durum çubuğu denetimi dikey kenarlığının piksel cinsinden genişliğini iki kez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

##  <a name="setparts"></a>  CStatusBarCtrl::SetParts

Durum çubuğu denetimi ve her parça öğenin sağ kenarı koordinatını bölümlerinin sayısını ayarlar.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Parametreler

*nParts*<br/>
Ayarlanacak parçaların sayısı. Parçaların sayısı 255'ten büyük olamaz.

*pWidths*<br/>
Tarafından belirtilen parçaları olarak aynı sayıda öğe olan bir tamsayı dizisi adresini *nParts*. Dizideki her öğe konumunu, istemci koordinatları, karşılık gelen bölümü'nün sağ kenarı belirtir. Bir öğe ise - 1, denetimin sağ kenarı için bu bölümü için sağ kenarı konumunu genişletir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple

Durum çubuğu denetimi basit metin görüntüler veya önceki bir çağrı tarafından ayarlanan tüm denetim bölümlerini görüntüler belirtir [SetParts](#setparts).

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSimple*<br/>
[in] Görüntü türü bayrak. Bu parametre TRUE ise, basit metin denetimi görüntüler; FALSE ise, birden fazla bölümü görüntüler.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı durum çubuğu denetimi basit olmayan öğesinden basit veya tam tersi değişirse, sistem denetimi hemen yeniden çizer.

##  <a name="settext"></a>  CStatusBarCtrl::SetText

Metni belirtilen bir durum çubuğu denetimi kısmında ayarlar.

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Belirten metin ayarlamak için null ile sonlandırılmış bir dize adresi. Varsa *nTür* SBT_OWNERDRAW, olan *lpszText* veri 32 bit temsil eder.

*nPane*<br/>
Ayarlanacak bölümü sıfır tabanlı dizini. Bu değer 255 ise, durum çubuğu denetimi yalnızca bir bölümü olan basit bir denetim olduğu varsayılır.

*nTür*<br/>
İşlemi çizme türü. Bkz: [SB_SETTEXT ileti](/windows/desktop/Controls/sb-settext) olası değerler listesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

İleti, Denetim sonraki WM_PAINT iletisini aldığında, yeni metin görüntülemek için neden değiştiğini denetim bölümünü geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

##  <a name="settiptext"></a>  CStatusBarCtrl::SetTipText

Araç İpucu metni bölmesi için bir durum çubuğunda ayarlar.

```
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parametreler

*nPane*<br/>
Araç ipucu metnini almak için durum çubuğu bölmesinin sıfır tabanlı dizini.

*pszTipText*<br/>
Araç İpucu metni içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [SB_SETTIPTEXT](/windows/desktop/Controls/sb-settiptext)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl Sınıfı](../../mfc/reference/ctoolbarctrl-class.md)
