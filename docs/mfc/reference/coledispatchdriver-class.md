---
title: COleDispatchDriver Sınıfı
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
ms.openlocfilehash: c22097c3a686857a6a5698033b7395c5d15f2570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366076"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver Sınıfı

OLE otomasyonunun istemci tarafını uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchDriver
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Bir `COleDispatchDriver` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|`COleDispatchDriver` Nesneye bağlantı `IDispatch` bağlar.|
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Bir `IDispatch` bağlantı oluşturur ve `COleDispatchDriver` nesneye bağlar.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Bir `IDispatch` bağlantıyı serbest bırakmadan ayırır.|
|[COleDispatchDriver::GetProperty](#getproperty)|Bir otomasyon özelliği alır.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Otomasyon yöntemlerini arama da yardımcı.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Bir `IDispatch` bağlantı bırakır.|
|[COleDispatchDriver::SetProperty](#setproperty)|Bir otomasyon özelliği ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|Kaynak değerini `COleDispatchDriver` nesneye kopyalar.|
|[COleDispatchDriver::operatör LPDISPATCH](#operator_lpdispatch)|Temel `IDispatch` işaretçiye erişir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|`IDispatch` Sırasında `ReleaseDispatch` veya nesne imha serbest bırakmak için olup olmadığını belirtir.|
|[COleDispatchSürücü::m_lpDispatch](#m_lpdispatch)|Buna `IDispatch` `COleDispatchDriver`bağlı arabirimin işaretçisini gösterir.|

## <a name="remarks"></a>Açıklamalar

`COleDispatchDriver`taban sınıfa sahip değildir.

OLE gönderiaraları, nesnenin yöntemlerine ve özelliklerine erişim sağlar. Tür `IDispatch`bir `COleDispatchDriver` gönderme bağlantısı ekleme, ayırma, oluşturma ve serbest bırakma nın üye işlevleri. Diğer üye işlevler aramayı `IDispatch::Invoke`kolaylaştırmak için değişken bağımsız değişken listeleri kullanır.

Bu sınıf doğrudan kullanılabilir, ancak genellikle yalnızca Sınıf Ekle sihirbazı tarafından oluşturulan sınıflar tarafından kullanılır. Bir tür kitaplığı alarak yeni C++ sınıfları oluşturduğunuzda, yeni `COleDispatchDriver`sınıflar.

Kullanma `COleDispatchDriver`hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Otomasyon Müşterileri](../../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDispatchDriver`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="coledispatchdriverattachdispatch"></a><a name="attachdispatch"></a>COleDispatchDriver::AttachDispatch

Nesneye `AttachDispatch` işaretçi `IDispatch` eklemek için üye işlevi arayın. `COleDispatchDriver` Daha fazla bilgi için Bkz. [IDispatch Arabirimi Uygulama.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Nesneye eklenecek `IDispatch` bir OLE nesnesine `COleDispatchDriver` işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına çıktığında gönderiyi serbest bırakıp bırakmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `IDispatch` nesneye zaten bağlı `COleDispatchDriver` olan herhangi bir işaretçiyi serbest bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

## <a name="coledispatchdrivercoledispatchdriver"></a><a name="coledispatchdriver"></a>COleDispatchDriver::COleDispatchDriver

Bir `COleDispatchDriver` nesne inşa eder.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Nesneye eklenecek `IDispatch` bir OLE nesnesine `COleDispatchDriver` işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına çıktığında gönderiyi serbest bırakıp bırakmayacağını belirtir.

*sevkSrc*<br/>
Varolan `COleDispatchDriver` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Form `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimini bağlar.

`COleDispatchDriver`Form ( **const**`COleDispatchDriver`& `dispatchSrc`) varolan `COleDispatchDriver` bir nesneyi kopyalar ve başvuru sayısını oluşturur.

Form `COleDispatchDriver`( ) bir `COleDispatchDriver` nesne oluşturur, `IDispatch` ancak arabirimi bağlamaz. Kullanmadan `COleDispatchDriver`önce ( ) bağımsız `IDispatch` değişkenler olmadan, [coleDispatchDriver kullanarak](#createdispatch) bir bağlamanız gerekir::CreateDispatch veya [COleDispatchDriver::AttachDispatch](#attachdispatch). Daha fazla bilgi için Bkz. [IDispatch Arabirimi Uygulama.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](#createdispatch).

## <a name="coledispatchdrivercreatedispatch"></a><a name="createdispatch"></a>COleDispatchDriver::CreateDispatch

[Bir IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirim nesnesi oluşturur `COleDispatchDriver` ve nesneye bağlar.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Oluşturulacak bağlantı `IDispatch` nesnesinin sınıf kimliği.

*pHata*<br/>
Oluşturmadan kaynaklanan durum kodunu tutacak bir OLE özel durum nesnesine işaretçi.

*lpszProgID*<br/>
Gönderme nesnesinin oluşturulacak otomasyon nesnesinin "Excel.Document.5" gibi programlı tanımlayıcısını işaretle.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

## <a name="coledispatchdriverdetachdispatch"></a><a name="detachdispatch"></a>COleDispatchDriver::DetachDispatch

Geçerli `IDispatch` bağlantıyı bu nesneden ayırır.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce eklenmiş OLE `IDispatch` nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Serbest `IDispatch` bırakılmadı.

LPDISPATCH türü hakkında daha fazla bilgi için Windows SDK'da [IDispatch Arabirimi Uygulama'ya](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

## <a name="coledispatchdrivergetproperty"></a><a name="getproperty"></a>COleDispatchDriver::GetProperty

*dwDispID*tarafından belirtilen nesne özelliğini alır.

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
Alınacak özelliği belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](#invokehelper).

*pvProp*<br/>
Özellik değerini alacak değişkenin adresi. *VtProp*tarafından belirtilen türe uygun olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

## <a name="coledispatchdriverinvokehelper"></a><a name="invokehelper"></a>COleDispatchDriver::InvokeHelper

WFlags tarafından belirtilen *bağlamda, dwDispID*tarafından belirtilen *wFlags*nesne yöntemi veya özelliği çağırır.

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
Çağrılacak yöntemi veya özelliği tanımlar.

*wFlags*<br/>
Çağrının bağlamını açıklayan `IDispatch::Invoke`bayraklar. . Olası değerlerin listesi [için, IDispatch'teki](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) *wFlags* parametresi::Windows SDK'da çağırın.

*vtRet*<br/>
İade değerinin türünü belirtir. Olası değerler için Açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değerini veya iade değerini alacak değişkenin adresi. *VtRet*tarafından belirtilen türe uygun olmalıdır.

*pbParamInfo*<br/>
*PbParamInfo'yu*izleyen parametrelerin türlerini belirten null-sonlandırılan bayt dizesini işaretçi.

*...*<br/>
*PbParamInfo'da*belirtilen türparametrelerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*pbParamInfo* parametresi yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Bağımsız değişken bağımsız değişken listesi sözdizimi bildiriminde **...** tarafından temsil edilir.

*vtRet* bağımsız değişkeni için olası değerler VARENUM numaralandırmasından alınır. Olası değerler aşağıdaki gibidir:

|Sembol|Dönüş Türü|
|------------|-----------------|
|Vt_empty|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|Vt_cy|**CY**|
|Vt_date|**Tarih**|
|Vt_bstr|Bstr|
|Vt_dıspatch|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**Bool**|
|VT_VARIANT|**VARIANT**|
|Vt_unknown|LPUNKNOWN|

*pbParamInfo* bağımsız **değişkeni, VTS_** sabitlerinin boşluktan ayrılmış bir listesidir. Boşluklara (virgülle değil) ayrılan bu değerlerden biri veya birkaçı, işlevin parametre listesini belirtir. Olası değerler [EVENT_CUSTOM](event-maps.md#event_custom) makrosuyla listelenir.

Bu işlev parametreleri VARIANTARG değerlerine dönüştürür, ardından [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) yöntemini çağırır. Çağrı `Invoke` başarısız olursa, bu işlev bir özel durum atar. Döndürülen `IDispatch::Invoke` SCODE (durum kodu) DISP_E_EXCEPTION ise, bu işlev bir [COleException](../../mfc/reference/coleexception-class.md) nesnesi atar; aksi takdirde bir [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)atar.

Daha fazla bilgi için, bkz [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [IDispatch Arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke), ve Windows SDK [COM Hata Kodları Yapısı.](/windows/win32/com/structure-of-com-error-codes)

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](#createdispatch).

## <a name="coledispatchdriverm_bautorelease"></a><a name="m_bautorelease"></a>COleDispatchDriver::m_bAutoRelease

TRUE ise, [m_lpDispatch](#m_lpdispatch) tarafından erişilen COM nesnesi, [ReleaseDispatch](#releasedispatch) `COleDispatchDriver` çağrıldığında veya bu nesne yok edildiğinde otomatik olarak serbest bırakılır.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_bAutoRelease` oluşturucu da TRUE olarak ayarlanır.

COM nesnelerinin serbest bırakılması hakkında daha fazla bilgi için bkz: [Başvuru Sayımı](/windows/win32/com/implementing-reference-counting) ve [IUnknown uygulama::Windows](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) SDK'da yayınlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

## <a name="coledispatchdriverm_lpdispatch"></a><a name="m_lpdispatch"></a>COleDispatchSürücü::m_lpDispatch

Buna bağlı `IDispatch` arabirimin `COleDispatchDriver`işaretçisi.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Açıklamalar

Veri `m_lpDispatch` üyesi, LPDISPATCH türünde ortak bir değişkendir.

Daha fazla bilgi için Windows SDK'daki [IDispatch'e](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) bakın.

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:AttachDispatch](#attachdispatch).

## <a name="coledispatchdriveroperator-"></a><a name="operator_eq"></a>COleDispatchDriver::operator =

Kaynak değerini `COleDispatchDriver` nesneye kopyalar.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*sevkSrc*<br/>
Varolan `COleDispatchDriver` bir nesneye işaretçi.

## <a name="coledispatchdriveroperator-lpdispatch"></a><a name="operator_lpdispatch"></a>COleDispatchDriver::operatör LPDISPATCH

Nesnenin alttaki `IDispatch` işaretçisi `COleDispatchDriver` erişer.

```
operator LPDISPATCH();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

## <a name="coledispatchdriverreleasedispatch"></a><a name="releasedispatch"></a>COleDispatchDriver::ReleaseDispatch

`IDispatch` Bağlantıyı serbest bırakır. Daha fazla bilgi için [Bkz. IDispatch Arabirimi Uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Açıklamalar

Bu bağlantı için otomatik sürüm ayarlanmışsa, bu işlev arabirimi serbest bırakmadan önce çağırır. `IDispatch::Release`

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:AttachDispatch](#attachdispatch).

## <a name="coledispatchdriversetproperty"></a><a name="setproperty"></a>COleDispatchDriver::SetProperty

*DwDispID*tarafından belirtilen OLE nesne özelliğini ayarlar.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Ayarlanacak özelliği tanımlar.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](#invokehelper).

*...*<br/>
*vtProp*tarafından belirtilen türün tek bir parametresi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
