---
title: CNetAddressCtrl sınıfı
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
ms.openlocfilehash: 23160c51466ce1a2857d3648dd5f4970dfe172f7
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504205"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl sınıfı

`CNetAddressCtrl` Sınıfı, giriş ve IPv4, IPv6 ve adlandırılmış DNS adreslerinin biçimini doğrulamak için kullanabileceğiniz ağ adresi denetimini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Oluşturur bir `CNetAddressCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|Belirtilen stilleriyle bir ağ adresi denetimi oluşturur ve bunu geçerli ekler `CNetAddressCtrl` nesne.|
|[CNetAddressCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stilleriyle bir ağ adresi denetimi oluşturur ve bunu geçerli ekler `CNetAddressCtrl` nesne.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Kullanıcı geçerli ağ adresi denetimi desteklenmeyen ağ adresi girdiğinde bir hata balon ipucu görüntüler.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Geçerli ağ adresi denetimi ile ilişkili ağ adresi doğrulanmış ve ayrıştırılmış bir gösterimini alır.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Geçerli ağ adresi denetimini destekleyen ağ adresi türünü alır.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Geçerli ağ adresi denetimini destekleyen ağ adresi türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Ağ adresi denetimi, kullanıcının girdiği adresinin biçimi doğru olduğunu doğrular. Denetim ağ adresine bağlanmaz. [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemini bir veya daha fazla adres türlerini belirtir, [CNetAddressCtrl::GetAddress](#getaddress) yöntemi ayrıştırabilir ve doğrulayın. Bir IPv4, IPv6 ve adlandırılmış bir sunucu, ağ, konak veya yayın iletisi hedef adresi biçiminde bir adres olabilir. Adresinin biçimi yanlış ise, kullanabileceğiniz [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) grafik işaret ağ adresi denetimi için metin kutusu ve bir önceden tanımlanmış görüntüler bilgi ipucu ileti kutusu görüntülemek için yöntemi hata iletisi.

`CNetAddressCtrl` Sınıfı türetilen [CEdit](../../mfc/reference/cedit-class.md) sınıfı. Sonuç olarak, ağ adresi denetimi tüm Windows düzenleme denetimi iletileri erişim sağlar.

Aşağıdaki şekil, bir ağ adresi denetimi içeren bir iletişim kutusu gösterir. Metin kutusunu (1) ağ adresi denetimi için bir geçersiz ağ adresi içeriyor. Ağ adresi geçersiz (2) bilgi ipucu iletisi görüntülenir.

![Bir ağ adresi denetimi ve Bilgi İpucu ile iletişim. ](../../mfc/reference/media/cnetaddctrl.png "İletişim bir ağ adresi denetimi ve bilgi ipucu.")

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir ağ adresi doğrulayan bir iletişim kutusu bölümüdür. Üç radyo düğmesi için olay işleyicileri, üç adresi türlerden biri olabilir ağ adresi belirtin. Kullanıcı ağ denetimi metin kutusuna bir adresi girer ve sonra adresinizi doğrulamak için bir düğmeye bastığında. Adresi geçerli bir başarı iletisi görüntülenir; Aksi takdirde, önceden tanımlı bilgi ipucu hata iletisi görüntülenir.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki kod örneği iletişim üstbilgi dosyasından tanımlar [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) ve [NET_ADDRESS_INFO](/windows/desktop/shell/hkey-type) gerektirdiği değişkenleri [CNetAddressCtrl::GetAddress](#getaddress)yöntemi.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

Bu sınıf, Windows Vista ve sonraki sürümlerde desteklenir.

Bu sınıf için ek gereksinimler açıklanmıştır [yapı gereksinimleri için Windows Vista ortak denetimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md).

##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl

Oluşturur bir `CNetAddressCtrl` nesne.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Açıklamalar

Kullanım [CNetAddressCtrl::Create](#create) veya [CNetAddressCtrl::CreateEx](#createex) Ağ denetimi oluşturma ve buna eklemek için yöntem `CNetAddressCtrl` nesne.

##  <a name="create"></a>  CNetAddressCtrl::Create

Belirtilen stilleriyle bir ağ adresi denetimi oluşturur ve bunu geçerli ekler `CNetAddressCtrl` nesne.

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
|*dwStyle*|[in] Denetime uygulanacak stilleri Bitsel bir birleşimi. Daha fazla bilgi için [düzenleme stilleri](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*Rect*|[in] Bir başvuru bir [RECT](/previous-versions/dd162897\(v=vs.85\)) denetimin boyutunu ve konumunu içeren yapısı.|
|*pParentWnd*|[in] Null olmayan bir işaretçiye bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst penceresine olan nesne.|
|*nID*|[in] Denetimin kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

##  <a name="createex"></a>  CNetAddressCtrl::CreateEx

Belirtilen genişletilmiş stilleriyle bir ağ adresi denetimi oluşturur ve bunu geçerli ekler `CNetAddressCtrl` nesne.

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
|*dwExStyle*|[in] Bitsel bir birleşimi (veya) genişletilmiş stiller denetime uygulanacak. Daha fazla bilgi için *dwExStyle* parametresinin [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) işlevi.|
|*dwStyle*|[in] Bitsel bir birleşimi (veya) denetime uygulanacak stilleri. Daha fazla bilgi için [düzenleme stilleri](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*Rect*|[in] Bir başvuru bir [RECT](/previous-versions/dd162897\(v=vs.85\)) denetimin boyutunu ve konumunu içeren yapısı.|
|*pParentWnd*|[in] Null olmayan bir işaretçiye bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst penceresine olan nesne.|
|*nID*|[in] Denetimin kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip

Geçerli ağ adresi denetimle ilişkili balon ipucu bir hata iletisi görüntüler.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Dönüş Değeri

Değer `S_OK` başarılıysa; değilse, bu yöntem, bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) geçerli ağ adresi denetimini destekleyen adresleri türlerini belirtmek için yöntemi. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırmak için yöntemi. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemi, bir hata iletisi bilgi ipucu görüntülenecek [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız.

Bu ileti çağırır [NetAddr_DisplayErrorTip](/windows/desktop/api/shellapi/nf-shellapi-netaddr_displayerrortip) Windows SDK'da açıklanan makrosu. Bu makro gönderir `NCM_DISPLAYERRORTIP` ileti.

##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress

Geçerli ağ adresi denetimi ile ilişkili olan ağ adresi doğrulanmış ve ayrıştırılmış bir gösterimini alır.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Parametreler

*pAddress*<br/>
[out içinde] İşaretçi bir [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) yapısı.  Ayarlama *pAddrInfo* adresine bu yapı üyesi bir [NET_ADDRESS_INFO](/windows/desktop/shell/hkey-type) siz GetAddress yöntemi çağırmadan önce yapılandırın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılıysa S_OK değeri; Aksi takdirde, bir COM hata kodu. Dönüş değerini bölümünü olası hata kodları hakkında daha fazla bilgi için bkz. [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) makrosu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa [NET_ADDRESS_INFO](/windows/desktop/shell/hkey-type) yapısı ağ adresi hakkında ek bilgiler içerir.

Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) adresleri geçerli ağ adresi denetimi destekleyebilir türlerini belirtmek için yöntemi. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırmak için yöntemi. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemi, bir hata iletisi bilgi ipucu görüntülenecek [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız.

Bu metodu çağıran [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) Windows SDK'da açıklanan makrosu. Bu makro NCM_GETADDRESS iletiyi gönderir.

##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType

Geçerli ağ adresi denetimini destekleyen ağ adresi türünü alır.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tür adresi belirten bir bit düzeyinde (veya) bayrakların birleşimi ağ adresi denetimini destekler. Daha fazla bilgi için [NET_STRING](/windows/desktop/shell/net-string).

### <a name="remarks"></a>Açıklamalar

Bu ileti çağırır [NetAddr_GetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getallowtype) Windows SDK'da açıklanan makrosu. Bu makro NCM_GETALLOWTYPE iletiyi gönderir.

##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType

Geçerli ağ adresi denetimini destekleyen ağ adresi türünü ayarlar.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwAddrMask*|[in] Tür adresi belirten bir bit düzeyinde (veya) bayrakların birleşimi ağ adresi denetimini destekler. Daha fazla bilgi için [NET_STRING](/windows/desktop/shell/net-string).|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılıysa S_OK; Aksi takdirde, bir COM hata kodu.

### <a name="remarks"></a>Açıklamalar

Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) geçerli ağ adresi denetimini destekleyen adresleri türlerini belirtmek için yöntemi. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırmak için yöntemi. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) yöntemi, bir hata iletisi bilgi ipucu görüntülenecek [CNetAddressCtrl::GetAddress](#getaddress) yöntemi başarısız.

Bu ileti çağırır [NetAddr_SetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_setallowtype) Windows SDK'da açıklanan makrosu. Bu makro NCM_SETALLOWTYPE iletiyi gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[CNetAddressCtrl Sınıfı](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)
