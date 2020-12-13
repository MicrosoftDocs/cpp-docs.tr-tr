---
description: 'Daha fazla bilgi edinin: Cnetaddressc$sınıfı'
title: Cnetaddressc$sınıfı
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: 66f2bb647d02b262f9264d5a99f84a3fb23fc119
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331510"
---
# <a name="cnetaddressctrl-class"></a>Cnetaddressc$sınıfı

`CNetAddressCtrl`Sınıfı, IPv4, IPv6 ve adlandırılmış DNS adreslerinin biçimini girmek ve doğrulamak için kullanabileceğiniz ağ adresi denetimini temsil eder.

## <a name="syntax"></a>Syntax

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cnetaddressc$:: cnetaddressc$](#cnetaddressctrl)|Bir `CNetAddressCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cnetaddressc$:: Create](#create)|Belirtilen stillerle bir ağ adresi denetimi oluşturur ve geçerli `CNetAddressCtrl` nesneye ekler.|
|[Cnetaddressc$:: CreateEx](#createex)|Belirtilen genişletilmiş stillerle bir ağ adresi denetimi oluşturur ve geçerli `CNetAddressCtrl` nesneye ekler.|
|[Cnetaddressccu::D Isplayerrortıp](#displayerrortip)|Kullanıcı geçerli ağ adresi denetimine desteklenmeyen bir ağ adresi girdiğinde bir hata balonu ipucu görüntüler.|
|[Cnetaddressc$:: GetAddress](#getaddress)|Geçerli ağ adresi denetimiyle ilişkili ağ adresinin doğrulanan ve ayrıştırılmış temsilini alır.|
|[Cnetaddresscu:: GetAllowType](#getallowtype)|Geçerli ağ adresi denetiminin destekleyebileceği ağ adresi türünü alır.|
|[Cnetaddresscu:: SetAllowType](#setallowtype)|Geçerli ağ adresi denetiminin destekleyebileceği ağ adresi türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Ağ adresi denetimi, kullanıcının girdiği adresin biçiminin doğru olduğunu doğrular. Denetim aslında ağ adresine bağlanmamıştır. [Cnetaddresscfy:: SetAllowType](#setallowtype) yöntemi, [Cnetaddresscfy:: GetAddress](#getaddress) yönteminin ayrıştırılabilir ve doğrulayabileceği bir veya daha fazla adres türünü belirtir. Bir adres, bir sunucu, ağ, ana bilgisayar veya yayın iletisi hedefi için bir IPv4, IPv6 veya adlandırılmış adres biçiminde olabilir. Adresin biçimi yanlış ise, ağ adresi denetiminin metin kutusuna grafiksel olarak işaret eden bir InfoTip ileti kutusu göstermek için [Cnetaddresscu::D Isplayerrortıp](#displayerrortip) yöntemini kullanabilirsiniz ve önceden tanımlanmış bir hata iletisi görüntüler.

`CNetAddressCtrl`Sınıfı, [cedıt](../../mfc/reference/cedit-class.md) sınıfından türetilir. Sonuç olarak, ağ adresi denetimi tüm Windows düzenleme denetim iletilerine erişim sağlar.

Aşağıdaki şekilde, bir ağ adresi denetimi içeren bir iletişim kutusu gösterilmektedir. Ağ adresi denetimi için (1) metin kutusu geçersiz bir ağ adresi içeriyor. Bilgi ipucu iletisi (2), ağ adresi geçersizse görüntülenir.

![Ağ adresi denetimi ve bilgi ipucu ile iletişim kutusu.](../../mfc/reference/media/cnetaddctrl.png "Ağ adresi denetimi ve bilgi ipucu ile iletişim kutusu.")

## <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bir ağ adresini doğrulayan bir iletişim kutusunun bölümüdür. Üç radyo düğmesi için olay işleyicileri, ağ adresinin üç adres türünden biri olabilir. Kullanıcı ağ denetiminin metin kutusuna bir adres girer ve sonra adresi doğrulamak için bir düğmeye basar. Adres geçerliyse, bir başarı iletisi görüntülenir; Aksi takdirde, önceden tanımlanmış Bilgi İpucu hata iletisi görüntülenir.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

İletişim kutusu üstbilgi dosyasındaki aşağıdaki kod örneği, [Cnetaddressc$:: GetAddress](#getaddress) yöntemi için gereken [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) ve [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) değişkenlerini tanımlar.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

Bu sınıf Windows Vista ve sonraki sürümlerde desteklenir.

Bu sınıf için ek gereksinimler, [Windows Vista ortak denetimleri Için derleme gereksinimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md)bölümünde açıklanmaktadır.

## <a name="cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a> Cnetaddressc$:: cnetaddressc$

Bir `CNetAddressCtrl` nesnesi oluşturur.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Bir ağ denetimi oluşturmak ve nesneye iliştirmek için [cnetaddressc$:: Create](#create) veya [Cnetaddressc$:: CreateEx](#createex) metodunu kullanın `CNetAddressCtrl` .

## <a name="cnetaddressctrlcreate"></a><a name="create"></a> Cnetaddressc$:: Create

Belirtilen stillerle bir ağ adresi denetimi oluşturur ve geçerli `CNetAddressCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*\
'ndaki Denetime uygulanacak stillerin bit düzeyinde birleşimi. Daha fazla bilgi için bkz. [stilleri düzenleme](../../mfc/reference/styles-used-by-mfc.md#edit-styles).

*Rect*\
'ndaki Denetimin konumunu ve boyutunu içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*\
'ndaki Denetimin üst penceresi olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.

*NID*\
'ndaki Denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="cnetaddressctrlcreateex"></a><a name="createex"></a> Cnetaddressc$:: CreateEx

Belirtilen genişletilmiş stillerle bir ağ adresi denetimi oluşturur ve geçerli `CNetAddressCtrl` nesneye ekler.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*\
'ndaki Denetime uygulanacak genişletilmiş stillerin bit tabanlı birleşimi (veya). Daha fazla bilgi için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Işlevinin *dwExStyle* parametresi.

*dwStyle*\
'ndaki Denetime uygulanacak stillerin bit tabanlı birleşimi (veya). Daha fazla bilgi için bkz. [stilleri düzenleme](../../mfc/reference/styles-used-by-mfc.md#edit-styles).

*Rect*\
'ndaki Denetimin konumunu ve boyutunu içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*\
'ndaki Denetimin üst penceresi olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.

*NID*\
'ndaki Denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a> Cnetaddressccu::D Isplayerrortıp

Geçerli ağ adresi denetimiyle ilişkili balon ipucunda bir hata mesajı görüntüler.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Dönüş Değeri

`S_OK`Bu yöntem başarılı olursa değeri, aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Geçerli ağ adresi denetiminin destekleyebileceği adres türlerini belirtmek için [Cnetaddressc$:: SetAllowType](#setallowtype) metodunu kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrıştırmak için [Cnetaddressc$:: GetAddress](#getaddress) metodunu kullanın. [Cnetaddressccu:: GetAddress](#getaddress) yöntemi başarısız olursa, bir hata iletisi bilgi ipucu göstermek Için [cnetaddressccu::D isplayerrortıp](#displayerrortip) metodunu kullanın.

Bu ileti, Windows SDK açıklanan [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) makrosunu çağırır. Bu makro iletiyi gönderir `NCM_DISPLAYERRORTIP` .

## <a name="cnetaddressctrlgetaddress"></a><a name="getaddress"></a> Cnetaddressc$:: GetAddress

Geçerli ağ adresi denetimiyle ilişkili ağ adresinin doğrulanan ve ayrıştırılmış temsilini alır.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Parametreler

*pAddress*<br/>
[in, out] [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) yapısına yönelik işaretçi.  GetAddress yöntemini çağırmadan önce bu yapının *pAddrInfo* üyesini bir [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) yapısının adresine ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa değer S_OK; Aksi halde bir COM hata kodu. Olası hata kodları hakkında daha fazla bilgi için [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) makrosunun dönüş değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) yapısı ağ adresiyle ilgili ek bilgiler içerir.

Geçerli ağ adresi denetiminin destekleyebileceği adres türlerini belirtmek için [Cnetaddressc$:: SetAllowType](#setallowtype) yöntemini kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrıştırmak için [Cnetaddressc$:: GetAddress](#getaddress) metodunu kullanın. [Cnetaddressccu:: GetAddress](#getaddress) yöntemi başarısız olursa, bir hata iletisi bilgi ipucu göstermek Için [cnetaddressccu::D isplayerrortıp](#displayerrortip) metodunu kullanın.

Bu yöntem, Windows SDK açıklanan [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) makrosunu çağırır. Bu makro NCM_GETADDRESS iletisini gönderir.

## <a name="cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a> Cnetaddresscu:: GetAllowType

Geçerli ağ adresi denetiminin destekleyebileceği ağ adresi türünü alır.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ağ adresi denetiminin destekleyebileceği adres türlerini belirten bayrakların bit düzeyinde birleşimi (veya). Daha fazla bilgi için bkz. [NET_STRING](/windows/win32/shell/net-string).

### <a name="remarks"></a>Açıklamalar

Bu ileti, Windows SDK açıklanan [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) makrosunu çağırır. Bu makro NCM_GETALLOWTYPE iletisini gönderir.

## <a name="cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a> Cnetaddresscu:: SetAllowType

Geçerli ağ adresi denetiminin destekleyebileceği ağ adresi türünü ayarlar.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Parametreler

*dwAddrMask*\
'ndaki Ağ adresi denetiminin destekleyebileceği adres türlerini belirten bayrakların bit düzeyinde birleşimi (veya). Daha fazla bilgi için bkz. [NET_STRING](/windows/win32/shell/net-string).

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa S_OK; Aksi halde bir COM hata kodu.

### <a name="remarks"></a>Açıklamalar

Geçerli ağ adresi denetiminin destekleyebileceği adres türlerini belirtmek için [Cnetaddressc$:: SetAllowType](#setallowtype) metodunu kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrıştırmak için [Cnetaddressc$:: GetAddress](#getaddress) metodunu kullanın. [Cnetaddressccu:: GetAddress](#getaddress) yöntemi başarısız olursa, bir hata iletisi bilgi ipucu göstermek Için [cnetaddressccu::D isplayerrortıp](#displayerrortip) metodunu kullanın.

Bu ileti, Windows SDK açıklanan [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) makrosunu çağırır. Bu makro NCM_SETALLOWTYPE iletisini gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[Cnetaddressc$sınıfı](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)
