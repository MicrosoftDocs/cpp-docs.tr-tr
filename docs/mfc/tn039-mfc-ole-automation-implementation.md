---
title: 'TN039: MFC OLE Otomasyon uygulaması | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97c42f59042490f6408fb457b12f4bdb1a2eeb88
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953366"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE Otomasyon Uygulaması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch arabirimi genel bakış  
 `IDispatch` Arabirimidir olarak uygulamaları kullanıma Visual BASIC veya diğer diller gibi diğer uygulamaları yapabileceğiniz gibi uygulamanın özelliklerini kullandığınız yöntemleri ve özellikleri anlamına gelir. Bu arabirim, en önemli parçasıdır `IDispatch::Invoke` işlevi. MFC kullanır "eşlemeleri dağıtma" uygulamak için `IDispatch::Invoke`. Düzenini veya "şeklini" gönderme harita MFC Uygulama bilgileri sağlar, `CCmdTarget`-doğrudan nesnenin özelliklerini yönetmek veya üye işlevlerini karşılamak için nesne içinde çağırın şekilde türetilmiş sınıfları, `IDispatch::Invoke` istek sayısı.  
  
 Çoğunlukla, ClassWizard ve MFC Uygulama Programcı OLE Otomasyon ayrıntılarını çoğunu gizlemek üzere işbirliği yapar. Programcı uygulamada kullanıma sunmak için gerçek işlevselliği yoğunlaşır ve temel tesisat hakkında endişelenmeye gerek yoktur.  
  
 MFC arka planda ne yaptığını anlamak gerekli olduğu durumlar vardır. Bu Not nasıl framework atar adres **DISPID**s üye işlevleri ve özellikleri. MFC kullanan atamak için algoritmasının bilgi **DISPID**s olduğunda yalnızca gerekli uygulamanızın nesneleri için bir "tür kitaplığı" oluşturduğunuzda gibi kimlikleri, bilmeniz gerekir.  
  
## <a name="mfc-dispid-assignment"></a>MFC DISPID atama  
 Otomasyon (Visual Basic kullanıcı, örneğin), son kullanıcı görür ancak gerçek adlarını Otomasyon özellikleri ve yöntemleri (örneğin, obj. kendi kodunda etkin ShowWindow) uygulaması `IDispatch::Invoke` gerçek adlarını almaz. En iyi duruma getirme nedenlerle aldığı bir **DISPID**, "yöntem veya erişilecek özellik açıklayan bir 32 bit Sihirli tanımlama bilgisi" olduğu. Bunlar **DISPID** değerleri sağlayıcıdan döndürülen `IDispatch` uygulaması adlı başka bir yöntem aracılığıyla `IDispatch::GetIDsOfNames`. Bir otomasyon istemci uygulaması çağıracak `GetIDsOfNames` her üye veya özellik için erişim ve bunları sonraki çağrılar için önbelleğe amaçlamaktadır sonra `IDispatch::Invoke`. Bu şekilde, pahalı dize arama yalnızca bir kez nesne kullanımı yerine bir kez başına yapılır `IDispatch::Invoke` çağırın.  
  
 MFC belirler **DISPID**s her yöntem ve özellik için temel üzerinde ikisinden:  
  
-   (1 göreli) gönderme haritanın üst mesafe  
  
-   En çok türetilen sınıfı (0 göreli) gönderme eşlemesinden uzaklığı  
  
 **DISPID** iki bölüme ayrılmıştır. **LOWORD** , **DISPID** gönderme haritanın üst mesafe ilk bileşeni içerir. **HIWORD** en çok türetilen sınıf mesafe içerir. Örneğin:  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x,
    m_y;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
BEGIN_DISPATCH_MAP(CDispPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x",
    m_x,
    VT_I2)  
    DISP_PROPERTY(CDispPoint, "y",
    m_y,
    VT_I2)  
