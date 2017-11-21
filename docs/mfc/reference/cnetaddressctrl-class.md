---
title: "CNetAddressCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 047032e65f0d1fa7847caae36e10fac4175b5db0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl sınıfı
`CNetAddressCtrl` Sınıfı, giriş ve IPv4, IPv6 ve adlandırılmış DNS adreslerini biçimi doğrulamak için kullanabileceğiniz ağ adresi denetimi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Oluşturan bir `CNetAddressCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|Bir ağ adresi denetimi ile belirtilen stilleri oluşturur ve geçerli iliştirir `CNetAddressCtrl` nesnesi.|  
|[CNetAddressCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stilleri ile bir ağ adresi denetimi oluşturur ve geçerli iliştirir `CNetAddressCtrl` nesnesi.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Kullanıcı desteklenmeyen ağ adresi, geçerli ağ adresi denetimi girdiğinde bir hata balon ipucu görüntüler.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|Geçerli ağ adresi denetimi ile ilişkilendirilmiş ağ adresi doğrulanmış ve ayrıştırılmış bir gösterimini alır.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Geçerli ağ adresi denetimi destekleyebilir ağ adres türünü alır.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Geçerli ağ adresi denetimi destekleyebilir ağ adres türünü ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ağ adresi denetimi, kullanıcının girdiği adresi biçimi doğru olduğunu doğrular. Denetim ağ adresine bağlanamıyor. [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemi belirtir. bir veya daha fazla adres türleri, [CNetAddressCtrl::GetAddress](#getaddress) yöntemi ayrıştırabilir ve doğrulayın. Bir adresi, bir IPv4, IPv6 veya bir sunucu, ağ, ana bilgisayar veya yayın iletisi hedef adlandırılmış adresini biçiminde olabilir. Adresinin biçimi yanlış ise, kullanabileceğiniz [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) grafik noktaları ağ adresi denetimi metin kutusuna ve önceden tanımlanmış bir görüntüleyen bir bilgi ipucu ileti kutusu görüntülemek için yöntemi hata iletisi.  
  
 `CNetAddressCtrl` Sınıfı türetilir [CEdit](../../mfc/reference/cedit-class.md) sınıfı. Sonuç olarak, ağ adresi denetimi tüm Windows Düzenle denetim iletileri erişim sağlar.  
  
 Aşağıdaki şekilde, bir ağ adresi denetimini içeren bir iletişim kutusu gösterilmektedir. Metin kutusu (1) ağ adresi denetimi için geçersiz bir ağ adresi içerir. Ağ adresi geçersiz değilse (2) bilgi ipucu ileti görüntülenir.  
  
 ![Bir ağ adresi denetimi ve Bilgi İpucu ile iletişim. ] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir ağ adresi doğrulayan bir iletişim kutusu bölümüdür. Üç radyo düğmeleri için olay işleyicileri belirtin ağ adresi üç adres türlerden biri olabilir. Kullanıcı ağ denetimi metin kutusuna bir adresi girer ve ardından adresini doğrulamak için bir düğmeye basar. Adres geçerli ise, bir başarı iletisi görüntülenir; Aksi takdirde, önceden tanımlı bilgi ipucu hata iletisi görüntülenir.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde iletişim üstbilgi dosyasından tanımlar [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) ve [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) gerektirdiği değişkenleri [CNetAddressCtrl::GetAddress](#getaddress)yöntemi.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
 Bu sınıf desteklenir [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] ve daha sonra.  
  
 Bu sınıf için ek gereksinimler açıklanmıştır [yapı gereksinimleri için Windows Vista ortak denetimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl  
 Oluşturan bir `CNetAddressCtrl` nesnesi.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CNetAddressCtrl::Create](#create) veya [CNetAddressCtrl::CreateEx](#createex) Ağ denetimi oluşturmak ve ona eklemek için yöntemi `CNetAddressCtrl` nesnesi.  
  
##  <a name="create"></a>CNetAddressCtrl::Create  
 Bir ağ adresi denetimi ile belirtilen stilleri oluşturur ve geçerli iliştirir `CNetAddressCtrl` nesnesi.  
  
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
|[in]`dwStyle`|Denetime uygulanacak stilleri Bitsel bir birleşimi. Daha fazla bilgi için bkz: [düzenleme stilleri](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in]`rect`|Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) denetimin boyutunu ve konumunu içeren yapısı.|  
|[in]`pParentWnd`|Null olmayan gösteren bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst pencere nesnesi.|  
|[in]`nID`|Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
##  <a name="createex"></a>CNetAddressCtrl::CreateEx  
 Belirtilen genişletilmiş stilleri ile bir ağ adresi denetimi oluşturur ve geçerli iliştirir `CNetAddressCtrl` nesnesi.  
  
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
|[in]`dwExStyle`|Bitsel bir birleşimi (veya) denetime uygulanacak genişletilmiş stilleri. Daha fazla bilgi için bkz: `dwExStyle` parametresinin [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) işlevi.|  
|[in]`dwStyle`|Bitsel bir birleşimi (veya) denetime uygulanacak stilleri. Daha fazla bilgi için bkz: [düzenleme stilleri](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in]`rect`|Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) denetimin boyutunu ve konumunu içeren yapısı.|  
|[in]`pParentWnd`|Null olmayan gösteren bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst pencere nesnesi.|  
|[in]`nID`|Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
##  <a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip  
 Geçerli ağ adresi denetimle ilişkili balon ipucu bir hata iletisi görüntüler.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değer `S_OK` bu yöntem başarılı olursa Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemi geçerli ağ adresi denetimi destekleyebilir adresleri türlerini belirtin. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) yöntemi doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırılamadı. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) durumunda bir hata iletisi bilgi ipucu görüntülenecek yöntemi [CNetAddressCtrl::GetAddress](#getaddress) yöntemdir başarısız.  
  
 Bu ileti çağırır [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) Windows SDK'ın açıklanan makrosu. Bu makrosu gönderir `NCM_DISPLAYERRORTIP` ileti.  
  
##  <a name="getaddress"></a>CNetAddressCtrl::GetAddress  
 Geçerli ağ adresi denetimi ile ilişkilendirilmiş ağ adresi doğrulanmış ve ayrıştırılmış bir gösterimini alır.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[içinde out]`pAddress`|İşaretçi bir [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) yapısı.  Ayarlama `pAddrInfo` adresine bu yapı üyesi bir [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress yöntemi çağırmadan önce yapılandırın.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değer `S_OK` bu yöntem başarılı olursa Aksi durumda, bir COM hata kodu. Dönüş değeri bölümünü olası hata kodları hakkında daha fazla bilgi için bkz [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) makrosu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarılı olursa [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) yapısı ağ adresi hakkında ek bilgiler içerir.  
  
 Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemi geçerli ağ adresi denetimi destekleyebilmesi adresleri türlerini belirtin. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) yöntemi doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırılamadı. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) durumunda bir hata iletisi bilgi ipucu görüntülenecek yöntemi [CNetAddressCtrl::GetAddress](#getaddress) yöntemdir başarısız.  
  
 Bu yöntemi çağırır [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) Windows SDK'ın açıklanan makrosu. Bu makrosu gönderir `NCM_GETADDRESS` ileti.  
  
##  <a name="getallowtype"></a>CNetAddressCtrl::GetAllowType  
 Geçerli ağ adresi denetimi destekleyebilir ağ adres türünü alır.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağ adresi denetimi adres türleri belirten Bitsel bir birleşimi (veya) bayrakları destekler. Daha fazla bilgi için bkz: [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ileti çağırır [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) Windows SDK'ın açıklanan makrosu. Bu makrosu gönderir `NCM_GETALLOWTYPE` ileti.  
  
##  <a name="setallowtype"></a>CNetAddressCtrl::SetAllowType  
 Geçerli ağ adresi denetimi destekleyebilir ağ adres türünü ayarlar.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`dwAddrMask`|Ağ adresi denetimi adres türleri belirten Bitsel bir birleşimi (veya) bayrakları destekler. Daha fazla bilgi için bkz: [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Bu yöntem başarılı olursa; Aksi halde, bir COM hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CNetAddressCtrl::SetAllowType](#setallowtype) yöntemi geçerli ağ adresi denetimi destekleyebilir adresleri türlerini belirtin. Kullanım [CNetAddressCtrl::GetAddress](#getaddress) yöntemi doğrulamak ve kullanıcının girdiği ağ adresi ayrıştırılamadı. Kullanım [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) durumunda bir hata iletisi bilgi ipucu görüntülenecek yöntemi [CNetAddressCtrl::GetAddress](#getaddress) yöntemdir başarısız.  
  
 Bu ileti çağırır [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) Windows SDK'ın açıklanan makrosu. Bu makrosu gönderir `NCM_SETALLOWTYPE` ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CNetAddressCtrl sınıfı](../../mfc/reference/cnetaddressctrl-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)
