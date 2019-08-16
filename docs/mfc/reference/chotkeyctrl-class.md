---
title: CHotKeyCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: 9818c32a7779d646ca5a9485a1331dfa393408ba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506157"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl sınıfı

Windows Common Hot Key Control işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHotKeyCtrl:: CHotKeyCtrl](#chotkeyctrl)|Bir `CHotKeyCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHotKeyCtrl:: Create](#create)|Etkin anahtar denetimi oluşturur ve bunu bir `CHotKeyCtrl` nesneye ekler.|
|[CHotKeyCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir etkin anahtar denetimi oluşturur ve bunu bir `CHotKeyCtrl` nesneye ekler.|
|[CHotKeyCtrl:: GetHotKey](#gethotkey)|Etkin anahtar denetiminden etkin bir anahtarın sanal anahtar kodunu ve değiştirici bayraklarını alır.|
|[CHotKeyCtrl:: GetHotKeyName](#gethotkeyname)|Etkin bir anahtara atanan, yerel karakter kümesindeki anahtar adını alır.|
|[CHotKeyCtrl:: GetKeyName](#getkeyname)|Belirtilen sanal anahtar koduna atanan, yerel karakter kümesindeki anahtar adını alır.|
|[CHotKeyCtrl:: SetHotKey](#sethotkey)|Etkin anahtar denetimi için kısayol tuşu birleşimini ayarlar.|
|[CHotKeyCtrl:: SetRules](#setrules)|Etkin anahtar denetimi için geçersiz birleşimleri ve varsayılan değiştirici bileşimini tanımlar.|

## <a name="remarks"></a>Açıklamalar

"Kısayol tuşu denetimi", kullanıcının kısayol tuşu oluşturmasını sağlayan bir penceredir. "Kısayol tuşu", kullanıcının bir eylemi hızlı bir şekilde gerçekleştirmek için bastabileceği bir anahtar birleşimidir. (Örneğin, bir Kullanıcı belirli bir pencereyi etkinleştiren ve Z sırasının en üstüne getiren bir kısayol tuşu oluşturabilir.) Sık kullanılan anahtar denetimi kullanıcının seçimlerini gösterir ve kullanıcının geçerli bir anahtar birleşimi seçmesi sağlar.

Bu denetim (ve bu nedenle `CHotKeyCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kullanıcı bir anahtar birleşimi seçtiğinde, uygulama denetimden belirtilen anahtar birleşimini alabilir ve WM_SETHOTKEY iletisini kullanarak sistemde etkin anahtarı ayarlayabilir. Bundan sonra kullanıcının kısayol tuşuna basması durumunda, WM_SETHOTKEY iletisinde belirtilen pencere SC_HOTKEY belirten bir WM_SYSCOMMAND iletisi alır. Bu ileti, onu alan pencereyi etkinleştirir. Etkin anahtar, WM_SETHOTKEY adlı uygulama çıkıncaya kadar geçerli kalır.

Bu mekanizma, WM_HOTKEY iletisine ve Windows [registerkısayol](/windows/win32/api/winuser/nf-winuser-registerhotkey) 'A ve [unregisterkısayol](/windows/win32/api/winuser/nf-winuser-unregisterhotkey) işlevlerine bağlı olan sık kullanılan anahtar desteğinden farklıdır.

Kullanma `CHotKeyCtrl`hakkında daha fazla bilgi için bkz [](../../mfc/controls-mfc.md) . [CHotKeyCtrl kullanma](../../mfc/using-chotkeyctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="chotkeyctrl"></a>CHotKeyCtrl:: CHotKeyCtrl

Bir `CHotKeyCtrl` nesnesi oluşturur.

```
CHotKeyCtrl();
```

##  <a name="create"></a>CHotKeyCtrl:: Create

Etkin anahtar denetimi oluşturur ve bunu bir `CHotKeyCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Kısayol tuşu denetiminin stilini belirtir. Denetim stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için bkz. Windows SDK [ortak denetim stilleri](/windows/win32/Controls/common-control-styles) .

*Rect*<br/>
Etkin anahtar denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect yapısı](/windows/win32/api/windef/ns-windef-rect)olabilir.

*pParentWnd*<br/>
Sık kullanılan anahtar denetiminin üst penceresini belirtir, genellikle bir [CDialog](../../mfc/reference/cdialog-class.md). NULL olmaması gerekir.

*NID*<br/>
Etkin anahtar denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CHotKeyCtrl` nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve ardından, `Create`etkin anahtar denetimini oluşturan ve bunu `CHotKeyCtrl` nesnesine ekleyen çağırın.

Denetimi ile genişletilmiş Windows stilleri kullanmak istiyorsanız, yerine `Create` [CreateEx](#createex) çağırın.

##  <a name="createex"></a>CHotKeyCtrl:: CreateEx

Bir denetim (alt pencere) oluşturmak ve `CHotKeyCtrl` nesneyle ilişkilendirmek için bu işlevi çağırın.

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
Kısayol tuşu denetiminin stilini belirtir. Denetim stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için, bkz. Windows SDK [ortak denetim stilleri](/windows/win32/Controls/common-control-styles) .

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

##  <a name="gethotkey"></a>CHotKeyCtrl:: GetHotKey

Etkin anahtar denetiminden klavye kısayolunun sanal anahtar kodunu ve değiştirici bayraklarını alır.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>Parametreler

*wVirtualKeyCode*<br/>
dışı Klavye kısayolunun sanal anahtar kodu. Standart sanal anahtar kodlarının listesi için bkz. Winuser. h.

*Wdeğiştiriciler*<br/>
dışı Klavye Kısayolunda değiştirici tuşlarını gösteren bir bit düzeyinde birleşim (veya) bayrakları.

Değiştirici bayrakları aşağıdaki gibidir:

|Bayrağı|Karşılık gelen anahtar|
|----------|-----------------------|
|HOTKEYF_ALT|ALT tuşu|
|HOTKEYF_CONTROL|CTRL tuşu|
|HOTKEYF_EXT|Genişletilmiş anahtar|
|HOTKEYF_SHIFT|SHIFT tuşu|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklenmiş yöntemde, sanal anahtar kodu ve değiştirici bayraklarını içeren bir DWORD. Düşük sıralı sözcüğün düşük sıra baytı sanal anahtar kodunu içerir, düşük sıralı sözcüğün üst sıra baytı değiştirici bayraklarını içerir ve yüksek sıralı sözcük sıfırdır.

### <a name="remarks"></a>Açıklamalar

Sanal anahtar kodu ve değiştirici Anahtarlar birlikte klavye kısayolunu tanımlar.

##  <a name="gethotkeyname"></a>CHotKeyCtrl:: GetHotKeyName

Sık kullanılan anahtarın yerelleştirilmiş adını almak için bu üye işlevi çağırın.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan etkin anahtarın yerelleştirilmiş adı. Seçili kısayol tuşu yoksa, `GetHotKeyName` boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin döndürdüğü ad klavye sürücüsünden geliyor. Yerelleştirilmiş olmayan bir klavye sürücüsünü Windows 'un yerelleştirilmiş bir sürümüne yükleyebilirsiniz ve tam tersi de geçerlidir.

##  <a name="getkeyname"></a>CHotKeyCtrl:: GetKeyName

Belirtilen sanal anahtar koduna atanan anahtarın yerelleştirilmiş adını almak için bu üye işlevi çağırın.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>Parametreler

*VK*<br/>
Sanal anahtar kodu.

*fExtended*<br/>
Sanal anahtar kodu bir genişletilmiş anahtardır, TRUE; Aksi halde yanlış.

### <a name="return-value"></a>Dönüş Değeri

*VK* parametresi tarafından belirtilen anahtarın yerelleştirilmiş adı. Anahtar eşlenmiş bir ada sahip değilse, `GetKeyName` boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin döndürdüğü anahtar adı klavye sürücüsünden geliyorsa, yerelleştirilmiş olmayan bir klavye sürücüsünü Windows 'un yerelleştirilmiş bir sürümüne yükleyebilirsiniz ve bunun tersini yapabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

##  <a name="sethotkey"></a>CHotKeyCtrl:: SetHotKey

Kısayol tuşu denetimi için klavye kısayolunu ayarlar.

```
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>Parametreler

*wVirtualKeyCode*<br/>
'ndaki Klavye kısayolunun sanal anahtar kodu. Standart sanal anahtar kodlarının listesi için bkz. Winuser. h.

*Wdeğiştiriciler*<br/>
'ndaki Klavye Kısayolunda değiştirici tuşlarını gösteren bir bit düzeyinde birleşim (veya) bayrakları.

Değiştirici bayrakları aşağıdaki gibidir:

|Bayrağı|Karşılık gelen anahtar|
|----------|-----------------------|
|HOTKEYF_ALT|ALT tuşu|
|HOTKEYF_CONTROL|CTRL tuşu|
|HOTKEYF_EXT|Genişletilmiş anahtar|
|HOTKEYF_SHIFT|SHIFT tuşu|

### <a name="remarks"></a>Açıklamalar

Sanal anahtar kodu ve değiştirici Anahtarlar birlikte klavye kısayolunu tanımlar.

##  <a name="setrules"></a>CHotKeyCtrl:: SetRules

Etkin anahtar denetimi için geçersiz birleşimleri ve varsayılan değiştirici bileşimini tanımlamak için bu işlevi çağırın.

```
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>Parametreler

*wInvalidComb*<br/>
Geçersiz anahtar birleşimlerini belirten bayrakların dizisi. Aşağıdaki değerlerin bir birleşimi olabilir:

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL + ALT

- HKCOMB_NONE değiştirilmemiş anahtarlar

- HKCOMB_S KAYDIRMA

- HKCOMB_SA SHIFT + ALT

- HKCOMB_SC SHIFT + CTRL

- HKCOMB_SCA SHIFT+CTRL+ALT

*Wdeğiştiriciler*<br/>
Kullanıcı geçersiz bir bileşim girdiğinde kullanılacak anahtar birleşimini belirten bayrakların dizisi. Değiştirici bayrakları hakkında daha fazla bilgi için bkz. [GetHotKey](#gethotkey).

### <a name="remarks"></a>Açıklamalar

Kullanıcı, *Winvalidcomb*'de belirtilen bayraklar tarafından tanımlandığı şekilde geçersiz bir anahtar birleşimi girdiğinde, sistem kullanıcı tarafından girilen anahtarları *wModifiers*'da belirtilen bayraklarla birleştirmek için veya işlecini kullanır. Elde edilen anahtar birleşimi bir dizeye dönüştürülür ve ardından sık kullanılan anahtar denetiminde görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
