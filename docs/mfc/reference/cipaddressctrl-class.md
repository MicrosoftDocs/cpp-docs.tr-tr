---
title: CIPAddressCtrl sınıfı | Microsoft Docs
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
ms.openlocfilehash: e3e5f88dc011e358c0438209f0a4b3e277419be9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042163"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl sınıfı
Windows ortak IP adresi denetim işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Oluşturan bir `CIPAddressCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP adresi denetimi içeriğini temizler.|  
|[CIPAddressCtrl::Create](#create)|Bir IP adresi denetimi oluşturur ve ona ekler bir `CIPAddressCtrl` nesnesi.|  
|[CIPAddressCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir IP adresi denetimi oluşturur ve ekler bir `CIPAddressCtrl` nesnesi.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|IP adresi denetimi tüm dört alanlarında adres değerlerini alır.|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP adresi denetimi tüm alanları boş olup olmadığını belirler.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Tüm dört alanlar için adres değerleri, IP adresi denetimi ayarlar.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP adresi denetimi belirtilen alan için klavye odağını ayarlar.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Belirtilen IP adresi denetimi alanında aralığı ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir IP adresi denetimi, bir düzenleme denetimi için benzer bir denetimi girin ve sayısal adresini Internet Protokolü (IP) biçiminde işlemek sağlar.  
  
 Bu denetim (ve bu nedenle `CIPAddressCtrl` sınıfı) altında Microsoft Internet Explorer 4.0 ve sonraki sürümlerde çalışan programlar için kullanılabilir. Bunlar ayrıca Windows ve Windows NT gelecekteki sürümlerinde kullanılabilir.  
  
 IP adresi denetimi hakkında daha fazla genel bilgi için bkz: [IP adresi denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb761372) Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl  
 Oluşturur bir `CIPAddressCtrl` nesnesi.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress  
 IP adresi denetimi içeriğini temizler.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 Bir IP adresi denetimi oluşturur ve ona ekler bir `CIPAddressCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 IP adresi denetimin stili. Pencere Stilleri bileşimi geçerli. Eklemelisiniz **WS_CHILD** denetimi alt pencere olması gerektiğinden stili. Bkz: [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) windows stilleri listesi için Windows SDK.  
  
 *Rect*  
 IP adresi denetimin boyutunu ve konumunu referansı. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 *pParentWnd*  
 IP adresi denetimin üst penceresi için bir işaretçi. Değil olmalıdır **NULL.**  
  
 *nID*  
 IP adresi denetimin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CIPAddressCtrl` iki adımda nesne.  
  
1.  Oluşturur Oluşturucusu çağrı `CIPAddressCtrl` nesnesi.  
  
2.  Çağrı `Create`, IP adresi denetimi oluşturur.  
  
 Genişletilmiş windows stilleri denetimi ile kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 Bir denetim (alt pencere) oluşturmak ve bunu ile ilişkilendirmek için bu işlevi çağırmak `CIPAddressCtrl` nesnesi.  
  
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
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: *dwExStyle* parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 *dwStyle*  
 IP adresi denetimin stili. Pencere Stilleri bileşimi geçerli. Eklemelisiniz **WS_CHILD** denetimi alt pencere olması gerektiğinden stili. Bkz: [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) windows stilleri listesi için Windows SDK.  
  
 *Rect*  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin üst penceresi için bir işaretçi.  
  
 *nID*  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 IP adresi denetimi tüm dört alanlarında adres değerlerini alır.  
  
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
 Paketlenmiş bir IP adresinden bir başvuru alanının 0 değeri.  
  
 *nField1*  
 Paketlenmiş bir IP adresi alan 1 değeri için başvuru.  
  
 *nField2*  
 Paketlenmiş bir IP adresinden bir başvuru alanının 2 değeri.  
  
 *nField3*  
 Paketlenmiş bir IP adresi alan 3 değeri için başvuru.  
  
 *dwAddress*  
 Bir başvuru adresine bir `DWORD` IP adresi alan değeri. Bkz: **açıklamalar** gösteren bir tablo için nasıl *dwAddress* doldurulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 IP adresi denetimi boş olmayan alanları sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), Windows SDK'ın açıklandığı gibi. Yukarıdaki ilk prototip, sırasıyla sağ okuma numaraları 0 ile 3 denetiminin alanlarındaki için sol, dört parametre doldurmak. Yukarıdaki ikinci prototip içinde *dwAddress* gibi doldurulur.  
  
|Alan|Alan değeri içeren BITS|  
|-----------|-------------------------------------|  
|0|24 ile 31 arasında|  
|1.|23 aracılığıyla 16|  
|2|8-15|  
|3|0 ile 7 arasında|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 IP adresi denetimi tüm alanları boş olup olmadığını belirler.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm IP adresi denetimi alanlar boşken sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 Tüm dört alanlar için adres değerleri, IP adresi denetimi ayarlar.  
  
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
 A `DWORD` değeri yeni IP adresini içerir. Bkz: **açıklamalar** gösteren bir tablo için nasıl `DWORD` değeri doldurulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), Windows SDK'ın açıklandığı gibi. Yukarıdaki ilk prototip, sırasıyla sağ okuma numaraları 0 ile 3 denetiminin alanlarındaki için sol, dört parametre doldurmak. Yukarıdaki ikinci prototip içinde *dwAddress* gibi doldurulur.  
  
|Alan|Alan değeri içeren BITS|  
|-----------|-------------------------------------|  
|0|24 ile 31 arasında|  
|1.|23 aracılığıyla 16|  
|2|8-15|  
|3|0 ile 7 arasında|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 IP adresi denetimi belirtilen alan için klavye odağını ayarlar.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Parametreler  
 *nAlan*  
 Sıfır tabanlı alan dizini odağı ayarlamanız gerekir. Bu değer alanları sayısından büyükse, odak ilk boş alana ayarlanır. Boş olmayan tüm alanlar odak ilk alana ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), Windows SDK'ın açıklandığı gibi.  
  
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
 Bu IP adresi denetiminde alt sınırı belirtilen alanın alma tamsayı referansı.  
  
 *nUpper*  
 Bu IP adresi denetimi belirtilen alan sayısı üst sınırı alma tamsayı referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), Windows SDK'ın açıklandığı gibi. İki parametre kullanmak *nLower* ve *nUpper*yerine alanın alt ve üst sınırlar belirtmek için *wRange* Win32 iletisiyle kullanılan parametre.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



