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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421263"
---
# <a name="coledispatchdriver-class"></a>Cotadispatchdriver sınıfı

OLE otomasyonunun istemci tarafını uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchDriver
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[Cotadispatchdriver:: Cotadispatchdriver](#coledispatchdriver)|`COleDispatchDriver` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[Cotadispatchdriver:: AttachDispatch](#attachdispatch)|`COleDispatchDriver` nesnesine bir `IDispatch` bağlantısı iliştirir.|
|[Cotadispatchdriver:: CreateDispatch](#createdispatch)|`IDispatch` bir bağlantı oluşturur ve `COleDispatchDriver` nesnesine iliştirir.|
|[Cotadispatchdriver::D etachDispatch](#detachdispatch)|`IDispatch` bağlantısını serbest bırakmadan ayırır.|
|[Cotadispatchdriver:: GetProperty](#getproperty)|Bir Automation özelliği alır.|
|[Cotadispatchdriver:: InvokeHelper](#invokehelper)|Otomasyon yöntemlerini çağırma Yardımcısı.|
|[Cotadispatchdriver:: ReleaseDispatch](#releasedispatch)|`IDispatch` bir bağlantı yayınlar.|
|[Cotadispatchdriver:: SetProperty](#setproperty)|Bir Automation özelliği ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Name|Açıklama|
|----------|-----------------|
|[COleDispatchDriver:: operator =](#operator_eq)|Kaynak değeri `COleDispatchDriver` nesnesine kopyalar.|
|[COleDispatchDriver:: operator LPDISPATCH](#operator_lpdispatch)|Temel alınan `IDispatch` işaretçisine erişir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[Colet Dispatchdriver:: m_bAutoRelease](#m_bautorelease)|`ReleaseDispatch` veya nesne yok etme sırasında `IDispatch` serbest bırakılıp başlatılmayacağını belirtir.|
|[Colet Dispatchdriver:: m_lpDispatch](#m_lpdispatch)|Bu `COleDispatchDriver`iliştirilmiş `IDispatch` arabirimine yönelik işaretçiyi gösterir.|

## <a name="remarks"></a>Açıklamalar

`COleDispatchDriver` temel bir sınıfa sahip değil.

OLE dağıtma arabirimleri, bir nesnenin yöntemlerine ve özelliklerine erişim sağlar. `COleDispatchDriver` üye işlevleri `IDispatch`tür bir dağıtım bağlantısını ekler, ayırın, oluşturun ve serbest bırakın. Diğer üye işlevleri `IDispatch::Invoke`çağrılmasını kolaylaştırmak için değişken bağımsız değişken listeleri kullanır.

Bu sınıf doğrudan kullanılabilir, ancak genellikle sınıf ekleme Sihirbazı tarafından oluşturulan sınıflar tarafından kullanılır. Bir tür kitaplığını içeri C++ aktararak yeni sınıflar oluşturduğunuzda, yeni sınıflar `COleDispatchDriver`türetilir.

`COleDispatchDriver`kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Otomasyon İstemcileri](../../mfc/automation-clients.md)

- [Otomasyon Sunucuları](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDispatchDriver`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="attachdispatch"></a>Cotadispatchdriver:: AttachDispatch

`COleDispatchDriver` nesnesine bir `IDispatch` işaretçisi iliştirmek için `AttachDispatch` member işlevini çağırın. Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
`COleDispatchDriver` nesnesine eklenecek OLE `IDispatch` nesnesine yönelik işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına geçtiğinde, gönderimi serbest bırakılacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `COleDispatchDriver` nesnesine zaten eklenmiş olan tüm `IDispatch` işaretçileri yayınlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>Cotadispatchdriver:: Cotadispatchdriver

`COleDispatchDriver` nesnesi oluşturur.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
`COleDispatchDriver` nesnesine eklenecek OLE `IDispatch` nesnesine yönelik işaretçi.

*bAutoRelease*<br/>
Bu nesne kapsam dışına geçtiğinde, gönderimi serbest bırakılacağını belirtir.

*dispatchSrc*<br/>
Mevcut bir `COleDispatchDriver` nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Form `COleDispatchDriver`(`LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **true**), [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimini bağlar.

Form `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) var olan bir `COleDispatchDriver` nesnesini kopyalar ve başvuru sayısını artırır.

Form `COleDispatchDriver`() bir `COleDispatchDriver` nesnesi oluşturur, ancak `IDispatch` arabirimine bağlanamaz. Bağımsız değişkenler olmadan `COleDispatchDriver`() kullanmadan önce, [Cotadispatchdriver:: CreateDispatch](#createdispatch) veya [Cotadispatchdriver:: AttachDispatch](#attachdispatch)kullanarak buna bir `IDispatch` bağlamanız gerekir. Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](#createdispatch)örneğine bakın.

##  <a name="createdispatch"></a>Cotadispatchdriver:: CreateDispatch

Bir [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) arabirimi nesnesi oluşturur ve onu `COleDispatchDriver` nesnesine iliştirir.

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
Oluşturulacak `IDispatch` bağlantı nesnesinin sınıf KIMLIĞI.

*pError*<br/>
Oluşturma işleminden kaynaklanan durum kodunu tutan OLE özel durum nesnesine yönelik işaretçi.

*lpszProgID*<br/>
Dağıtım nesnesinin oluşturulacağı Otomasyon nesnesinin "Excel. Document. 5" gibi programlama tanımlayıcısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>Cotadispatchdriver::D etachDispatch

Geçerli `IDispatch` bağlantısını bu nesneden ayırır.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce eklenmiş OLE `IDispatch` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`IDispatch` serbest bırakıldı.

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
`IDispatch::Invoke`çağrısının bağlamını açıklayan bayraklar. biçimindeki telefon numarasıdır. Olası değerler listesi için, Windows SDK [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) Içindeki *wFlags* parametresine bakın.

*Sanal tret*<br/>
Dönüş değerinin türünü belirtir. Olası değerler için, açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değeri veya dönüş değeri alacak değişkenin adresi. *VtRet*tarafından belirtilen türle eşleşmesi gerekir.

*Pbparaınfo*<br/>
*Pbparaınfo*'dan sonraki parametrelerin türlerini belirten, null ile sonlandırılmış bir bayt dizesi işaretçisi.

*...*<br/>
*Pbparaınfo*içinde belirtilen türlerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*Pbparaınfo* parametresi, yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Bağımsız değişkenlerin değişken listesi, sözdizimi bildiriminde **...** ile temsil edilir.

*VtRet* bağımsız değişkeninin olası DEĞERLERI, VARENUM numaralandırmasından alınır. Olası değerler aşağıdaki gibidir:

|Sembol|Dönüş Türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**Lı**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**VARYANTı**|
|VT_UNKNOWN|LPUNKNOWN|

*Pbparaınfo* bağımsız değişkeni, **VTS_** sabitlerin boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayırarak bu değerlerden bir veya daha fazlası, işlevin parametre listesini belirtir. Olası değerler [event_custom](event-maps.md#event_custom) makrosu ile listelenir.

Bu işlev, parametreleri VARIANTARG değerlerine dönüştürür, sonra [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) metodunu çağırır. `Invoke` çağrısı başarısız olursa, bu işlev bir özel durum oluşturur. `IDispatch::Invoke` tarafından döndürülen SCODE (durum kodu) DISP_E_EXCEPTION, bu işlev bir [Copaexception](../../mfc/reference/coleexception-class.md) nesnesi oluşturur; Aksi takdirde, bir [Cotadispatchexception](../../mfc/reference/coledispatchexception-class.md)oluşturur.

Daha fazla bilgi için, bkz. [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [ıDISPATCH:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)ve [com hata kodlarının yapısını](/windows/win32/com/structure-of-com-error-codes) Windows SDK.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](#createdispatch)örneğine bakın.

##  <a name="m_bautorelease"></a>Colet Dispatchdriver:: m_bAutoRelease

TRUE ise, [ReleaseDispatch](#releasedispatch) çağrıldığında veya bu `COleDispatchDriver` nesnesi yok edildiğinde [M_LPDISPATCH](#m_lpdispatch) tarafından erişilen com nesnesi otomatik olarak serbest bırakılır.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_bAutoRelease` oluşturucuda TRUE olarak ayarlanır.

COM nesnelerini serbest bırakma hakkında daha fazla bilgi için, Windows SDK [başvuru sayma](/windows/win32/com/implementing-reference-counting) ve [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) ' i uygulama bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>Colet Dispatchdriver:: m_lpDispatch

Bu `COleDispatchDriver`iliştirilmiş `IDispatch` arabirimine yönelik işaretçi.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Açıklamalar

`m_lpDispatch` veri üyesi, LPDISPATCH türünde ortak bir değişkendir.

Daha fazla bilgi için Windows SDK [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) bölümüne bakın.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: AttachDispatch](#attachdispatch)örneğine bakın.

##  <a name="operator_eq"></a>COleDispatchDriver:: operator =

Kaynak değeri `COleDispatchDriver` nesnesine kopyalar.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Parametreler

*dispatchSrc*<br/>
Varolan bir `COleDispatchDriver` nesnesine yönelik bir işaretçi.

##  <a name="operator_lpdispatch"></a>COleDispatchDriver:: operator LPDISPATCH

`COleDispatchDriver` nesnesinin temeldeki `IDispatch` işaretçisine erişir.

```
operator LPDISPATCH();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>Cotadispatchdriver:: ReleaseDispatch

`IDispatch` bağlantısını serbest bırakır. Daha fazla bilgi için bkz [. IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Açıklamalar

Bu bağlantı için otomatik sürüm ayarlandıysa, bu işlev arabirimi bırakmadan önce `IDispatch::Release` çağırır.

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
