---
title: COleDispatchDriver sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57f9eaa33abd0f24a1d584c5ba2a1e4d6f9e5d44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver sınıfı
OLE Otomasyon istemci tarafı uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDispatchDriver  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Oluşturan bir `COleDispatchDriver` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Bağlayan bir `IDispatch` bağlantı `COleDispatchDriver` nesnesi.|  
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Oluşturur bir `IDispatch` bağlantı ve ekler `COleDispatchDriver` nesnesi.|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Ayırır bir `IDispatch` serbest olmadan bağlantı.|  
|[COleDispatchDriver::GetProperty](#getproperty)|Bir Otomasyon özelliğini alır.|  
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Otomasyon yöntemleri çağırma Yardımcısı.|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Sürümler bir `IDispatch` bağlantı.|  
|[COleDispatchDriver::SetProperty](#setproperty)|Bir Otomasyon özelliğini ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|Kaynak değerin kopyalar `COleDispatchDriver` nesnesi.|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Erişen temel `IDispatch` işaretçi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Yayın belirtir `IDispatch` sırasında `ReleaseDispatch` veya nesne yok.|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|İşaretçi gösterir `IDispatch` arabirimi için bağlı `COleDispatchDriver`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleDispatchDriver` bir taban sınıfı yok.  
  
 OLE gönderme arabirimleri nesnenin yöntemlere ve özelliklere erişim sağlar. Üye işlevlerini `COleDispatchDriver` ekleme, detach, oluşturma ve gönderme bağlantı türü sürüm `IDispatch`. Diğer üye işlevlerini çağırma basitleştirmek için değişken bağımsız değişken listeleri kullanma **IDispatch::Invoke**.  
  
 Bu sınıf doğrudan kullanılabilir, ancak genelde yalnızca sınıfı Ekle Sihirbazı tarafından oluşturulan sınıflar tarafından kullanılır. Tür kitaplığı içeri aktararak yeni C++ sınıfları oluşturduğunuzda, yeni sınıflar türetilmiş `COleDispatchDriver`.  
  
 Kullanma hakkında daha fazla bilgi için `COleDispatchDriver`, aşağıdaki makalelere bakın:  
  
- [Otomasyon İstemcileri](../../mfc/automation-clients.md)  
  
- [Otomasyon Sunucuları](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch  
 Çağrı `AttachDispatch` üye işlevi ekleme bir `IDispatch` işaretçi `COleDispatchDriver` nesnesi. Daha fazla bilgi için bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDispatch`  
 İşaretçi bir OLE `IDispatch` eklenmesi için nesne `COleDispatchDriver` nesne.  
  
 `bAutoRelease`  
 Bu nesne kapsam dışına çıktığında yayımlanacak gönderme olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev herhangi serbest `IDispatch` zaten eklenmiş. işaretçi `COleDispatchDriver` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]  
  
##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver  
 Oluşturan bir `COleDispatchDriver` nesnesi.  
  
```  
COleDispatchDriver();  
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);  
  COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDispatch`  
 İşaretçi bir OLE `IDispatch` eklenmesi için nesne `COleDispatchDriver` nesne.  
  
 `bAutoRelease`  
 Bu nesne kapsam dışına çıktığında yayımlanacak gönderme olup olmadığını belirtir.  
  
 `dispatchSrc`  
 Başvuru mevcut bir `COleDispatchDriver` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Formun `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) bağlanan [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) arabirimi.  
  
 Formun `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) var olan kopyalar `COleDispatchDriver` nesne ve başvuru sayısını artırır.  
  
 Formun `COleDispatchDriver`() oluşturur bir `COleDispatchDriver` nesne ancak bağlanamıyor `IDispatch` arabirimi. Kullanmadan önce `COleDispatchDriver`bağlanma (bağımsız değişkenler olmadan), bir `IDispatch` kullanarak ona [COleDispatchDriver::CreateDispatch](#createdispatch) veya [COleDispatchDriver::AttachDispatch](#attachdispatch). Daha fazla bilgi için bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](#createdispatch).  
  
##  <a name="createdispatch"></a>  COleDispatchDriver::CreateDispatch  
 Oluşturur bir [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) arabirimi nesnesi ve ekleninceye `COleDispatchDriver` nesnesi.  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Sınıf kimliği `IDispatch` oluşturulacak bağlantı nesnesi.  
  
 `pError`  
 İşaretçi oluşturulması kaynaklanan durum kodu tutacak bir OLE özel durum nesnesi.  
  
 `lpszProgID`  
 İşaretçi "Excel.Document.5" dağıtım nesnesi oluşturulacak Otomasyon nesnenin gibi programlama tanımlayıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch  
 Geçerli ayırır `IDispatch` bu nesneden bağlantı.  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce eklenen OLE gösteren bir işaretçi `IDispatch` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `IDispatch` Serbest bırakılmaz.  
  
 Hakkında daha fazla bilgi için `LPDISPATCH` yazın, bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="getproperty"></a>  COleDispatchDriver::GetProperty  
 Belirtilen nesne özelliği alır `dwDispID`.  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Alınacak özelliği tanımlar.  
  
 `vtProp`  
 Alınacak özellik belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](#invokehelper).  
  
 `pvProp`  
 Özellik değeri alacak değişkeni adresidir. Tarafından belirtilen tür eşleşmelidir `vtProp`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="invokehelper"></a>  COleDispatchDriver::InvokeHelper  
 Nesne yöntemi veya özelliği tarafından belirtilen çağırır `dwDispID`, tarafından belirtilen bağlamda `wFlags`.  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Yöntemi veya özelliği çağrılacak tanımlar.  
  
 `wFlags`  
 Çağrı bağlamında açıklayan bayrakları **IDispatch::Invoke**. biçimindeki telefon numarasıdır. Olası değerler listesi için bkz: `wFlags` parametresinde [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) Windows SDK'sındaki.  
  
 `vtRet`  
 Dönüş değeri türünü belirtir. Olası değerler için Açıklamalar bölümüne bakın.  
  
 `pvRet`  
 Özellik değeri alır veya dönüş değeri değişken adresidir. Tarafından belirtilen tür eşleşmelidir `vtRet`.  
  
 `pbParamInfo`  
 Aşağıdaki parametre türlerini belirtme bayt null ile sonlandırılmış dizeye işaretçi `pbParamInfo`.  
  
 *...*  
 Belirtilen türlerinin parametrelerin değişken listesi `pbParamInfo`.  
  
### <a name="remarks"></a>Açıklamalar  
 `pbParamInfo` Parametresi, yöntemi veya özelliği için geçirilen parametre türlerini belirtir. Bağımsız değişken listesi tarafından temsil edilen **...**  sözdizimi bildirimi.  
  
 Olası değerler için `vtRet` bağımsız değişkeni gerçekleştirilecek `VARENUM` numaralandırması. Olası değerler aşağıdaki gibidir:  
  
|Simgesi|Dönüş Türü|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**TARİH**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**DEĞİŞKEN**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `pbParamInfo` Değişken değeri boşlukla ayrılmış bir listesini **VTS_** sabitleri. Bir veya daha fazla (değil virgüller), boşlukla ayrılmış bu değerleri işlev parametre listesi belirtir. Olası değerler ile listelenen [EVENT_CUSTOM](event-maps.md#event_custom) makrosu.  
  
 Bu işlev parametreleri dönüştürür **VARIANTARG** değerleri sonra çağırır [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) yöntemi. Varsa çağrısı `Invoke` başarısız olursa, bu işlev throw bir özel durum. Varsa `SCODE` (durum kodu) tarafından döndürülen **IDispatch::Invoke** olan `DISP_E_EXCEPTION`, bu işlev oluşturur bir [COleException](../../mfc/reference/coleexception-class.md) ; Aksi takdirde oluşturur nesnesi bir [ COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
 Daha fazla bilgi için bkz: [VARIANTARG](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [IDispatch arabirimi uygulama](http://msdn.microsoft.com/library/windows/desktop/ms221037\(v=vs.85\).aspx), [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx), ve [yapısı, COM hata kodları](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](#createdispatch).  
  
##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease  
 Varsa **TRUE**, tarafından erişilen COM nesnesi [m_lpDispatch](#m_lpdispatch) ne zaman otomatik olarak yayımlanır [ReleaseDispatch](#releasedispatch) adı verilir veya bu `COleDispatchDriver` nesnesi yok.  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `m_bAutoRelease` ayarlanır **TRUE** oluşturucuda.  
  
 COM nesneleri serbest bırakma hakkında daha fazla bilgi için bkz: [uygulama başvuru sayımı](http://msdn.microsoft.com/library/windows/desktop/ms693431) ve [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch  
 İşaretçi `IDispatch` arabirimi için bağlı `COleDispatchDriver`.  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_lpDispatch` Veri üyesi olan bir ortak değişken türü `LPDISPATCH`.  
  
 Daha fazla bilgi için bkz: [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="operator_eq"></a>  COleDispatchDriver::operator =  
 Kaynak değerin kopyalar `COleDispatchDriver` nesnesi.  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `dispatchSrc`  
 Var olan bir işaretçi `COleDispatchDriver` nesnesi.  
  
##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH  
 Erişen temel `IDispatch` işaretçisi `COleDispatchDriver` nesnesi.  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch  
 Sürümler `IDispatch` bağlantı. Daha fazla bilgi için bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bağlantı için otomatik bırakma ayarlanmışsa, bu işlevi çağırır **IDispatch::Release** arabirimi serbest önce.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="setproperty"></a>  COleDispatchDriver::SetProperty  
 OLE nesne özelliği tarafından belirtilen ayarlar `dwDispID`.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Ayarlanacak özelliği tanımlar.  
  
 `vtProp`  
 Ayarlanacak özelliği türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](#invokehelper).  
  
 *...*  
 Tek bir parametre tarafından belirtilen türde `vtProp`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [MFC örnek ACDUAL](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