END_DISPATCH_MAP()  
 
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Gördüğünüz gibi her ikisi de OLE Otomasyon arabirimleri kullanıma iki sınıf vardır. Bu sınıfların birini diğer türetilmiş ve böylece OLE Otomasyon bölümü de dahil olmak üzere, temel sınıfın işlevselliği yararlanır ("x" ve "y" özellikleri bu durumda).  
  
 MFC oluşturacağını **DISPID**s için sınıf CDispPoint gibi:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Özellikleri bir taban sınıf içinde olmadığından **HIWORD** , **DISPID** her zaman sıfır (CDispPoint için en çok türetilen sınıf mesafe sıfırsa) olur.  
  
 MFC oluşturacağını **DISPID**s için sınıf CDisp3DPoint gibi:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Z özelliğinin verilen bir **DISPID** sıfır **HIWORD** CDisp3DPoint özellikleri gösterme sınıfında tanımlamış. Bir taban sınıf içinde X ve Y özellikleri tanımlamış **HIWORD** , **DISPID** bu özellikler tanımlanmışsa sınıfı en çok türetilen sınıfından bir türetme uzaklıkta olduğundan 1 ' dir.  
  
> [!NOTE]
>  **LOWORD** Haritası açık girişleri bulunsa bile her zaman eşleme konumu tarafından belirlenir **DISPID** (hakkında bilgi için sonraki bölüme bakın **_ıd** sürümleri `DISP_PROPERTY` ve `DISP_FUNCTION` makroları).  
  
## <a name="advanced-mfc-dispatch-map-features"></a>Gelişmiş MFC gönderme eşleme özellikleri  
 Visual C++ bu sürümü ile ClassWizard desteklemediği ek özellikler birkaç vardır. ClassWizard destekleyen `DISP_FUNCTION`, `DISP_PROPERTY`, ve `DISP_PROPERTY_EX` tanımlayan bir yöntemi, üye değişkeni özelliğinin ve get/set üyesi işlevi özellik, sırasıyla. Bu özellikler genellikle çoğu otomasyon sunucuları oluşturmak için gerekli değildir.  
  
 Desteklenen ClassWizard makroları yeterli olmadığı durumlarda, aşağıdaki ek makroları kullanılabilir: `DISP_PROPERTY_NOTIFY`, ve `DISP_PROPERTY_PARAM`.  
  
## <a name="disppropertynotify--macro-description"></a>Dısp_property_notıfy — Makrosu açıklaması  
  
```  
 
    DISP_PROPERTY_NOTIFY(
 theClass,   
    pszName, 
    memberName, 
    pfnAfterSet, 
    vtPropType) 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 Sınıfın adı.  
  
 *pszName*  
 Dış özelliğin adı.  
  
 *memberName*  
 Özellik depolandığı üye değişkeni adı.  
  
 *pfnAfterSet*  
 Özelliği değiştirildiğinde çağırmak için üye işlevinin adı.  
  
 *vtPropType*  
 Özelliğin türünü belirten bir değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Ek bağımsız değişken kabul bu makro çok dısp_property gibi olmasıdır. Ek bağımsız değişken *pfnAfterSet,* hiçbir parametre 'void OnPropertyNotify()' alır ve hiçbir şey döndüren bir üye işlevi olması gerekir. Çağrılacağı **sonra** üye değişkeni değiştirildi.  
  
## <a name="disppropertyparam--macro-description"></a>Dısp_property_param — Makrosu açıklaması  
  
```  
 
    DISP_PROPERTY_PARAM(
 theClass,   
    pszName, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 Sınıfın adı.  
  
 *pszName*  
 Dış özelliğin adı.  
  
 *memberGet*  
 Özellik get için kullanılan üye işlevinin adı.  
  
 *memberSet*  
 Özelliği ayarlamak için kullanılan üye işlevinin adı.  
  
 *vtPropType*  
 Özelliğin türünü belirten bir değer.  
  
 *vtsParams*  
 Bir dize alanı VTS_ her parametre için ayrılmış.  
  
## <a name="remarks"></a>Açıklamalar  
 Çok dısp_property_ex makrosu gibi bu makrosu ile ayrı Get ve kümesi üye işlevleri erişilen bir özelliğini tanımlar. Ancak, bu makrosu özelliği için bir parametre listesi belirtmenize olanak tanır. Bu, diğer herhangi bir yolla dizine veya parametreli özellikleri uygulamak için kullanışlıdır. Parametreleri her zaman ilk olarak, yeni değer özelliği için arkasından yerleştirilir. Örneğin:  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item",
    GetItem,
    SetItem,
    VT_DISPATCH,
    VTS_I2 VTS_I2)  
```  
  
 Alma ve üye işlevleri ayarlama karşılık gelir:  
  
```  
LPDISPATCH CMyObject::GetItem(short row,
    short col)  
