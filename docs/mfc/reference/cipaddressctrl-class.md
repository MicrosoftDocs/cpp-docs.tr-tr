---
title: CIPAddressCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: 28aa0e7137647bc49406dab1e82b9c2b05ca3538
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372350"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl Sınıfı

Windows ortak IP Adresi denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Bir `CIPAddressCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP Adresi Denetimi'nin içeriğini temizler.|
|[CIPAddressCtrl::Oluştur](#create)|IP Adresi Denetimi oluşturur ve bir `CIPAddressCtrl` nesneye bağlar.|
|[CIPAddressCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir IP Adresi denetimi oluşturur `CIPAddressCtrl` ve bir nesneye bağlar.|
|[CIPAddressCtrl::GetAddress](#getaddress)|IP Adresi Denetimi'ndeki dört alanın adres değerlerini alır.|
|[CIPAddressCtrl::Boş](#isblank)|IP Adres Denetimi'ndeki tüm alanların boş olup olmadığını belirler.|
|[CIPAddressCtrl::SetAddress](#setaddress)|IP Adresi Denetimi'ndeki dört alanın adres değerlerini ayarlar.|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Klavye odağıIP Adres Denetimi'nde belirtilen alana ayarlar.|
|[CIPAddressCtrl::SetFieldAralığı](#setfieldrange)|IP Adresi Denetimi'nde belirtilen alandaki aralığı ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir düzenleme denetimine benzer bir denetim olan IP Adresi denetimi, Internet Protokolü (IP) biçiminde sayısal bir adres girmenize ve işlemenize olanak tanır.

Bu denetim (ve `CIPAddressCtrl` bu nedenle sınıf) yalnızca Microsoft Internet Explorer 4.0 ve sonraki programlar altında çalışan programlar için kullanılabilir. Ayrıca Windows ve Windows NT gelecekteki sürümleri altında satışa sunulacak.

IP Adres Denetimi hakkında daha genel bilgi için Windows SDK'daki [IP Adres Denetimleri'ne](/windows/win32/Controls/ip-address-controls) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl

Bir `CIPAddressCtrl` nesnesi oluşturur.

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a>CIPAddressCtrl::ClearAddress

IP Adresi Denetimi'nin içeriğini temizler.

```
void ClearAddress();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress)davranışını uygular.

## <a name="cipaddressctrlcreate"></a><a name="create"></a>CIPAddressCtrl::Oluştur

IP Adresi Denetimi oluşturur ve bir `CIPAddressCtrl` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
IP Adresi denetiminin stili. Pencere stillerinin bir birleşimini uygulayın. Denetim bir alt pencere olması gerektiğinden, WS_CHILD stilieklemeniz gerekir. Windows stilleri listesi için Windows SDK'daki [CreateWindow'a](/windows/win32/api/winuser/nf-winuser-createwindoww) bakın.

*Rect*<br/>
IP Adresi Denetimi'nin boyutuna ve konumuna bir başvuru. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
IP Adresi Denetimi'nin üst penceresine işaretçi. NULL olmamalıdır.

*Nıd*<br/>
IP Adresi Denetimi'nin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CIPAddressCtrl` iki adımda inşa ee.

1. Nesneyi oluşturan oluşturucuyu `CIPAddressCtrl` çağırın.

1. ARAMA `Create`, IP Adres Denetimi oluşturur.

Genişletilmiş windows stillerini denetiminiz ile kullanmak istiyorsanız, `Create`'' yerine [CreateEx'i](#createex) arayın.

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a>CIPAddressCtrl::CreateEx

Denetim (alt pencere) oluşturmak ve `CIPAddressCtrl` nesneyle ilişkilendirmek için bu işlevi çağırın.

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
IP Adresi denetiminin stili. Pencere stillerinin bir birleşimini uygulayın. Denetim bir alt pencere olması gerektiğinden, WS_CHILD stilieklemeniz gerekir. Windows stilleri listesi için Windows SDK'daki [CreateWindow'a](/windows/win32/api/winuser/nf-winuser-createwindoww) bakın.

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

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a>CIPAddressCtrl::GetAddress

