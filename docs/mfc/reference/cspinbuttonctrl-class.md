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
ms.openlocfilehash: 3c973d92550469804a5389b84f53005e4f2c154f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290436"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl sınıfı

Windows ortak değer değiştirme düğmesi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Oluşturur bir `CSpinButtonCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSpinButtonCtrl::Create](#create)|Değer değiştirme düğmesi denetimi oluşturur ve ona bağlanan bir `CSpinButtonCtrl` nesne.|
|[CSpinButtonCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir değer değiştirme düğmesi denetimi oluşturur ve ona ekler bir `CSpinButtonCtrl` nesne.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|Değer değiştirme düğmesi denetimi için hızlandırma bilgilerini alır.|
|[CSpinButtonCtrl::GetBase](#getbase)|Değer değiştirme düğmesi denetimi için geçerli temel alır.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Geçerli buddy penceresindeki bir işaretçi alır.|
|[CSpinButtonCtrl::GetPos](#getpos)|Değer değiştirme düğmesi denetimi geçerli konumunu alır.|
|[CSpinButtonCtrl::GetRange](#getrange)|Üst ve alt sınırları (aralık) için bir değer değiştirme düğmesi denetimi alır.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|Hızlandırma değer değiştirme düğmesi denetimi için ayarlar.|
|[CSpinButtonCtrl::SetBase](#setbase)|Temel bir değer değiştirme düğmesi denetimi için ayarlar.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Buddy penceresindeki Değer değiştirme düğmesi denetimi için ayarlar.|
|[CSpinButtonCtrl::SetPos](#setpos)|Geçerli konum denetimi için ayarlar.|
|[CSpinButtonCtrl::SetRange](#setrange)|Üst ve alt sınırları (aralık) bir değer değiştirme düğmesi denetimi için ayarlar.|

## <a name="remarks"></a>Açıklamalar

"(Bir yukarı-aşağı denetimi olarak da bilinir) bir değer değiştirme düğmesi denetimi" artırın veya kaydırma konumunu veya bir özel denetimde görüntülenen bir sayı gibi bir değeri Azalt kullanıcının tıklayabileceği ok düğmelerini çifti var. Değer değiştirme düğmesi denetimi ile ilişkilendirilen değeri, geçerli konumuna çağrılır. Değer değiştirme düğmesi denetimi genellikle bir "buddy penceresindeki." adlı bir yardımcı denetimiyle kullanılır

Bu denetimi (ve bu nedenle `CSpinButtonCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Kullanıcı için bir değer değiştirme düğmesi denetimi ve buddy penceresinin genellikle tek bir denetim gibi arayın. Değer değiştirme düğmesi denetimi otomatik olarak kendini kendi buddy penceresindeki yanındaki getirin, ve geçerli konumuna buddy penceresinin başlığını otomatik olarak ayarlayın, belirtebilirsiniz. Sayısal girişi için kullanıcıdan bir düzenleme denetimi ile bir değer değiştirme düğmesi denetimi kullanabilirsiniz.

Yukarı oka tıklayarak en doğru geçerli konumu, ve aşağı oka tıklayarak geçerli konumu en doğru taşır. Varsayılan olarak, en az 100'dür ve en fazla 0'dır. En düşük ayarı (örneğin, varsayılan ayarlar kullanıldığında) ayarlama, Yukarı Ok düşüşleri tıklayarak üst sınırdan büyük olduğundan dilediğiniz zaman konum değerini ve aşağı oka tıklayarak artar ve bu.

Değer değiştirme düğmesi denetimi buddy penceresindeki olmadan Basitleştirilmiş kaydırma çubuğu bir tür işlev görür. Örneğin, bir sekme denetimi, kullanıcının ek sekmeleri görünüme gidin etkinleştirmek için bir değer değiştirme düğmesi denetimi görüntüler.

Kullanma hakkında daha fazla bilgi için `CSpinButtonCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [CSpinButtonCtrl kullanma](../../mfc/using-cspinbuttonctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="create"></a>  CSpinButtonCtrl::Create

Değer değiştirme düğmesi denetimi oluşturur ve ona bağlanan bir `CSpinButtonCtrl` nesne...

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Döndürme düğme denetiminin stilini belirtir. Değer değiştirme düğmesi denetimi stilleri herhangi bir birleşimini denetimi için geçerlidir. Bu stiller açıklanan [yukarı-aşağı denetim stilleri](/windows/desktop/Controls/up-down-control-styles) Windows SDK.

*Rect*<br/>
Döndürme düğme denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı

*pParentWnd*<br/>
Değer değiştirme düğmesi denetiminin üst penceresine, genellikle bir işaretçi bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Değer değiştirme düğmesi denetimi'nın kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CSpinButtonCtrl` ilk iki adımını nesne, oluşturucusunu çağırın ve ardından arama `Create`, değer değiştirme düğmesi denetimi oluşturur ve ona ekler `CSpinButtonCtrl` nesne.