void CMyObject::SetItem(short row,
    short col,
    LPDISPATCH newValue)  
```  
  
## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — Makrosu açıklamaları  
  
```  
 
    DISP_FUNCTION_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnMember, 
    vtRetVal, 
    vtsParams)DISP_PROPERTY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    vtPropType)DISP_PROPERTY_NOTIFY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    pfnAfterSet, 
    vtPropType)DISP_PROPERTY_EX_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType)DISP_PROPERTY_PARAM_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 Sınıfın adı.  
  
 *pszName*  
 Dış özelliğin adı.  
  
 *DISPID*  
 Özellik veya yöntem için sabit DISPID.  
  
 *pfnGet*  
 Özellik get için kullanılan üye işlevinin adı.  
  
 *pfnSet*  
 Özelliği ayarlamak için kullanılan üye işlevinin adı.  
  
 *memberName*  
 Özelliğini eşleştirmek için üye değişkeni adı  
  
 *vtPropType*  
 Özelliğin türünü belirten bir değer.  
  
 *vtsParams*  
 Bir dize alanı VTS_ her parametre için ayrılmış.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makroları belirtmenize olanak veren bir **DISPID** MFC otomatik olarak izin vermek yerine bir atayın. Bu kimlik makrosu ada eklenir dışında bu makroları Gelişmiş aynı ada sahip (örneğin **DISP_PROPERTY_ID**) ve kimliği hemen sonra belirtilen parametresiyle belirlenir *pszName* parametresi. AFXDISP bakın. H Bu makroları hakkında daha fazla bilgi için. **_Id** girişleri gönderme harita sonunda yerleştirilmelidir. Otomatik etkiler **DISPID** nesil aynı olmayan bir şekilde **_ıd** makrosu sürümü gerekir ( **DISPID**s konumu tarafından belirlenir). Örneğin:  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y",
    m_y,
    VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x",
    0x00020003,
    m_x,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC DISPID değerleri için sınıf CDisp3DPoint gibi üretir:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Bir sabit belirtme **DISPID** önceden var olan bir gönderme arabirimi geriye dönük uyumluluğu korumak veya bazı sistem tarafından tanımlanan yöntemler veya özellikler uygulamak için yararlıdır (genellikle bir negatif tarafından gösterilen  **DISPID**, gibi **DISPID_NEWENUM** koleksiyonu).  
  
#### <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Bir COleClientItem IDispatch arabirimi alınıyor  
 OLE sunucu işlevselliğinin yanı sıra bunların belge nesneleri içinde Otomasyon pek çok sunucu destekler. Bu Otomasyon arabirimi erişmek için doğrudan erişim için ise gerekli `COleClientItem::m_lpObject` üye değişkeni. Aşağıdaki kodu alacak `IDispatch` türetilmiş bir nesne için arabirim `COleClientItem`. Bu işlevsellik gerekli bulursanız, aşağıdaki kodu, uygulamanızda içerebilir:  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);

 ASSERT(m_lpObject != NULL);

 
    LPUNKNOWN lpUnk = m_lpObject;  
 
    Run();
*// must be running  
 
    LPOLELINK lpOleLink = NULL;  
    if (m_lpObject->QueryInterface(IID_IOleLink,   
 (LPVOID FAR*)&lpOleLink) == NOERROR)  
 {  
    ASSERT(lpOleLink != NULL);

    lpUnk = NULL;  
    if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)  
 {  
    TRACE0("Warning: Link is not connected!\n");

    lpOleLink->Release();
return NULL;  
 }  
    ASSERT(lpUnk != NULL);

 }  
 
    LPDISPATCH lpDispatch = NULL;  
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
 != NOERROR)  
 {  
    TRACE0("Warning: does not support IDispatch!\n");

    return NULL;  
 }  
 
    ASSERT(lpDispatch != NULL);

    return lpDispatch;  
}  
```  
  
 Gönderme arabirimi döndürülen bu işlev sonra doğrudan kullanılan veya iliştirilmiş bir `COleDispatchDriver` tür kullanımı uyumlu erişim. Doğrudan kullanırsanız, sizi aramasını emin olun, `Release` üyesi olduğunda aracılığıyla işaretçisi ile ( `COleDispatchDriver` yıkıcı olmadığından bu varsayılan olarak).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

