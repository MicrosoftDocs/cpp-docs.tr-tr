---
title: Cotadispatchdriver sınıfı
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
ms.openlocfilehash: fa88147b57b0506f7f9ab96d4a5d2f43fdd75458
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504176"
---
# <a name="coledispatchdriver-class"></a>Cotadispatchdriver sınıfı

OLE otomasyonunun istemci tarafını uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchDriver
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotadispatchdriver:: Cotadispatchdriver](#coledispatchdriver)|Bir `COleDispatchDriver` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadispatchdriver:: AttachDispatch](#attachdispatch)|`COleDispatchDriver` Nesnesine bir `IDispatch` bağlantı ekler.|
|[Cotadispatchdriver:: CreateDispatch](#createdispatch)|Bir `IDispatch` bağlantı oluşturur ve `COleDispatchDriver` nesneye iliştirir.|
|[Cotadispatchdriver::D etachDispatch](#detachdispatch)|Bağlantıyı serbest `IDispatch` bırakmadan bir bağlantıyı ayırır.|
|[Cotadispatchdriver:: GetProperty](#getproperty)|Bir Automation özelliği alır.|
|[Cotadispatchdriver:: InvokeHelper](#invokehelper)|Otomasyon yöntemlerini çağırma Yardımcısı.|
|[Cotadispatchdriver:: ReleaseDispatch](#releasedispatch)|Bir `IDispatch` bağlantı yayınlar.|
|[Cotadispatchdriver:: SetProperty](#setproperty)|Bir Automation özelliği ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchDriver:: operator =](#operator_eq)|Kaynak değerini `COleDispatchDriver` nesnesine kopyalar.|
|[COleDispatchDriver:: operator LPDISPATCH](#operator_lpdispatch)|Temel `IDispatch` işaretçiye erişir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet Dispatchdriver:: m_bAutoRelease](#m_bautorelease)|Veya nesne yok etme `IDispatch` sırasında `ReleaseDispatch` serbest bırakılıp başlatılmayacağını belirtir.|
|[Colet Dispatchdriver:: m_lpDispatch](#m_lpdispatch)|`IDispatch` Buna`COleDispatchDriver`eklenen arabirime yönelik işaretçiyi gösterir.|

## <a name="remarks"></a>Açıklamalar

`COleDispatchDriver`taban sınıfına sahip değildir.

OLE dağıtma arabirimleri, bir nesnenin yöntemlerine ve özelliklerine erişim sağlar. Bir dağıtım bağlantısı `COleDispatchDriver` `IDispatch`eklemek, ayırmak, oluşturmak ve serbest bırakmak için üye işlevleri. Diğer üye işlevleri, çağırma `IDispatch::Invoke`işlemini basitleştirmek için değişken bağımsız değişken listeleri kullanır.

Bu sınıf doğrudan kullanılabilir, ancak genellikle sınıf ekleme Sihirbazı tarafından oluşturulan sınıflar tarafından kullanılır. Bir tür kitaplığını içeri C++ aktararak yeni sınıflar oluşturduğunuzda, yeni sınıflar öğesinden `COleDispatchDriver`türetilir.

Kullanma `COleDispatchDriver`hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Otomasyon İstemcileri](../../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDispatchDriver`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="attachdispatch"></a>Cotadispatchdriver:: AttachDispatch

Nesneyebir`COleDispatchDriver` `AttachDispatch` `IDispatch` işaretçi iliştirmek için üye işlevini çağırın. Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
`COleDispatchDriver` Nesneye eklenecek OLE `IDispatch` nesnesine yönelik işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına geçtiğinde, gönderimi serbest bırakılacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `COleDispatchDriver` nesnesine `IDispatch` zaten eklenmiş olan herhangi bir işaretçiyi yayınlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>Cotadispatchdriver:: Cotadispatchdriver

Bir `COleDispatchDriver` nesnesi oluşturur.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
`COleDispatchDriver` Nesneye eklenecek OLE `IDispatch` nesnesine yönelik işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına geçtiğinde, gönderimi serbest bırakılacağını belirtir.

*dispatchSrc*<br/>
Varolan `COleDispatchDriver` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Form `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **bool** [](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)true) IDispatch arabirimini bağlar.`bAutoRelease` = 

`COleDispatchDriver`Form ( **const**`COleDispatchDriver`& ), varolan`COleDispatchDriver` bir nesneyi kopyalar ve başvuru sayısını artırır.`dispatchSrc`

Form `COleDispatchDriver`() bir `COleDispatchDriver` nesne oluşturur, `IDispatch` ancak arabirimi bağlanamaz. Bağımsız değişkenler olmadan `IDispatch` ()kullanmadanönce,cotadispatchdriver::CreateDispatchveyacotadispatchdriver::AttachDispatchkullanarakbir`COleDispatchDriver`öğesine bağlamanız gerekir. [](#createdispatch) [](#attachdispatch) Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](#createdispatch)örneğine bakın.

##  <a name="createdispatch"></a>Cotadispatchdriver:: CreateDispatch

Bir [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimi nesnesi oluşturur ve `COleDispatchDriver` nesneye ekler.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Oluşturulacak `IDispatch` bağlantı nesnesinin sınıf kimliği.

*pError*<br/>
Oluşturma işleminden kaynaklanan durum kodunu tutan OLE özel durum nesnesine yönelik işaretçi.

*lpszProgID*<br/>
Dağıtım nesnesinin oluşturulacağı Otomasyon nesnesinin "Excel. Document. 5" gibi programlama tanımlayıcısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>Cotadispatchdriver::D etachDispatch

Geçerli `IDispatch` bağlantıyı bu nesneden ayırır.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce eklenmiş OLE `IDispatch` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`IDispatch` Serbest bırakıldı.

LPDISPATCH türü hakkında daha fazla bilgi için, bkz. Windows SDK [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>Cotadispatchdriver:: GetProperty

*Dwdıspıd*tarafından belirtilen nesne özelliğini alır.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Alınacak özelliği tanımlar.

*vtProp*<br/>
Alınacak özelliği belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](#invokehelper)için açıklamalar bölümüne bakın.

*pvProp*<br/>
Özellik değerini alacak değişkenin adresi. Bu, *vtProp*tarafından belirtilen türle eşleşmelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>Cotadispatchdriver:: InvokeHelper

*WFlags*tarafından belirtilen bağlamda *dwdıspıd*tarafından belirtilen nesne yöntemini veya özelliği çağırır.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Çağrılacak yöntemi veya özelliği tanımlar.

*wFlags*<br/>
Çağrısının bağlamını açıklayan bayraklar `IDispatch::Invoke`. biçimindeki telefon numarasıdır. Olası değerler listesi için, Windows SDK [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) Içindeki *wFlags* parametresine bakın.

*Sanal tret*<br/>
Dönüş değerinin türünü belirtir. Olası değerler için, açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değeri veya dönüş değeri alacak değişkenin adresi. *VtRet*tarafından belirtilen türle eşleşmesi gerekir.

*Pbparaınfo*<br/>
*Pbparaınfo*'dan sonraki parametrelerin türlerini belirten, null ile sonlandırılmış bir bayt dizesi işaretçisi.

*...*<br/>
*Pbparaınfo*içinde belirtilen türlerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*Pbparaınfo* parametresi, yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Bağımsız değişken listesi tarafından temsil edilen **...** söz dizimi bildirimi.

*VtRet* bağımsız değişkeninin olası DEĞERLERI, VARENUM numaralandırmasından alınır. Olası değerler aşağıdaki gibidir:

|Sembol|Dönüş Türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**LI**|
|VT_DATE|**GÜNCEL**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**VARYANTI**|
|VT_UNKNOWN|LPUNKNOWN|

*PbParamInfo* bağımsız değişkeni, **VTS_** sabitleri boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayırarak bu değerlerden bir veya daha fazlası, işlevin parametre listesini belirtir. Olası değerler [event_custom](event-maps.md#event_custom) makrosu ile listelenir.

Bu işlev, parametreleri VARIANTARG değerlerine dönüştürür, sonra [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) metodunu çağırır. Çağrısı `Invoke` başarısız olursa, bu işlev bir özel durum oluşturur. Tarafından `IDispatch::Invoke` döndürülen SCODE (durum kodu) DISP_E_EXCEPTION ise, bu işlev bir [copaexception](../../mfc/reference/coleexception-class.md) nesnesi oluşturur; Aksi takdirde [copadispatchexception](../../mfc/reference/coledispatchexception-class.md)oluşturur.

Daha fazla bilgi için, bkz. [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [ıDISPATCH:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)ve [com hata kodlarının yapısını](/windows/win32/com/structure-of-com-error-codes) Windows SDK.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](#createdispatch)örneğine bakın.

##  <a name="m_bautorelease"></a>Colet Dispatchdriver:: m_bAutoRelease

TRUE ise, [ReleaseDispatch](#releasedispatch) çağrıldığında veya bu `COleDispatchDriver` nesne yok edildiğinde [m_lpDispatch](#m_lpdispatch) tarafından erişilen com nesnesi otomatik olarak serbest bırakılır.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_bAutoRelease` oluşturucuda true olarak ayarlanır.

COM nesnelerini serbest bırakma hakkında daha fazla bilgi için, Windows SDK [başvuru sayma](/windows/win32/com/implementing-reference-counting) ve [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) ' i uygulama bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>Colet Dispatchdriver:: m_lpDispatch

`IDispatch` Buna`COleDispatchDriver`eklenen arabirime yönelik işaretçi.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Açıklamalar

`m_lpDispatch` Veri üyesi, lpDispatch türünde ortak bir değişkendir.

Daha fazla bilgi için Windows SDK [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) bölümüne bakın.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: AttachDispatch](#attachdispatch)örneğine bakın.

##  <a name="operator_eq"></a>COleDispatchDriver:: operator =

Kaynak değerini `COleDispatchDriver` nesnesine kopyalar.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*dispatchSrc*<br/>
Varolan `COleDispatchDriver` bir nesneye yönelik bir işaretçi.

##  <a name="operator_lpdispatch"></a>COleDispatchDriver:: operator LPDISPATCH

`COleDispatchDriver` Nesnenin temel `IDispatch` işaretçisine erişir.

```
operator LPDISPATCH();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>Cotadispatchdriver:: ReleaseDispatch

`IDispatch` Bağlantıyı serbest bırakır. Daha fazla bilgi için bkz [. IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Açıklamalar

Bu bağlantı için otomatik sürüm ayarlandıysa, bu işlev arabirimi serbest bırakmadan önce `IDispatch::Release` çağırır.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: AttachDispatch](#attachdispatch)örneğine bakın.

##  <a name="setproperty"></a>Cotadispatchdriver:: SetProperty

*Dwdıspıd*tarafından belirtilen OLE nesnesi özelliğini ayarlar.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Ayarlanacak özelliği tanımlar.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](#invokehelper)için açıklamalar bölümüne bakın.

*...*<br/>
*VtProp*tarafından belirtilen türde tek bir parametre.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