IP Adresi Denetimi'ndeki dört alanın adres değerlerini alır.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>Parametreler

*nField0*<br/>
Paketlenmiş bir IP adresinden alan 0 değerine başvuru.

*nField1*<br/>
Paketlenmiş bir IP adresinden alan 1 değerine bir başvuru.

*nField2*<br/>
Paketlenmiş bir IP adresinden alan 2 değerine bir başvuru.

*nField3*<br/>
Paketlenmiş bir IP adresinden alan 3 değerine bir başvuru.

*dwAddress*<br/>
IP adresini alan bir DWORD değerinin adresine yapılan başvuru. *dwAddress'in* nasıl doldurulduğunu gösteren bir tabloiçin **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

IP Adresi Denetimi'ndeki boş olmayan alanların sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress)davranışını uygular. Yukarıdaki ilk prototipte, kontrolden 0'dan 3'e kadar olan alanlardaki sayılar sırasıyla soldan sağa okunur ve dört parametreyi doldurun. Yukarıdaki ikinci *prototipte, dwAddress* aşağıdaki gibi doldurulur.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|0|24 ile 31 arası|
|1|16 ile 23 arası|
|2|8 ile 15 arasında|
|3|0 ile 7 arasında|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a>CIPAddressCtrl::Boş

IP Adres Denetimi'ndeki tüm alanların boş olup olmadığını belirler.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm IP Adresi Denetimi alanları boşsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ipm-isblank)iletisinin IPM_ISBLANK davranışını uygular.

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a>CIPAddressCtrl::SetAddress

IP Adresi Denetimi'ndeki dört alanın adres değerlerini ayarlar.

```
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>Parametreler

*nField0*<br/>
Paketlenmiş bir IP adresinden alan 0 değeri.

*nField1*<br/>
Paketlenmiş bir IP adresinden alan 1 değeri.

*nField2*<br/>
Paketlenmiş bir IP adresinden alan 2 değeri.

*nField3*<br/>
Paketlenmiş bir IP adresinden alan 3 değeri.

*dwAddress*<br/>
Yeni IP adresini içeren bir DWORD değeri. DWORD değerinin nasıl doldurulduğunu gösteren bir tabloiçin **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)davranışını uygular. Yukarıdaki ilk prototipte, kontrolden 0'dan 3'e kadar olan alanlardaki sayılar sırasıyla soldan sağa okunur ve dört parametreyi doldurun. Yukarıdaki ikinci *prototipte, dwAddress* aşağıdaki gibi doldurulur.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|0|24 ile 31 arası|
|1|16 ile 23 arası|
|2|8 ile 15 arasında|
|3|0 ile 7 arasında|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus

Klavye odağıIP Adres Denetimi'nde belirtilen alana ayarlar.

```
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Parametreler

*nAlan*<br/>
Odak ayarlanmalıdır sıfır tabanlı alan dizini. Bu değer alan sayısından büyükse, odak ilk boş alana ayarlanır. Tüm alanlar boş değilse, odak ilk alana ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ipm-setfocus)iletisinin IPM_SETFOCUS davranışını uygular.

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>CIPAddressCtrl::SetFieldAralığı

IP Adresi Denetimi'nde belirtilen alandaki aralığı ayarlar.

```
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Parametreler

*nAlan*<br/>
Aralığın uygulanacağı sıfır tabanlı alan dizini.

*nLower*<br/>
Bu IP Adresi Denetimi'nde belirtilen alanın alt sınırını alan bir tamsayıya başvuru.

*nUpper*<br/>
Bu IP Adresi Denetimi'nde belirtilen alanın üst sınırını alan bir tamsayıya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [IPM_SETRANGE](/windows/win32/Controls/ipm-setrange)davranışını uygular. Win32 iletisi ile kullanılan *wRange* parametresi yerine alanın alt ve üst sınırlarını belirtmek için *nLower* ve *nUpper*olmak üzere iki parametreyi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
