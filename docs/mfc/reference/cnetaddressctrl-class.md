---
title: CNetAddressCtrl Sınıfı
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
ms.openlocfilehash: c6f391966ef6657363e8f23e5666a57a935b08e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752780"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl Sınıfı

Sınıf, `CNetAddressCtrl` IPv4, IPv6 ve adlandırılmış DNS adreslerinin biçimini giriş ve doğrulama için kullanabileceğiniz ağ adresi denetimini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Bir `CNetAddressCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CNetAddressCtrl::Oluştur](#create)|Belirtilen stilleri içeren bir ağ adresi denetimi oluşturur `CNetAddressCtrl` ve geçerli nesneye bağlar.|
|[CNetAddressCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stilleri içeren bir ağ adresi denetimi oluşturur `CNetAddressCtrl` ve geçerli nesneye bağlar.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Kullanıcı geçerli ağ adresi denetimine desteklenmeyen bir ağ adresi girdiğinde bir hata balon ucu görüntüler.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Geçerli ağ adresi denetimiyle ilişkili ağ adresinin doğrulanmış ve ayrışmış bir temsilini alır.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Geçerli ağ adresi denetiminin destekedebileceği ağ adresi türünü alır.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Geçerli ağ adresi denetiminin destekedebileceği ağ adresi türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Ağ adresi denetimi, kullanıcının girdiği adresbiçiminin doğru olduğunu doğrular. Denetim aslında ağ adresine bağlanmaz. [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemi, [CNetAddressCtrl::GetAddress](#getaddress) yönteminin ayrıştının ve doğrulayabildiği bir veya daha fazla adres türünü belirtir. Adres, bir sunucu, ağ, ana bilgisayar veya yayın iletisi hedefi için IPv4, IPv6 veya adlandırılmış adres şeklinde olabilir. Adresbiçimi yanlışsa, ağ adresi denetiminin metin kutusuna grafik olarak işaret eden ve önceden tanımlanmış bir hata iletisi görüntüleyen bir bilgi ipucu iletisi kutusunu görüntülemek için [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemini kullanabilirsiniz.

Sınıf `CNetAddressCtrl` [CEdit](../../mfc/reference/cedit-class.md) sınıfından türetilmiştir. Sonuç olarak, ağ adresi denetimi tüm Windows denetim iletilerine erişim sağlar.

Aşağıdaki şekilde ağ adresi denetimi içeren bir iletişim kutusu gösterilmiştir. Ağ adresi denetimi için metin kutusu (1) geçersiz bir ağ adresi içerir. Ağ adresi geçersizse bilgi ipucu iletisi (2) görüntülenir.

![Ağ adresi denetimi ve bilgi ipucu içeren iletişim bilgileri.](../../mfc/reference/media/cnetaddctrl.png "Ağ adresi denetimi ve bilgi ipucu içeren iletişim bilgileri.")

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, ağ adresini doğrulayan bir iletişim kutusunun bir bölümüdür. Üç radyo düğmesi için olay işleyicileri, ağ adresinin üç adres türünden biri olabileceğini belirtir. Kullanıcı ağ denetiminin metin kutusuna bir adres girer ve adresi doğrulamak için bir düğmeye basar. Adres geçerliyse, bir başarı iletisi görüntülenir; aksi takdirde, önceden tanımlanmış bilgi ipucu hata iletisi görüntülenir.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Örnek

İletişim üstbilgi dosyasından aşağıdaki kod [örneği, CNetAddressCtrl::GetAddress](#getaddress) yönteminin gerektirdiği [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) ve [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) değişkenleri tanımlar.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cedit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

Bu sınıf Windows Vista ve daha sonra desteklenir.

Bu sınıf için ek gereksinimler [Windows Vista Ortak Denetimleri için Yapı Gereksinimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md)açıklanmıştır.

## <a name="cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl

Bir `CNetAddressCtrl` nesne inşa eder.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Bir ağ denetimi oluşturmak ve nesneye takmak için [CNetAddressCtrl::Create](#create) veya [CNetAddressCtrl::CreateEx](#createex) yöntemini `CNetAddressCtrl` kullanın.

## <a name="cnetaddressctrlcreate"></a><a name="create"></a>CNetAddressCtrl::Oluştur

Belirtilen stilleri içeren bir ağ adresi denetimi oluşturur `CNetAddressCtrl` ve geçerli nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Dwstyle*|[içinde] Denetime uygulanacak stillerin bitwise kombinasyonu. Daha fazla bilgi için [Stilleri Edit'e](../../mfc/reference/styles-used-by-mfc.md#edit-styles)bakın.|
|*Rect*|[içinde] Denetimin konumunu ve boyutunu içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.|
|*pParentWnd*|[içinde] Denetimin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.|
|*Nıd*|[içinde] Kontrol kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cnetaddressctrlcreateex"></a><a name="createex"></a>CNetAddressCtrl::CreateEx

Belirtilen genişletilmiş stilleri içeren bir ağ adresi denetimi oluşturur `CNetAddressCtrl` ve geçerli nesneye bağlar.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwExStyle*|[içinde] Denetime uygulanacak genişletilmiş stillerin bitwise kombinasyonu (OR). Daha fazla bilgi için [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevinin *dwExStyle* parametresini görün.|
|*Dwstyle*|[içinde] Denetime uygulanacak stillerin bitwise kombinasyonu (OR). Daha fazla bilgi için [Stilleri Edit'e](../../mfc/reference/styles-used-by-mfc.md#edit-styles)bakın.|
|*Rect*|[içinde] Denetimin konumunu ve boyutunu içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.|
|*pParentWnd*|[içinde] Denetimin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.|
|*Nıd*|[içinde] Kontrol kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip

Geçerli ağ adresi denetimiyle ilişkili balon ucunda bir hata iletisi görüntüler.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `S_OK` yöntem başarılı olursa değer; aksi takdirde, bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Geçerli ağ adresi denetiminin desteklenebildiği adres türlerini belirtmek için [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemini kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrışdırmak için [CNetAddressCtrl::GetAddress](#getaddress) yöntemini kullanın. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemini kullanarak [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız olursa hata iletisi bilgi ucunu görüntüleyin.

Bu ileti, Windows SDK'da açıklanan [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) makroyu çağırır. Bu makro `NCM_DISPLAYERRORTIP` iletiyi gönderir.

## <a name="cnetaddressctrlgetaddress"></a><a name="getaddress"></a>CNetAddressCtrl::GetAddress

Geçerli ağ adresi denetimiyle ilişkili ağ adresinin doğrulanmış ve ayrıştırılmış bir temsilini alır.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Parametreler

*pAddress*<br/>
[içinde, dışarı] [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) bir yapıya işaretçi.  GetAddress yöntemini aramadan önce bu yapının *pAddrInfo* üyesini [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) bir yapının adresine ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa değer S_OK; aksi takdirde, bir COM hata kodu. Olası hata kodları hakkında daha fazla bilgi için [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) makronun İade Değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa, [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) yapısı ağ adresi hakkında ek bilgiler içerir.

Geçerli ağ adresi denetiminin destekleyebilir adres türlerini belirtmek için [CNetAddressCtrl kullanın::SetAllowType](#setallowtype) yöntemini kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrışdırmak için [CNetAddressCtrl::GetAddress](#getaddress) yöntemini kullanın. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemini kullanarak [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız olursa hata iletisi bilgi ucunu görüntüleyin.

Bu yöntem, Windows SDK'da açıklanan [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) makroyu çağırır. Bu makro NCM_GETADDRESS iletisi gönderir.

## <a name="cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>CNetAddressCtrl::GetAllowType

Geçerli ağ adresi denetiminin destekedebileceği ağ adresi türünü alır.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ağ adresi denetiminin destekleyebilir adres türlerini belirten bayrakların bitwise birleşimi (VEYA). Daha fazla bilgi için [NET_STRING.](/windows/win32/shell/net-string)

### <a name="remarks"></a>Açıklamalar

Bu ileti, Windows SDK'da açıklanan [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) makroyu çağırır. Bu makro NCM_GETALLOWTYPE iletisi gönderir.

## <a name="cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>CNetAddressCtrl::SetAllowType

Geçerli ağ adresi denetiminin destekedebileceği ağ adresi türünü ayarlar.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwAddrMaske*|[içinde] Ağ adresi denetiminin destekleyebilir adres türlerini belirten bayrakların bitwise birleşimi (VEYA). Daha fazla bilgi için [NET_STRING.](/windows/win32/shell/net-string)|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa S_OK; aksi takdirde, bir COM hata kodu.

### <a name="remarks"></a>Açıklamalar

Geçerli ağ adresi denetiminin desteklenebildiği adres türlerini belirtmek için [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemini kullanın. Kullanıcının girdiği ağ adresini doğrulamak ve ayrışdırmak için [CNetAddressCtrl::GetAddress](#getaddress) yöntemini kullanın. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemini kullanarak [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız olursa hata iletisi bilgi ucunu görüntüleyin.

Bu ileti, Windows SDK'da açıklanan [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) makroyu çağırır. Bu makro NCM_SETALLOWTYPE iletisi gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[CNetAddressCtrl Sınıfı](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)
