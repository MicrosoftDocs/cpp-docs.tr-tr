---
title: Cıpaddressctrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0177d350d37b7fb1afe27d8aa4aad98dd985ec13
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679184"
---
# <a name="cipaddressctrl-class"></a>Cıpaddressctrl sınıfı
Windows ortak IP adresi denetimi işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Oluşturur bir `CIPAddressCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP adresi denetimi içeriğini temizler.|  
|[CIPAddressCtrl::Create](#create)|Bir IP adresi denetimi oluşturur ve ona bağlanan bir `CIPAddressCtrl` nesne.|  
|[CIPAddressCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir IP adresi denetimi oluşturur ve ona ekler bir `CIPAddressCtrl` nesne.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|IP adresi denetimi tüm dört alanlarına ilişkin adres değerlerini alır.|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP adresi denetimi içindeki tüm alanları boş olup olmadığını belirler.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|IP adresi denetimi tüm dört alan adres değerlerini ayarlar.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Klavye odağı belirtilen alan IP adresi denetimi için ayarlar.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Belirtilen IP adresi denetimi alanında aralığı ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir denetimi bir düzenleme denetimi için benzer bir IP adresi denetimini girin ve Internet Protokolü (IP) biçimindeki sayısal bir adrese işlemek sağlar.  
  
 Bu denetimi (ve bu nedenle `CIPAddressCtrl` sınıfı) altında Microsoft Internet Explorer 4.0 ve sonraki sürümlerde çalışan programlar için kullanılabilir. Bunlar ayrıca Windows ve Windows NT gelecekteki sürümlerinde kullanılabilir.  
  
 IP adresi denetimi hakkında daha fazla genel bilgi için bkz: [IP adresi denetimleri](/windows/desktop/Controls/ip-address-controls) Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl  
 Oluşturur bir `CIPAddressCtrl` nesne.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress  
 IP adresi denetimi içeriğini temizler.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_CLEARADDRESS](/windows/desktop/Controls/ipm-clearaddress)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 Bir IP adresi denetimi oluşturur ve ona bağlanan bir `CIPAddressCtrl` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 IP adresi denetimin stili. Pencere stilleri bileşimini uygulayın. Denetimi alt pencere olması gerektiğinden WS_CHILD stili eklemeniz gerekir. Bkz: [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK'sındaki windows stilleri listesi.  
  
 *Rect*  
 IP adresi denetimin boyutunu ve konumunu başvuru. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 *pParentWnd*  
 IP adresi denetiminin üst penceresine bir işaretçi. NULL olmamalıdır.  
  
 *nID*  
 IP adresi denetimin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CIPAddressCtrl` iki adımda nesne.  
  
1.  Oluşturan oluşturucu çağrısı `CIPAddressCtrl` nesne.  
  
2.  Çağrı `Create`, IP adresi denetimi oluşturur.  
  
 Genişletilmiş windows stilleri ile denetiminizi kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 Bir denetim (alt pencere) oluşturma ve ilişkilendirmek için bu işlevi çağırın `CIPAddressCtrl` nesne.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwExStyle*  
 Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.  
  
 *dwStyle*  
 IP adresi denetimin stili. Pencere stilleri bileşimini uygulayın. Denetimi alt pencere olması gerektiğinden WS_CHILD stili eklemeniz gerekir. Bkz: [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK'sındaki windows stilleri listesi.  
  
 *Rect*  
 Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin ana penceresine bir işaretçi.  
  
 *nID*  
 Denetimin alt penceresi kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 IP adresi denetimi tüm dört alanlarına ilişkin adres değerlerini alır.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>Parametreler  
 *nField0*  
 Paketlenmiş bir IP adresinden alan 0 değerine başvuru.  
  
 *nField1*  
 Paketlenmiş bir IP adresinden alan 1 değerine başvuru.  
  
 *nField2*  
 Paketlenmiş bir IP adresinden alan 2 değerine başvuru.  
  
 *nField3*  
 Paketlenmiş bir IP adresinden alan 3 değerine başvuru.  
  
 *dwAddress*  
 IP adresi alır bir DWORD değeri adresini başvuru. Bkz: **açıklamalar** gösteren bir tablo için nasıl *dwAddress* doldurulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 IP adresi denetimi boş olmayan alan sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_GETADDRESS](/windows/desktop/Controls/ipm-getaddress)Windows SDK içinde açıklandığı gibi. Yukarıdaki ilk prototip, sırasıyla sağa okuma numaraları 0 ile 3 denetimin alanlarında için sol, dört parametreleri doldurun. Yukarıdaki ikinci prototipteki *dwAddress* şu şekilde doldurulur.  
  
|Alan|Alan değeri içeren BITS|  
|-----------|-------------------------------------|  
|0|24 ile 31|  
|1.|16-23|  
|2|8 ile 15|  
|3|0 ile 7 arasındaki|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 IP adresi denetimi içindeki tüm alanları boş olup olmadığını belirler.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm IP adresi denetimi alanları boş olan olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_ISBLANK](/windows/desktop/Controls/ipm-isblank)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 IP adresi denetimi tüm dört alan adres değerlerini ayarlar.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>Parametreler  
 *nField0*  
 Paketlenmiş bir IP adresi alanı 0 değeri.  
  
 *nField1*  
 Paketlenmiş bir IP adresi alanı 1 değeri.  
  
 *nField2*  
 Paketlenmiş bir IP adresi alanı 2 değeri.  
  
 *nField3*  
 Paketlenmiş bir IP adresi alanı 3 değeri.  
  
 *dwAddress*  
 Yeni IP adresini içeren bir DWORD değeri. Bkz: **açıklamalar** için DWORD değerini nasıl doldurulur gösteren bir tablo.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_SETADDRESS](/windows/desktop/Controls/ipm-setaddress)Windows SDK içinde açıklandığı gibi. Yukarıdaki ilk prototip, sırasıyla sağa okuma numaraları 0 ile 3 denetimin alanlarında için sol, dört parametreleri doldurun. Yukarıdaki ikinci prototipteki *dwAddress* şu şekilde doldurulur.  
  
|Alan|Alan değeri içeren BITS|  
|-----------|-------------------------------------|  
|0|24 ile 31|  
|1.|16-23|  
|2|8 ile 15|  
|3|0 ile 7 arasındaki|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 Klavye odağı belirtilen alan IP adresi denetimi için ayarlar.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Parametreler  
 *nAlan*  
 Sıfır tabanlı alan dizini odağı ayarlamanız gerekir. Bu değer, alanlar sayısından büyükse, odak ilk boş alana ayarlanır. Tüm alanları boş olmayan ise odak ilk alan için ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_SETFOCUS](/windows/desktop/Controls/ipm-setfocus)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange  
 Belirtilen IP adresi denetimi alanında aralığı ayarlar.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Parametreler  
 *nAlan*  
 Sıfır tabanlı alan dizini aralığın uygulanır.  
  
 *nLower*  
 Bu IP adresi denetimi belirtilen alan alt sınırını alma tamsayı başvuru.  
  
 *nUpper*  
 Bu IP adresi denetimi belirtilen alan sayısı üst sınırını alma tamsayı başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışı uygulayan [IPM_SETRANGE](/windows/desktop/Controls/ipm-setrange)Windows SDK içinde açıklandığı gibi. İki parametre kullanmak *nLower* ve *nUpper*yerine alan alt ve üst sınırlarını belirtmek için *wRange* Win32 iletinin kullanılan parametre.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



