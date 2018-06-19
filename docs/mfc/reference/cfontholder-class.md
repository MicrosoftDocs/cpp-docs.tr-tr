---
title: CFontHolder sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5cb28b738822b3e35aa840c731eb11bc2c2b83d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367522"
---
# <a name="cfontholder-class"></a>CFontHolder sınıfı
Stok Font özelliği uygular ve bir Windows yazı tipi nesnesi işlevselliği kapsar ve `IFont` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|Oluşturan bir `CFontHolder` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|Bir kapsayıcının özelliği tarayıcıda görüntülenen dizesini alır.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Yazı tipinin döndürür `IDispatch` arabirimi.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Bir Windows yazı tipi için bir işleyici döner.|  
|[CFontHolder::InitializeFont](#initializefont)|Başlatır bir `CFontHolder` nesnesi.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|İlgili yazı tipi için bilgi alır.|  
|[CFontHolder::ReleaseFont](#releasefont)|Keser `CFontHolder` nesnesinin `IFont` ve `IFontNotification` arabirimleri.|  
|[CFontHolder::Select](#select)|Yazı tipi kaynak bir cihaz bağlamına seçer.|  
|[CFontHolder::SetFont](#setfont)|Bağlanan `CFontHolder` nesnesine bir `IFont` arabirimi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Bir işaretçi `CFontHolder` nesnenin `IFont` arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFontHolder` bir taban sınıfı yok.  
  
 Özel yazı tipi özelliklerini denetlemek için uygulamak için bu sınıf kullanın. Makaleyi gibi özellikleri oluşturma hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: yazı tiplerini kullanarak](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CFontHolder`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="cfontholder"></a>  CFontHolder::CFontHolder  
 Oluşturan bir `CFontHolder` nesnesi.  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNotify*  
 Yazı tipinin işaretçi `IPropertyNotifySink` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `InitializeFont` kullanmadan önce sonuç nesnesi başlatılamadı.  
  
##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString  
 Bir kapsayıcının özelliği tarayıcıda görüntülenen bir dize alır.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `strValue`  
 Başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntü dizesini tutun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize başarıyla alınırsa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch  
 Yazı tipinin dağıtma arabirimi bir işaretçi almak için bu işlevini çağırın.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CFontHolder` nesnenin **IFontDisp** arabirimi. İşlev çağrıları Not `GetFontDispatch` çağırmalıdır `IUnknown::Release` ile işiniz bittiğinde bu arabirim işaretçisi üzerinde.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `InitializeFont` çağırmadan önce `GetFontDispatch`.  
  
##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle  
 Bir Windows yazı tipi için bir tanıtıcı almak için bu işlevini çağırın.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parametreler  
 `cyLogical`  
 Denetim çizilen dikdörtgenin mantıksal birimler cinsinden yüksekliği.  
  
 `cyHimetric`  
 Yükseklik içinde `MM_HIMETRIC` denetiminin birimleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi nesnesi için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Oranını `cyLogical` ve `cyHimetric` yazı tipinin punto boyutunu ifade için doğru görüntüleme boyutu mantıksal birimler hesaplamak için kullanılan `MM_HIMETRIC` birimleri:  
  
 Görüntü boyutu = ( `cyLogical`  /  `cyHimetric`) yazı tipi boyutu X  
  
 Hiçbir parametre sürüm ekran için doğru boyutta bir yazı tipi için bir tanıtıcı döndürür.  
  
##  <a name="initializefont"></a>  CFontHolder::InitializeFont  
 Başlatır bir `CFontHolder` nesnesi.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFontDesc`  
 Yazı tipi açıklama yapısına yönelik işaretçinin ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)) yazı tipinin özelliklerini belirtir.  
  
 `pFontDispAmbient`  
 Kapsayıcının ortam Font özelliği işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `pFontDispAmbient` değil **NULL**, `CFontHolder` nesne için bir kopyasını bağlı `IFont` kapsayıcının ortam Font özelliği tarafından kullanılan arabirim.  
  
 Varsa `pFontDispAmbient` olan **NULL**, yeni bir yazı tipi nesnesi gösterdiği yazı tipi açıklamasından ya da oluşturulur `pFontDesc` veya `pFontDesc` olan **NULL**, varsayılan açıklamasından.  
  
 Oluşturduktan sonra bu işlev çağrısı bir `CFontHolder` nesnesi.  
  
##  <a name="m_pfont"></a>  CFontHolder::m_pFont  
 Bir işaretçi `CFontHolder` nesnenin `IFont` arabirimi.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics  
 Tarafından temsil edilen fiziksel yazı tipi hakkında bilgi alır `CFontHolder` nesnesi.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Parametreler  
 `lptm`  
 Bir işaretçi bir [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) bilgi alacak yapısı.  
  
##  <a name="releasefont"></a>  CFontHolder::ReleaseFont  
 Bu işlev bağlantısını keser `CFontHolder` nesnesinin kendi `IFont` arabirimi.  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>  CFontHolder::Select  
 Belirtilen cihaz bağlamına denetiminizin yazı tipi seçmek için bu işlevini çağırın.  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Cihaz bağlamı içine yazı tipi seçilir.  
  
 `cyLogical`  
 Denetim çizilen dikdörtgenin mantıksal birimler cinsinden yüksekliği.  
  
 `cyHimetric`  
 Yükseklik içinde `MM_HIMETRIC` denetiminin birimleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değiştirilen yazı tipi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [GetFontHandle](#getfonthandle) bir irdelemesi `cyLogical` ve `cyHimetric` parametreleri.  
  
##  <a name="setfont"></a>  CFontHolder::SetFont  
 Varolan bir yazı tipi serbest bırakır ve bağlayan `CFontHolder` nesnesine bir `IFont` arabirimi.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNewFont*  
 İşaretçi yeni `IFont` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPropExchange Sınıfı](../../mfc/reference/cpropexchange-class.md)
