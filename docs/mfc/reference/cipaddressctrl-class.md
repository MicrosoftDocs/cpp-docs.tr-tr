---
description: 'Şu konuda daha fazla bilgi edinin: Şifreddresscskclass'
title: Şifreddressc, sınıfı
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
ms.openlocfilehash: e5791726bc31e9b7485d0de7ecfc5461408ed02a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340950"
---
# <a name="cipaddressctrl-class"></a>Şifreddressc, sınıfı

Windows ortak IP adresi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Şifreddressci:: Şifreadresisci](#cipaddressctrl)|Bir `CIPAddressCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Şifreddressci:: ClearAddress](#clearaddress)|IP adresi denetiminin içeriğini temizler.|
|[Şifreddressci:: Create](#create)|Bir IP adresi denetimi oluşturur ve bunu bir nesneye ekler `CIPAddressCtrl` .|
|[Şifreddressci:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir IP adresi denetimi oluşturur ve bunu bir `CIPAddressCtrl` nesneye ekler.|
|[Şifreddressci:: GetAddress](#getaddress)|IP adresi denetimindeki tüm dört alan için adres değerlerini alır.|
|[Şifreleri:: ISBLANK](#isblank)|IP adresi denetimindeki tüm alanların boş olup olmadığını belirler.|
|[Şifreddressci:: SetAddress](#setaddress)|IP adresi denetimindeki tüm dört alan için adres değerlerini ayarlar.|
|[Şifreoddresscn:: SetFieldFocus](#setfieldfocus)|Klavye odağını IP adresi denetimindeki belirtilen alana ayarlar.|
|[Şifreddressch:: SetFieldRange](#setfieldrange)|IP adresi denetimindeki belirtilen alanın aralığını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir düzenleme denetimine benzer bir denetim olan bir IP adresi denetimi, Internet Protokolü (IP) biçiminde bir sayısal adres girmenize ve değiştirmenize olanak sağlar.

Bu denetim (ve bu nedenle `CIPAddressCtrl` sınıfı) yalnızca Microsoft Internet Explorer 4,0 ve üzeri sürümlerde çalışan programlar için kullanılabilir. Bunlar, Windows ve Windows NT 'nin sonraki sürümlerinde de kullanılabilir.

IP adresi denetimi hakkında daha fazla genel bilgi için, Windows SDK [IP adresi denetimleri](/windows/win32/Controls/ip-address-controls) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a> Şifreddressci:: Şifreadresisci

Bir `CIPAddressCtrl` nesnesi oluşturur.

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a> Şifreddressci:: ClearAddress

IP adresi denetiminin içeriğini temizler.

```cpp
void ClearAddress();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress)davranışını uygular.

## <a name="cipaddressctrlcreate"></a><a name="create"></a> Şifreddressci:: Create

Bir IP adresi denetimi oluşturur ve bunu bir nesneye ekler `CIPAddressCtrl` .

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
IP adresi denetiminin stili. Pencere stillerinin birleşimini uygulayın. Denetimin bir alt pencere olması gerektiğinden WS_CHILD stilini dahil etmeniz gerekir. Windows stillerinin listesi için Windows SDK [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) ' a bakın.

*Rect*<br/>
IP adresi denetiminin boyut ve konumuna bir başvuru. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
IP adresi denetiminin üst penceresine yönelik bir işaretçi. NULL olmaması gerekir.

*NID*<br/>
IP adresi denetiminin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CIPAddressCtrl`İki adımda bir nesne oluşturursunuz.

1. Nesnesini oluşturan oluşturucuyu çağırın `CIPAddressCtrl` .

1. `Create`IP adresi denetimini oluşturan çağrısı.

Denetimi ile genişletilmiş Windows stilleri kullanmak istiyorsanız, yerine [CreateEx](#createex) çağırın `Create` .

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a> Şifreddressci:: CreateEx

Bir denetim (alt pencere) oluşturmak ve nesneyle ilişkilendirmek için bu işlevi çağırın `CIPAddressCtrl` .

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
IP adresi denetiminin stili. Pencere stillerinin birleşimini uygulayın. Denetimin bir alt pencere olması gerektiğinden WS_CHILD stilini dahil etmeniz gerekir. Windows stillerinin listesi için Windows SDK [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) ' a bakın.

*Rect*<br/>
*PParentWnd* istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a> Şifreddressci:: GetAddress

IP adresi denetimindeki tüm dört alan için adres değerlerini alır.

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
Paketlenmiş bir IP adresinden alan 1 değerine başvuru.

*nField2*<br/>
Paketlenmiş bir IP adresinden alan 2 değerine başvuru.

*nField3*<br/>
Paketlenmiş bir IP adresinden alan 3 değerine başvuru.

*dwAddress*<br/>
IP adresini alan bir DWORD değeri adresine başvuru. *DwAddress* 'in nasıl doldurulacağını gösteren bir tablo için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

IP adresi denetimindeki boş olmayan alan sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress)davranışını uygular. Yukarıdaki ilk prototipte, denetimin 0 ile 3 arasındaki alanlarındaki sayılar, soldan sağa doğru okundu ve dört parametreyi dolduracaktır. Yukarıdaki ikinci prototipde *dwAddress* aşağıdaki gibi doldurulur.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|0|24 ila 31|
|1|16 ila 23|
|2|8 ila 15|
|3|0 ila 7|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a> Şifreleri:: ISBLANK

IP adresi denetimindeki tüm alanların boş olup olmadığını belirler.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm IP adresi denetim alanları boşsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_ISBLANK](/windows/win32/Controls/ipm-isblank)davranışını uygular.

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a> Şifreddressci:: SetAddress

IP adresi denetimindeki tüm dört alan için adres değerlerini ayarlar.

```cpp
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
Yeni IP adresini içeren bir DWORD değeri. DWORD değerinin nasıl doldurulacağını gösteren bir tablo için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)davranışını uygular. Yukarıdaki ilk prototipte, denetimin 0 ile 3 arasındaki alanlarındaki sayılar, soldan sağa doğru okundu ve dört parametreyi dolduracaktır. Yukarıdaki ikinci prototipde *dwAddress* aşağıdaki gibi doldurulur.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|0|24 ila 31|
|1|16 ila 23|
|2|8 ila 15|
|3|0 ila 7|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a> Şifreoddresscn:: SetFieldFocus

Klavye odağını IP adresi denetimindeki belirtilen alana ayarlar.

```cpp
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Parametreler

*Nalan*<br/>
Odağın ayarlanması gereken sıfır tabanlı alan dizini. Bu değer, alan sayısından büyükse, odak ilk boş alana ayarlanır. Tüm alanlar boş değilse, odak ilk alana ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus)davranışını uygular.

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a> Şifreddressch:: SetFieldRange

IP adresi denetimindeki belirtilen alanın aralığını ayarlar.

```cpp
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Parametreler

*Nalan*<br/>
Aralığın uygulanacağı sıfır tabanlı alan dizini.

*nLower*<br/>
Bu IP adresi denetimindeki belirtilen alanın alt sınırını alan bir tamsayıya yönelik başvuru.

*nUpper*<br/>
Bu IP adresi denetimindeki belirtilen alanın üst sınırını alan bir tamsayıya yönelik başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [IPM_SETRANGE](/windows/win32/Controls/ipm-setrange)davranışını uygular. Win32 iletisiyle kullanılan *wRange* parametresi yerine, alanın alt ve üst sınırlarını belirtmek Için *nLower* ve *nUpper* parametrelerini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
