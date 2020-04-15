---
title: CHotKeyCtrl Sınıfı
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
ms.openlocfilehash: 758fb78fbd4e25a0e2fb8cea300c5371ece04fb4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366881"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl Sınıfı

Windows ortak sıcak anahtar denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Bir `CHotKeyCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHotKeyCtrl::Oluştur](#create)|Sıcak bir anahtar denetimi oluşturur ve `CHotKeyCtrl` bir nesneye bağlar.|
|[CHotKeyCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile sıcak bir anahtar denetimi oluşturur `CHotKeyCtrl` ve bir nesneye bağlar.|
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Sıcak anahtar kontrolünden sanal anahtar kodunu ve sıcak anahtarın değiştirici bayraklarını alır.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Sıcak bir anahtara atanan yerel karakter kümesindeki anahtar adını alır.|
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Belirtilen sanal anahtar koduna atanan yerel karakter kümesinde anahtar adını alır.|
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Sıcak tuş kontrolü için sıcak tuş kombinasyonunu ayarlar.|
|[CHotKeyCtrl::SetRules](#setrules)|Geçersiz kombinasyonları ve sıcak anahtar denetimi için varsayılan değiştirici birleşimini tanımlar.|

## <a name="remarks"></a>Açıklamalar

"Sıcak anahtar denetimi", kullanıcının sıcak bir anahtar oluşturmasını sağlayan bir penceredir. "Sıcak anahtar", kullanıcının eylemi hızlı bir şekilde gerçekleştirmek için basabileceği anahtar kombinasyonudur. (Örneğin, bir kullanıcı belirli bir pencereyi etkinleştiren ve Z sırasının en üstüne getiren sıcak bir anahtar oluşturabilir.) Sıcak anahtar denetimi kullanıcının seçimlerini görüntüler ve kullanıcının geçerli bir anahtar kombinasyonu seçmesini sağlar.

Bu denetim (ve `CHotKeyCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kullanıcı bir anahtar kombinasyonu seçtiğinde, uygulama belirtilen anahtar kombinasyonunu denetimden alabilir ve sistemdeki sıcak anahtarı ayarlamak için WM_SETHOTKEY iletiyi kullanabilir. Kullanıcı daha sonra sıcak tuşa bastığında, sistemin herhangi bir bölümünden, WM_SETHOTKEY iletisinde belirtilen pencere SC_HOTKEY belirten bir WM_SYSCOMMAND iletisi alır. Bu ileti, onu alan pencereyi etkinleştirir. Sıcak anahtar, WM_SETHOTKEY olarak adlandırılan uygulama çıkana kadar geçerli kalır.

Bu mekanizma, WM_HOTKEY iletisi ve Windows [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey) ve [UnregisterHotKey](/windows/win32/api/winuser/nf-winuser-unregisterhotkey) işlevlerine bağlı sıcak anahtar desteği farklıdır.

Kullanma `CHotKeyCtrl`hakkında daha fazla bilgi [Using CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl

Bir `CHotKeyCtrl` nesne inşa eder.

```
CHotKeyCtrl();
```

## <a name="chotkeyctrlcreate"></a><a name="create"></a>CHotKeyCtrl::Oluştur

Sıcak bir anahtar denetimi oluşturur ve `CHotKeyCtrl` bir nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Sıcak anahtar denetiminin stilini belirtir. Kontrol stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için Windows SDK'daki [Ortak Denetim Stilleri'ne](/windows/win32/Controls/common-control-styles) bakın.

*Rect*<br/>
Sıcak anahtar kontrolünün boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT yapısı](/windows/win32/api/windef/ns-windef-rect)olabilir.

