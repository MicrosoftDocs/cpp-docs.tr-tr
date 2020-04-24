---
title: CSpinButtonCtrl Sınıfı
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
ms.openlocfilehash: cedfe16a6870bc779121e8e864866cfcb711b148
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753115"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl Sınıfı

Windows ortak spin düğmesi denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Bir `CSpinButtonCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl::Oluştur](#create)|Döndürme düğmesi denetimi oluşturur ve nesneye `CSpinButtonCtrl` bağlar.|
|[CSpinButtonCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir spin düğmesi denetimi oluşturur `CSpinButtonCtrl` ve bir nesneye bağlar.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|Döndürme düğmesi kontrolü için hızlanma bilgilerini alır.|
|[CSpinButtonCtrl::GetBase](#getbase)|Döndürme düğmesi denetimi için geçerli tabanı alır.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Geçerli arkadaş penceresiiçin bir işaretçi alır.|
|[CSpinButtonCtrl::GetPos](#getpos)|Döndürme düğmesi denetiminin geçerli konumunu alır.|
|[CSpinButtonCtrl::GetRange](#getrange)|Döndürme düğmesi kontrolü için üst ve alt sınırları (aralık) alır.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|Döndürme düğmesi kontrolü için ivmeyi ayarlar.|
|[CSpinButtonCtrl::SetBase](#setbase)|Döndürme düğmesi kontrolü için tabanı ayarlar.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Döndürme düğmesi kontrolü için arkadaş penceresini ayarlar.|
|[CSpinButtonCtrl::SetPos](#setpos)|Denetim için geçerli konumu ayarlar.|
|[CSpinButtonCtrl::SetAralığı](#setrange)|Spin düğmesi kontrolü için üst ve alt sınırları (aralık) ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Döndürme düğmesi denetimi" (yukarı-aşağı denetim olarak da bilinir), kullanıcının kaydırma konumu veya bir eş arkadaşı denetiminde görüntülenen bir sayı gibi bir değeri artım veya düşürmek için tıklatabileceği bir çift ok düğmesidir. Spin düğmesi denetimiyle ilişkili değer, geçerli konumu olarak adlandırılır. Döndürme düğmesi denetimi en sık "arkadaş penceresi" adı verilen bir eş arkadaşı denetimiyle kullanılır.

Bu denetim (ve `CSpinButtonCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kullanıcı için, bir spin düğmesi denetimi ve onun dostum penceresi genellikle tek bir kontrol gibi görünür. Döndürme düğmesi denetiminin kendisini otomatik olarak arkadaş penceresinin yanına konumlandırdığını ve arkadaş penceresinin alt yazısını otomatik olarak geçerli konumuna ayarladığını belirtebilirsiniz. Sayısal giriş için kullanıcıyı harekete geçirebilmek için bir döndürme denetimi ile döndürme düğmesi denetimi kullanabilirsiniz.

Yukarı ok tıklatıldığında geçerli konumu maksimuma doğru hareket ettirir ve aşağı ok tıklatıldığında geçerli konumu minimuma doğru hareket ettirir. Varsayılan olarak, en az 100 ve en büyük 0'dır. Minimum ayar maksimum ayardan büyük olduğunda (örneğin, varsayılan ayarlar kullanıldığında), yukarı ok tıklatıldığında konum değeri azalır ve aşağı ok ayarı artar.

Bir dostum penceresi olmayan bir döndürme düğmesi denetimi, basitleştirilmiş kaydırma çubuğu gibi işlev görür. Örneğin, sekme denetimi bazen kullanıcının ek sekmeleri görünüme kaydırmasını sağlamak için bir döndürme düğmesi denetimi görüntüler.

Kullanma `CSpinButtonCtrl`hakkında daha fazla bilgi [Using CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::Oluştur

Döndürme düğmesi denetimi oluşturur ve nesneye `CSpinButtonCtrl` bağlar...

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Döndürme düğmesi denetiminin stilini belirtir. Döndürme düğmesi kontrol stillerinin herhangi bir birleşimini kontrole uygulayın. Bu stiller, Windows SDK'daki [Yukarı-Aşağı Denetim Stilleri'nde](/windows/win32/Controls/up-down-control-styles) açıklanmıştır.

*Rect*<br/>
Spin düğmesi denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir

*pParentWnd*<br/>
Döndürme düğmesi denetiminin ana penceresine işaretçi, genellikle bir `CDialog`. NULL olmamalıdır.

*Nıd*<br/>
Döndürme düğmesi denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CSpinButtonCtrl` önce iki adımda oluşturursunuz, oluşturucuyu ararsınız ve sonra `Create`spin düğmesi `CSpinButtonCtrl` denetimini oluşturur ve nesneye bağlar.

Genişletilmiş pencere stilleriile bir spin düğmesi denetimi oluşturmak için [CSpinButtonCtrl::CreateEx](#createex) yerine `Create`.

## <a name="cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CSpinButtonCtrl` nesneyle ilişkilendirir.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş windows stilleri listesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Döndürme düğmesi denetiminin stilini belirtir. Döndürme düğmesi kontrol stillerinin herhangi bir birleşimini kontrole uygulayın. Bu stiller, Windows SDK'daki [Yukarı-Aşağı Denetim Stilleri'nde](/windows/win32/Controls/up-down-control-styles) açıklanmıştır.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz WS_EX_ tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

## <a name="cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl

Bir `CSpinButtonCtrl` nesne inşa eder.

```
CSpinButtonCtrl();
```

## <a name="cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel

Döndürme düğmesi kontrolü için hızlanma bilgilerini alır.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
*pAccel*tarafından belirtilen dizideki öğe sayısı.

*pAccel*<br/>
Hızlanma bilgileri alan bir dizi [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) yapısını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Alınan hızlandırıcı yapı sayısı.

## <a name="cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase

Döndürme düğmesi denetimi için geçerli tabanı alır.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli temel değer.

## <a name="cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy

Geçerli arkadaş penceresiiçin bir işaretçi alır.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli arkadaş penceresiiçin bir işaretçi.

## <a name="cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos

Döndürme düğmesi denetiminin geçerli konumunu alır.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpbHata*<br/>
Değer başarıyla alınırsa veya bir hata oluşursa sıfır olmayan bir boolean değerine işaretçi. Bu parametre NULL olarak ayarlanırsa, hatalar bildirilmemiştir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, düşük sıralı sözcükteki 16 bit geçerli konumu döndürür. Bir hata oluştuysa, yüksek sıralı sözcük sıfır değildir.

İkinci sürüm 32 bit konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen değeri işlediğinde, denetim, dostum penceresinin alt yazısına bağlı olarak geçerli konumunu güncelleştirir. Denetim, arkadaş penceresi yoksa veya resim yazısı geçersiz veya aralık dışı bir değer belirtiyorsa bir hata döndürür.

## <a name="cspinbuttonctrlgetrange"></a><a name="getrange"></a>CSpinButtonCtrl::GetRange

Döndürme düğmesi kontrolü için üst ve alt sınırları (aralık) alır.

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

*Alt*<br/>
Denetim için alt sınırı alan bir aramaya başvuru.

*Üst*<br/>
Denetim için üst sınırı alan bir aramaya başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, üst ve alt sınırları içeren 32 bitlik bir değer döndürür. Alt sıra sözcüğü denetim için üst sınırdır ve üst düzey sözcük alt sınırdır.

### <a name="remarks"></a>Açıklamalar

Üye işlev, `GetRange32` spin düğmesi denetiminin aralığını 32 bit tamsayı olarak alır.

## <a name="cspinbuttonctrlsetaccel"></a><a name="setaccel"></a>CSpinButtonCtrl::SetAccel

Döndürme düğmesi kontrolü için ivmeyi ayarlar.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
*pAccel*tarafından belirtilen [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) yapı sayısı.

*pAccel*<br/>
Hızlanma bilgileri içeren bir dizi UDACCEL yapısına işaretçi. Öğeler `nSec` üyeye göre artan sırada sıralanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="cspinbuttonctrlsetbase"></a><a name="setbase"></a>CSpinButtonCtrl::SetBase

Döndürme düğmesi kontrolü için tabanı ayarlar.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parametreler

*nBase*<br/>
Denetim için yeni temel değer. Ondalık veya 16 ondalık için 10 olabilir hexadecimal için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı ysa önceki temel değer veya geçersiz bir taban verilirse sıfır.

### <a name="remarks"></a>Açıklamalar

Temel değer, dostum penceresinin sayıları ondalık veya hexadecimal basamakta gösterip görüntülemediğini belirler. Hexadecimal sayılar her zaman imzasızdır; ondalık sayılar imzalanır.

## <a name="cspinbuttonctrlsetbuddy"></a><a name="setbuddy"></a>CSpinButtonCtrl::SetBuddy

Döndürme düğmesi kontrolü için arkadaş penceresini ayarlar.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parametreler

*pWndBuddy*<br/>
Yeni arkadaş penceresine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Önceki arkadaş penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürme denetimi, hemen hemen her zaman bazı içerikleri görüntüleyen bir edit denetimi gibi başka bir pencereyle ilişkilendirilir. Bu diğer pencerespin denetiminin "dostum" olarak adlandırılır.

## <a name="cspinbuttonctrlsetpos"></a><a name="setpos"></a>CSpinButtonCtrl::SetPos

Döndürme düğmesi denetimi için geçerli konumu ayarlar.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kontrol için yeni bir pozisyon. Bu değer, denetim için üst ve alt sınırlar tarafından belirtilen aralıkta olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Önceki konum (16 bit `SetPos`hassasiyet için, 32-bit hassasiyet için). `SetPos32`

### <a name="remarks"></a>Açıklamalar

`SetPos32`32 bit konumu ayarlar.

## <a name="cspinbuttonctrlsetrange"></a><a name="setrange"></a>CSpinButtonCtrl::SetAralığı

Spin düğmesi kontrolü için üst ve alt sınırları (aralık) ayarlar.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parametreler

*nLower* ve *nUpper*<br/>
Denetim için üst ve alt sınırlar. Çünkü, `SetRange`ne sınır UD_MAXVAL'dan büyük veya UD_MINVAL daha az olabilir; ayrıca, iki sınır arasındaki fark UD_MAXVAL geçemez. `SetRange32`sınırlarüzerinde herhangi bir kısıtlama koyar; herhangi bir sonda kullanın.

### <a name="remarks"></a>Açıklamalar

Üye işlev, `SetRange32` spin düğmesi kontrolü için 32 bit aralığını ayarlar.

> [!NOTE]
> Döndürme düğmesi için varsayılan aralık, en fazla sıfır (0) ve en az 100 olarak ayarlanmıştır. En büyük değer minimum değerden daha az olduğundan, yukarı ok tıklatıldığında konumu azaltır ve aşağı ok atamama artar. Bu `CSpinButtonCtrl::SetRange` değerleri ayarlamak için kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl Sınıfı](../../mfc/reference/csliderctrl-class.md)