Genişletilmiş pencere stilleri ile değer değiştirme düğmesi denetimi oluşturmak için arama [CSpinButtonCtrl::CreateEx](#createex) yerine `Create`.

##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CSpinButtonCtrl` nesne.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Döndürme düğme denetiminin stilini belirtir. Değer değiştirme düğmesi denetimi stilleri herhangi bir birleşimini denetimi için geçerlidir. Bu stiller açıklanan [yukarı-aşağı denetim stilleri](/windows/desktop/Controls/up-down-control-styles) Windows SDK.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz WS_EX_ tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için.

##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl

Oluşturur bir `CSpinButtonCtrl` nesne.

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel

Değer değiştirme düğmesi denetimi için hızlandırma bilgilerini alır.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
Tarafından belirtilen dizideki öğelerin sayısını *pAccel*.

*pAccel*<br/>
Bir dizi işaretçi [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) yapıları hızlandırma bilgilerini alır.

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı yapıların sayısı aldı.

##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase

Değer değiştirme düğmesi denetimi için geçerli temel alır.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli taban değeri.

##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy

Geçerli buddy penceresindeki bir işaretçi alır.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli buddy penceresindeki bir işaretçi.

##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos

Değer değiştirme düğmesi denetimi geçerli konumunu alır.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpbError*<br/>
Başarıyla alındığında sıfır olmayan bir hata oluşursa bir işaretçiye sıfır için değer olarak ayarlanırsa bir Boole değeri. Bu parametre NULL olarak ayarlanırsa, hataları raporlanmaz.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm düşük düzey word 16-bit gereçli konumu döndürür. Yüksek düzeyli bir hata oluşursa sıfır olmayan bir sözcüktür.

Dosyanın ikinci sürümü, 32-bit konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer işlediğinde, denetime buddy penceresinin açıklamalı alt yazı göre geçerli konumunu güncelleştirir. Denetimin hiç buddy penceresindeki ise veya geçersiz veya aralık dışı bir değer resim yazısını belirtir bir hata döndürür.

##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange

Üst ve alt sınırları (aralık) için bir değer değiştirme düğmesi denetimi alır.

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

*Daha düşük*<br/>
Denetimi alt sınırını alır bir tamsayı başvuru.

*üst*<br/>
Denetimi üst sınırını alır bir tamsayı başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm üst ve alt sınırları içeren 32-bit bir değer döndürür. Düşük düzeyli denetimin üst sınırını olup ve dwpoint alt sınır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `GetRange32` değer değiştirme düğmesi denetimi'nın aralığı bir 32 bit tamsayı olarak alır.

##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel

Hızlandırma değer değiştirme düğmesi denetimi için ayarlar.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*nAccel*<br/>
Sayısı [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) yapıları tarafından belirtilen *pAccel*.

*pAccel*<br/>
Bir dizi hızlandırma bilgiler içeren UDACCEL yapıları işaretçi. Öğeleri göre artan sırada sıralanması `nSec` üyesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase

Temel bir değer değiştirme düğmesi denetimi için ayarlar.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parametreler

*nBase*<br/>
Denetim için yeni taban değeri. Ondalık 10 veya 16 onaltılık için olabilir.

### <a name="return-value"></a>Dönüş Değeri

Önceki taban değeri başarılı olursa, ya da geçersiz bir taban belirtilmezse sıfır.

### <a name="remarks"></a>Açıklamalar

Temel değerin buddy penceresindeki sayılar ondalık veya onaltılı basamak görüntülenip görüntülenmeyeceğini belirler. Onaltılık sayılar daima işaretsizdir; ondalık sayılar imzalanmıştır.

##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy

Buddy penceresindeki Değer değiştirme düğmesi denetimi için ayarlar.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parametreler

*pWndBuddy*<br/>
Yeni buddy penceresindeki işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Önceki buddy penceresindeki bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürme denetimi neredeyse her zaman bazı içerik görüntüleyen bir düzenleme denetimi gibi başka bir pencere ile ilişkilidir. Bu, başka bir pencere döndürme denetimi "dost" adı verilir.

##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos

Geçerli konum bir değer değiştirme düğmesi denetimi için ayarlar.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Yeni denetimin konumu. Bu değer, denetimin üst ve alt sınırları tarafından belirtilen aralıkta olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Önceki konumu (16-bit duyarlığını `SetPos`, 32-bit duyarlık için `SetPos32`).

### <a name="remarks"></a>Açıklamalar

`SetPos32` 32-bit konumunu ayarlar.

##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange

Üst ve alt sınırları (aralık) bir değer değiştirme düğmesi denetimi için ayarlar.

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
Denetimi üst ve alt sınırları. İçin `SetRange`, hiçbir sınır UD_MAXVAL büyük olabilir veya iki sınırları arasındaki farkı UD_MAXVAL daha azını UD_MINVAL; Ayrıca, aşamaz. `SetRange32` herhangi bir kısıtlama barındırabileceğiniz yerleştirir; herhangi bir tamsayı kullanın.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `SetRange32` 32-bit aralığı değer değiştirme düğmesi denetimi için ayarlar.

> [!NOTE]
>  Değer değiştirme düğmesi için varsayılan aralığı sıfır (0) olarak ayarlayın en fazla ve en az 100'e ayarlayın sahiptir. Maksimum değer minimum değerden daha az olduğundan, konumu yukarı oka tıklayarak azaltır ve aşağı oka tıklayarak da artacaktır. Kullanım `CSpinButtonCtrl::SetRange` bu değerleri ayarlamak için.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl Sınıfı](../../mfc/reference/csliderctrl-class.md)