*pParentWnd*<br/>
Sıcak anahtar denetiminin ana penceresini, genellikle bir [CDialog'u](../../mfc/reference/cdialog-class.md)belirtir. NULL olmamalıdır.

*Nıd*<br/>
Sıcak anahtar denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız, başlatma başarılı olduysa; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CHotKeyCtrl` iki adımda inşa ee. İlk olarak, oluşturucuyu `Create`çağırın ve ardından sıcak anahtar denetimini `CHotKeyCtrl` oluşturan ve nesneye iliştiren , çağırın.

Genişletilmiş windows stillerini denetiminiz ile kullanmak istiyorsanız, `Create`'' yerine [CreateEx'i](#createex) arayın.

## <a name="chotkeyctrlcreateex"></a><a name="createex"></a>CHotKeyCtrl::CreateEx

Denetim (alt pencere) oluşturmak ve `CHotKeyCtrl` nesneyle ilişkilendirmek için bu işlevi çağırın.

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
Sıcak anahtar denetiminin stilini belirtir. Kontrol stillerinin herhangi bir birleşimini uygulayın. Daha fazla bilgi için Windows SDK'daki [Ortak Denetim Stilleri'ne](/windows/win32/Controls/common-control-styles) bakın.

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

## <a name="chotkeyctrlgethotkey"></a><a name="gethotkey"></a>CHotKeyCtrl::GetHotKey

Bir klavye kısayolu sanal anahtar kodu ve değiştirici bayraklarını sıcak tuş kontrolünden alır.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>Parametreler

*wVirtualKeyCode*<br/>
[çıkış] Klavye kısayolu sanal tuş kodu. Standart sanal anahtar kodlarının listesi için Winuser.h bölümüne bakın.

*wModifiers*<br/>
[çıkış] Klavye kısayollarında değiştirici tuşlarını gösteren bayrakların bityiş li birleşimi (VEYA).

Değiştirici bayraklar aşağıdaki gibidir:

|Bayrak|Karşılık Gelen Anahtar|
|----------|-----------------------|
|HOTKEYF_ALT|ALT tuşu|
|HOTKEYF_CONTROL|CTRL tuşu|
|HOTKEYF_EXT|Genişletilmiş anahtar|
|HOTKEYF_SHIFT|SHIFT tuşu|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklenen yöntemde, sanal anahtar kodu ve değiştirici bayrakları içeren bir DWORD. Düşük sıralı sözcüğün düşük sıralı baytsanal anahtar kodu içerir, düşük sıralı sözcüğün yüksek sıralı bayt değiştirici bayrakları içerir ve yüksek sıralı sözcük sıfırdır.

### <a name="remarks"></a>Açıklamalar

Sanal tuş kodu ve değiştirici tuşları birlikte klavye kısayolu tanımlar.

## <a name="chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName

Sıcak anahtarın yerelleştirilmiş adını almak için bu üye işlevini arayın.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçilen sıcak anahtarın yerelleştirilmiş adı. Seçili sıcak anahtar yoksa, `GetHotKeyName` boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin döndürdettiği ad klavye sürücüsünden gelir. Windows'un yerelleştirilmiş bir sürümüne yerelleştirilmiş olmayan bir klavye sürücüsü yükleyebilirsiniz ve bunun tersi de olabilir.

## <a name="chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>CHotKeyCtrl::GetKeyName

Belirtilen bir sanal anahtar koduna atanan anahtarın yerelleştirilmiş adını almak için bu üye işlevini arayın.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>Parametreler

*vk*<br/>
Sanal anahtar kodu.

*fGenişletilmiş*<br/>
Sanal anahtar kodu genişletilmiş bir anahtarsa, TRUE; aksi takdirde YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

*vk* parametresi tarafından belirtilen anahtarın yerelleştirilmiş adı. Anahtarda eşlenen ad yoksa, `GetKeyName` boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin döndürdettiği anahtar adı klavye sürücüsünden gelir, böylece Windows'un yerelleştirilmiş bir sürümüne yerelleştirilmiş olmayan bir klavye sürücüsü yükleyebilirsiniz ve bunun tersi de tam tersi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

## <a name="chotkeyctrlsethotkey"></a><a name="sethotkey"></a>CHotKeyCtrl::SetHotKey

Klavye kısayolu sıcak tuş kontrolü için ayarlar.

```
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>Parametreler

*wVirtualKeyCode*<br/>
[içinde] Klavye kısayolu sanal tuş kodu. Standart sanal anahtar kodlarının listesi için Winuser.h bölümüne bakın.

*wModifiers*<br/>
[içinde] Klavye kısayollarında değiştirici tuşlarını gösteren bayrakların bityiş li birleşimi (VEYA).

Değiştirici bayraklar aşağıdaki gibidir:

|Bayrak|Karşılık Gelen Anahtar|
|----------|-----------------------|
|HOTKEYF_ALT|ALT tuşu|
|HOTKEYF_CONTROL|CTRL tuşu|
|HOTKEYF_EXT|Genişletilmiş anahtar|
|HOTKEYF_SHIFT|SHIFT tuşu|

### <a name="remarks"></a>Açıklamalar

Sanal tuş kodu ve değiştirici tuşları birlikte klavye kısayolu tanımlar.

## <a name="chotkeyctrlsetrules"></a><a name="setrules"></a>CHotKeyCtrl::SetRules

Geçersiz kombinasyonları ve sıcak anahtar denetimi için varsayılan değiştirici birleşimini tanımlamak için bu işlevi arayın.

```
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>Parametreler

*wInvalidComb*<br/>
Geçersiz anahtar birleşimlerini belirten bayraklar dizisi. Aşağıdaki değerlerin bir birleşimi olabilir:

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL+ALT

- HKCOMB_NONE Değiştirilmemiş tuşları

- HKCOMB_S SHIFT

- HKCOMB_SA SHIFT+ALT

- HKCOMB_SC SHIFT+CTRL

- HKCOMB_SCA SHIFT+CTRL+ALT

*wModifiers*<br/>
Kullanıcı geçersiz bir kombinasyon girdiğinde kullanılacak anahtar birleşimini belirten bayraklar dizisi. Değiştirici bayraklar hakkında daha fazla bilgi için [GetHotKey'e](#gethotkey)bakın.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı geçersiz bir anahtar kombinasyonu girdiğinde, *wInvalidComb*belirtilen bayraklar tarafından tanımlanan , sistem *wModifiers*belirtilen bayraklar ile kullanıcı tarafından girilen anahtarları birleştirmek için OR işleci kullanır. Elde edilen anahtar birleşimi bir dize dönüştürülür ve daha sonra sıcak anahtar denetiminde görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
