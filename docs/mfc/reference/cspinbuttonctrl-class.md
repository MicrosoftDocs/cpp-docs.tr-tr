---
title: CSpinButtonCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: c167745eed45b7081e62a2c3be225a33e7ee0520
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502436"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl sınıfı

Windows ortak döndürme düğmesi denetiminin işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl:: CSpinButtonCtrl](#cspinbuttonctrl)|Bir `CSpinButtonCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl:: Create](#create)|Bir döndürme düğmesi denetimi oluşturur ve bunu bir `CSpinButtonCtrl` nesneye ekler.|
|[CSpinButtonCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir döndürme düğmesi denetimi oluşturur ve bunu bir `CSpinButtonCtrl` nesneye ekler.|
|[CSpinButtonCtrl:: GetAccel](#getaccel)|Bir döndürme düğmesi denetimi için hızlandırma bilgilerini alır.|
|[CSpinButtonCtrl:: GetBase](#getbase)|Bir döndürme düğmesi denetimi için geçerli temeli alır.|
|[CSpinButtonCtrl:: Getarkadaş](#getbuddy)|Geçerli arkadaş penceresine bir işaretçi alır.|
|[CSpinButtonCtrl:: GetPos](#getpos)|Bir döndürme düğmesi denetiminin geçerli konumunu alır.|
|[CSpinButtonCtrl:: GetRange](#getrange)|Bir döndürme düğmesi denetimi için üst ve alt sınırları (Aralık) alır.|
|[CSpinButtonCtrl:: SetAccel](#setaccel)|Bir döndürme düğmesi denetimi için hızlandırma belirler.|
|[CSpinButtonCtrl:: SetBase](#setbase)|Bir döndürme düğmesi denetiminin temelini ayarlar.|
|[CSpinButtonCtrl:: Setarkadaş](#setbuddy)|Bir döndürme düğmesi denetimi için arkadaş penceresini ayarlar.|
|[CSpinButtonCtrl:: SetPos](#setpos)|Denetimin geçerli konumunu ayarlar.|
|[CSpinButtonCtrl:: SetRange](#setrange)|Bir döndürme düğmesi denetimi için üst ve alt sınırları (Aralık) ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir "döndürme düğmesi denetimi" (yukarı-aşağı denetimi olarak da bilinir), kullanıcının bir değeri artırmak veya azaltmak için, bir kaydırma konumu ya da bir yardımcı denetimde görüntülenen bir sayı gibi bir ok düğmesi çiftidir. Bir döndürme düğmesi denetimiyle ilişkili değer, geçerli konumu olarak adlandırılır. Bir döndürme düğmesi denetimi, genellikle "arkadaş penceresi" olarak adlandırılan bir yardımcı denetimle kullanılır.

Bu denetim (ve bu nedenle `CSpinButtonCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kullanıcıya, bir döndürme düğmesi denetimi ve arkadaş penceresi genellikle tek bir denetim gibi görünür. Bir döndürme düğmesi denetiminin otomatik olarak kendi arkadaş penceresinin yanına konumlandırmayacağını ve arkadaş penceresinin başlığını otomatik olarak geçerli konumuna ayarlayabileceğinizi belirtebilirsiniz. Kullanıcıdan sayısal giriş istemek için bir düzenleme denetimiyle bir döndürme düğmesi denetimi kullanabilirsiniz.

Yukarı oka tıklamak geçerli konumu en büyük değere doğru hareket ettirir ve aşağı oka tıklamak geçerli konumu en düşük değere doğru hareket ettirir. Varsayılan olarak, en az 100, üst sınır 0 ' dır. En düşük ayar en yüksek ayarından daha büyük olduğunda (örneğin, varsayılan ayarlar kullanıldığında), yukarı okuna tıklamak konum değerini düşürür ve aşağı oka tıklanması onu arttırır.

Arkadaş penceresi olmayan bir döndürme düğmesi denetimi, Basitleştirilmiş kaydırma çubuğu sıralaması olarak çalışır. Örneğin, bir sekme denetimi bazen kullanıcının ek sekmeleri görünüme kaydırabilmesini sağlamak için bir döndürme düğmesi denetimi görüntüler.

Kullanma `CSpinButtonCtrl`hakkında daha fazla bilgi için bkz. [CSpinButtonCtrl using](../../mfc/using-cspinbuttonctrl.md) [denetimleri](../../mfc/controls-mfc.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="create"></a>CSpinButtonCtrl:: Create

Bir döndürme düğmesi denetimi oluşturur ve bunu bir `CSpinButtonCtrl` nesneye ekler...

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Döndürme düğmesi denetiminin stilini belirtir. Denetime herhangi bir döndürme düğmesi denetim stillerinin birleşimini uygulayın. Bu stiller Windows SDK [Yukarı açılan denetim stillerinde](/windows/win32/Controls/up-down-control-styles) açıklanmıştır.

*Rect*<br/>
Döndürme düğmesi denetiminin boyutunu ve konumunu belirtir. Bu bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir

*pParentWnd*<br/>
Döndürme düğmesi denetiminin üst penceresine (genellikle a `CDialog`) yönelik bir işaretçi. NULL olmaması gerekir.

*NID*<br/>
Döndürme düğmesi denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Önce iki adımda `CSpinButtonCtrl` bir nesne oluşturun, oluşturucuyu çağırın ve sonra döndürme düğmesi denetimini oluşturan `CSpinButtonCtrl` ve `Create`bunu nesnesine ekleyen çağırın.

Genişletilmiş pencere stilleriyle bir döndürme düğmesi denetimi oluşturmak için yerine `Create` [CSpinButtonCtrl:: CreateEx](#createex) çağırın.

##  <a name="createex"></a>CSpinButtonCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CSpinButtonCtrl` nesneyle ilişkilendirir.

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
Döndürme düğmesi denetiminin stilini belirtir. Denetime herhangi bir döndürme düğmesi denetim stillerinin birleşimini uygulayın. Bu stiller Windows SDK [Yukarı açılan denetim stillerinde](/windows/win32/Controls/up-down-control-styles) açıklanmıştır.

*Rect*<br/>
*PParentWnd*istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stili önsöz ws_ex_ tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl:: CSpinButtonCtrl

Bir `CSpinButtonCtrl` nesnesi oluşturur.

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>CSpinButtonCtrl:: GetAccel

Bir döndürme düğmesi denetimi için hızlandırma bilgilerini alır.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
Dizide *pAccel*tarafından belirtilen öğe sayısı.

*pAccel*<br/>
Hızlandırma bilgilerini alan bir [Uıdaccel](/windows/win32/api/commctrl/ns-commctrl-udaccel) yapıları dizisine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Alınan Hızlandırıcı yapılarının sayısı.

##  <a name="getbase"></a>CSpinButtonCtrl:: GetBase

Bir döndürme düğmesi denetimi için geçerli temeli alır.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli temel değer.

##  <a name="getbuddy"></a>CSpinButtonCtrl:: Getarkadaş

Geçerli arkadaş penceresine bir işaretçi alır.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli arkadaş penceresine yönelik bir işaretçi.

##  <a name="getpos"></a>CSpinButtonCtrl:: GetPos

Bir döndürme düğmesi denetiminin geçerli konumunu alır.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpbError*<br/>
Bir hata oluşursa, değer başarıyla alınırsa sıfır veya sıfır olmayan bir Boole değeri işaretçisi. Bu parametre NULL olarak ayarlandıysa hatalar raporlanır.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, düşük sıralı sözcükteki 16 bit geçerli konumu döndürür. Bir hata oluştuysa yüksek sıralı sözcük sıfır dışı olur.

İkinci sürüm 32 bitlik konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen değeri işlediğinde denetim, arkadaş penceresinin açıklamalı alt yazısına göre geçerli konumunu günceller. Bir arkadaş penceresi yoksa veya başlık geçersiz veya Aralık dışı bir değer belirtiyorsa denetim bir hata döndürür.

##  <a name="getrange"></a>CSpinButtonCtrl:: GetRange

Bir döndürme düğmesi denetimi için üst ve alt sınırları (Aralık) alır.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>Parametreler

*düşürül*<br/>
Denetim için alt sınırı alan bir tamsayıya başvuru.

*üst*<br/>
Denetim için üst sınırı alan bir tamsayıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, üst ve alt limitlerin bulunduğu 32 bitlik bir değer döndürür. Düşük sıralı sözcük, denetim için üst sınırdır ve yüksek sıralı sözcük alt sınırdır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `GetRange32` , döndürme düğmesi denetiminin aralığını 32 bitlik bir tamsayı olarak alır.

##  <a name="setaccel"></a>CSpinButtonCtrl:: SetAccel

Bir döndürme düğmesi denetimi için hızlandırma belirler.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
*PAccel*tarafından belirtilen [uıdaccel](/windows/win32/api/commctrl/ns-commctrl-udaccel) yapılarının sayısı.

*pAccel*<br/>
Hızlandırma bilgilerini içeren bir UıDACCEL yapıları dizisine yönelik işaretçi. Öğeler, `nSec` üyeye göre artan sırada sıralanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

##  <a name="setbase"></a>CSpinButtonCtrl:: SetBase

Bir döndürme düğmesi denetiminin temelini ayarlar.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parametreler

*nBase*<br/>
Denetim için yeni temel değer. Onaltılık için 10 veya ondalık için 16 olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa önceki temel değer ya da geçersiz bir taban verilirse sıfır.

### <a name="remarks"></a>Açıklamalar

Temel değer, arkadaş penceresinin sayıları ondalık ya da onaltılık rakamlarla görüntüleyip görüntülemediğini belirler. Onaltılık sayılar her zaman işaretsiz; ondalık sayılar imzalanır.

##  <a name="setbuddy"></a>CSpinButtonCtrl:: Setarkadaş

Bir döndürme düğmesi denetimi için arkadaş penceresini ayarlar.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parametreler

*Pwndarkadaş*<br/>
Yeni arkadaş penceresine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Önceki arkadaş penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir döndürme denetimi, bazı içerikleri görüntüleyen bir düzenleme denetimi gibi başka bir pencere ile neredeyse her zaman ilişkilendirilir. Bu diğer pencereye, döndürme denetiminin "arkadaş" adı verilir.

##  <a name="setpos"></a>CSpinButtonCtrl:: SetPos

Bir döndürme düğmesi denetimi için geçerli konumu ayarlar.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Denetim için yeni konum. Bu değer, denetimin üst ve alt limitleriyle belirtilen aralıkta olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Önceki konum (için 16 bit duyarlık `SetPos`, 32 bit `SetPos32`duyarlık için).

### <a name="remarks"></a>Açıklamalar

`SetPos32`32 bit konumunu ayarlar.

##  <a name="setrange"></a>CSpinButtonCtrl:: SetRange

Bir döndürme düğmesi denetimi için üst ve alt sınırları (Aralık) ayarlar.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower* ve *nUpper*<br/>
Denetimin üst ve alt sınırları. İçin `SetRange`, hiçbir limit UD_MAXVAL değerinden büyük veya UD_MINVAL değerinden küçük olabilir; Ayrıca, iki sınır arasındaki fark UD_MAXVAL değerini aşamaz. `SetRange32`sınırlara kısıtlama vermez; herhangi bir tamsayı kullanın.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `SetRange32` , döndürme düğmesi denetimi için 32 bitlik aralığı ayarlar.

> [!NOTE]
>  Döndürme düğmesinin varsayılan aralığı, en yüksek değeri sıfır (0) ve en az 100 olarak ayarlanır. En büyük değer en küçük değerden daha düşük olduğundan, yukarı oka tıklamak konumu düşürür ve aşağı oka tıklanması bunu artıracaktır. Bu `CSpinButtonCtrl::SetRange` değerleri ayarlamak için kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl Sınıfı](../../mfc/reference/csliderctrl-class.md)
