---
title: COleDispatchDriver sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: c0c1fd14105bae3b5413f92b547339ccabf3bb91
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774782"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver sınıfı

OLE Otomasyonu nesnesi etkin tarafını uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchDriver
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Oluşturur bir `COleDispatchDriver` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Bağlanan bir `IDispatch` bağlantı `COleDispatchDriver` nesne.|
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Oluşturur bir `IDispatch` bağlantı ve ekler `COleDispatchDriver` nesne.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Ayırır bir `IDispatch` bunu serbest olmadan bağlantı.|
|[COleDispatchDriver::GetProperty](#getproperty)|Bir Otomasyon özelliği alır.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Otomasyon yöntemleri çağırmak için Yardımcısı.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Yayınları bir `IDispatch` bağlantı.|
|[COleDispatchDriver::SetProperty](#setproperty)|Bir Otomasyon özelliği ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|Kaynak değerin kopyalar `COleDispatchDriver` nesne.|
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Erişen temel `IDispatch` işaretçi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Yayın belirtir `IDispatch` sırasında `ReleaseDispatch` veya nesne yok etme.|
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|İşaretçi gösterir `IDispatch` arabirimi şuna bağlı `COleDispatchDriver`.|

## <a name="remarks"></a>Açıklamalar

`COleDispatchDriver` bir temel sınıfa sahip değil.

OLE dağıtma arabirimleri, bir nesnenin yöntemlere ve özelliklere erişim sağlar. Üye işlevlerinin `COleDispatchDriver` ekleme, ayırma, oluşturma ve gönderme bağlantı türü sürüm `IDispatch`. Diğer üye işlevlerini çağırma basitleştirmek için değişken bağımsız değişken listeleri kullanın. `IDispatch::Invoke`.

Bu sınıf doğrudan kullanılabilir, ancak genellikle yalnızca Sınıf Ekle Sihirbazı tarafından oluşturulan sınıflar tarafından kullanılır. Bir tür kitaplığı içeri aktararak yeni C++ sınıfları oluşturduğunuzda, yeni sınıflar türetilmiş `COleDispatchDriver`.

Kullanma hakkında daha fazla bilgi için `COleDispatchDriver`, aşağıdaki makalelere bakın:

- [Otomasyon İstemcileri](../../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDispatchDriver`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch

Çağrı `AttachDispatch` üye işlevini eklemek için bir `IDispatch` işaretçisine `COleDispatchDriver` nesne. Daha fazla bilgi için [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
OLE işaretçi `IDispatch` ekleneceği nesne `COleDispatchDriver` nesne.

*bAutoRelease*<br/>
Bu nesne kapsam dışına çıktığında yayımlanacak gönderme olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev tüm sürümleri `IDispatch` zaten iliştirilmiş işaretçi `COleDispatchDriver` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver

Oluşturur bir `COleDispatchDriver` nesne.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
OLE işaretçi `IDispatch` ekleneceği nesne `COleDispatchDriver` nesne.

*bAutoRelease*<br/>
Bu nesne kapsam dışına çıktığında yayımlanacak gönderme olup olmadığını belirtir.

*dispatchSrc*<br/>
Mevcut bir başvuru `COleDispatchDriver` nesne.

### <a name="remarks"></a>Açıklamalar

Form `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) bağlanan [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimi.

Form `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) varolan kopyalar `COleDispatchDriver` nesne ve başvuru sayısını artırır.

Form `COleDispatchDriver`oluşturur () bir `COleDispatchDriver` nesnesi ancak bağlanamıyor `IDispatch` arabirimi. Kullanmadan önce `COleDispatchDriver`bağlanma (bağımsız değişkenler olmadan), bir `IDispatch` kullanarak kendisine [COleDispatchDriver::CreateDispatch](#createdispatch) veya [COleDispatchDriver::AttachDispatch](#attachdispatch). Daha fazla bilgi için [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="createdispatch"></a>  COleDispatchDriver::CreateDispatch

Oluşturur bir [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimi nesnesi ve ekler `COleDispatchDriver` nesne.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
Sınıf kimliği `IDispatch` oluşturulacak bağlantı nesnesi.

*pError*<br/>
Oluşturma işleminden kaynaklanan durum kodunu barındıracak bir OLE özel durum nesnesine işaretçi.

*lpszProgID*<br/>
"Excel.Document.5" dağıtım nesnesi oluşturulacak Otomasyon nesnenin gibi programlama tanımlayıcısı, işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch

Geçerli ayırır `IDispatch` bu nesneden bağlantı.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce eklenen OLE işaretçisi `IDispatch` nesne.

### <a name="remarks"></a>Açıklamalar

`IDispatch` Serbest bırakılmaz.

LPDISPATCH türü hakkında daha fazla bilgi için bkz. [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>  COleDispatchDriver::GetProperty

Belirtilen nesne özelliği alır *dwDispID*.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Alınacak özelliği tanımlar.

*vtProp*<br/>
Alınacak alan özelliği belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](#invokehelper).

*pvProp*<br/>
Özellik değeri alacak değişkenin adresi. Tarafından belirtilen tür eşleşmelidir *vtProp*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>  COleDispatchDriver::InvokeHelper

Nesne yöntemi veya özelliği tarafından belirtilen çağırır *dwDispID*, tarafından belirtilen bağlamı *wFlags*.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Yöntem veya özellik çağrılacak tanımlar.

*wFlags*<br/>
Çağrı bağlamını tanımlayan bayraklar `IDispatch::Invoke`. biçimindeki telefon numarasıdır. Olası değerler listesi için bkz. *wFlags* parametresinde [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK.

*vtRet*<br/>
Dönüş değerinin türünü belirtir. Olası değerler için Açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değeri alır veya dönüş değeri değişkenin adresidir. Tarafından belirtilen tür eşleşmelidir *vtRet*.

*pbParamInfo*<br/>
Aşağıdaki parametre türleri belirtme bayt null ile sonlandırılmış bir dize işaretçisi *pbParamInfo*.

*...*<br/>
Belirtilen tür parametrelerinin değişken listesi *pbParamInfo*.

### <a name="remarks"></a>Açıklamalar

*PbParamInfo* parametresi yöntemi veya özelliği için geçirilen parametre türlerini belirtir. Bağımsız değişken listesi tarafından temsil edilen **...**  söz dizimi bildirimi.

Olası değerler için *vtRet* bağımsız değişken VARENUM sabit listesinden alınmış alınır. Olası değerler aşağıdaki gibidir:

|Sembol|Dönüş Türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**TARİH**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**DEĞİŞKEN**|
|VT_UNKNOWN|LPUNKNOWN|

*PbParamInfo* bağımsız değişkeni, boşlukla ayrılmış bir listesi **VTS_** sabitler. Bir veya daha fazla (değil virgüller), boşluk ile ayırarak, bu değerleri işlevin parametre listesi belirtir. Olası değerler ile listelenen [EVENT_CUSTOM](event-maps.md#event_custom) makrosu.

Bu işlev parametreleri VARIANTARG değerlerine dönüştürür ve ardından çağırır [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) yöntemi. Çağrı `Invoke` başarısız olursa, bu işlev bir özel durum oluşturur. ' % S'SCODE (durum kodu) tarafından döndürülen, `IDispatch::Invoke` DISP_E_EXCEPTION, olan bu işlevin bir [COleException](../../mfc/reference/coleexception-class.md) nesne; Aksi takdirde oluşturur bir [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).

Daha fazla bilgi için [VARIANTARG](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke), ve [yapısı, COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK içinde.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease

TRUE ise, COM nesnesi tarafından erişilen [m_lpDispatch](#m_lpdispatch) ne zaman otomatik olarak yayımlanacaktır [ReleaseDispatch](#releasedispatch) adı verilir veya bu `COleDispatchDriver` nesnesi yok edildiğinde.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_bAutoRelease` oluşturucuda TRUE olarak ayarlanır.

COM nesneleri serbest bırakma ile ilgili daha fazla bilgi için bkz: [uygulama başvuru sayımı](/windows/desktop/com/implementing-reference-counting) ve [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch

İşaretçi `IDispatch` arabirimi şuna bağlı `COleDispatchDriver`.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Açıklamalar

`m_lpDispatch` Veri üyesi LPDISPATCH türü genel değişkenidir.

Daha fazla bilgi için [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="operator_eq"></a>  COleDispatchDriver::operator =

Kaynak değerin kopyalar `COleDispatchDriver` nesne.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*dispatchSrc*<br/>
Varolan bir işaretçi `COleDispatchDriver` nesne.

##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH

Erişen temel `IDispatch` işaretçisinin `COleDispatchDriver` nesne.

```
operator LPDISPATCH();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch

Yayınları `IDispatch` bağlantı. Daha fazla bilgi için [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Açıklamalar

Bu bağlantı için otomatik yayın ayarlanmışsa, pencereyi sürüklerken `IDispatch::Release` önce arabirimi yayımladı.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="setproperty"></a>  COleDispatchDriver::SetProperty

Tarafından belirtilen OLE nesne özelliği ayarlar *dwDispID*.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Ayarlanacak özelliği tanımlar.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](#invokehelper).

*...*<br/>
Tek bir parametre tarafından belirtilen türde *vtProp*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[ACDUAL örneği](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
