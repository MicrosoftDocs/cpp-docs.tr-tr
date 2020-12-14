---
description: 'Daha fazla bilgi edinin: OLE denetimlerini kaydetme'
title: OLE Denetimlerini Kaydetme
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 2556d67e509f7c4217a726ed097bbb69788af7fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218933"
---
# <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

Diğer OLE sunucusu nesneleri gibi OLE denetimlerine diğer OLE kullanan uygulamalar erişebilir. Bu, denetimin tür kitaplığı ve sınıfı kaydedilerek elde edilir.

Aşağıdaki işlevler, Windows kayıt veritabanına denetimin sınıfını, özellik sayfalarını ve tür kitaplığını eklemenize ve kaldırmanıza olanak tanır:

### <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

|Ad|Açıklama|
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Kayıt veritabanına denetimin sınıfını ekler.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Kayıt veritabanına bir denetim özelliği sayfası ekler.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Denetimin tür kitaplığını kayıt veritabanına ekler.|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Kayıt veritabanından bir denetim sınıfını veya özellik sayfası sınıfını kaldırır.|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Kayıt veritabanından denetimin tür kitaplığını kaldırır.|

`AfxOleRegisterTypeLib` genellikle bir denetim DLL 'inin uygulamasında çağırılır `DllRegisterServer` . Benzer şekilde, `AfxOleUnregisterTypeLib` tarafından çağrılır `DllUnregisterServer` . `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass` ve `AfxOleUnregisterClass` genellikle `UpdateRegistry` bir denetimin sınıf fabrikası veya özellik sayfasının üye işlevi tarafından çağırılır.

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a> AfxOleRegisterControlClass

Denetim sınıfını Windows kayıt veritabanına kaydeder.

```
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,
    REFCLSID clsid,
    LPCTSTR pszProgID,
    UINT idTypeName,
    UINT idBitmap,
    int nRegFlags,
    DWORD dwMiscStatus,
    REFGUID tlid,
    WORD wVerMajor,
    WORD wVerMinor);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Denetim sınıfıyla ilişkili modülün örnek tanıtıcısı.

*in*<br/>
Denetimin benzersiz sınıf KIMLIĞI.

*Pszprogıd*<br/>
Denetimin benzersiz program KIMLIĞI.

*ıdtypename*<br/>
Denetim için Kullanıcı tarafından okunabilen bir tür adı içeren dizenin kaynak KIMLIĞI.

*ıdbit eşlem*<br/>
Bir araç çubuğunda veya paletteki OLE denetimini temsil etmek için kullanılan bit eşlemin kaynak KIMLIĞI.

*nRegFlags*<br/>
Aşağıdaki bayraklardan birini veya daha fazlasını içerir:

- `afxRegInsertable` OLE nesneleri için nesne Ekle iletişim kutusunda denetimin görünmesine izin verir.

- `afxRegApartmentThreading` Kayıt defterindeki iş parçacığı modelini ThreadingModel = Apartment olarak ayarlar.

- `afxRegFreeThreading` Kayıt defterindeki iş parçacığı modelini ThreadingModel = ücretsiz olarak ayarlar.

   İki bayrağı birleştirebilir `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel = both olarak ayarlayabilirsiniz. İş parçacığı modeli kaydı hakkında daha fazla bilgi için Windows SDK [ınprocserver32](/windows/win32/com/inprocserver32) bakın.

> [!NOTE]
> MFC 4,2 ' den önceki MFC sürümlerinde **`int`** *nregflags* parametresi, denetimin nesne Ekle iletişim kutusundan eklenmesine izin verilen veya ızın verilmeyen bir bool parametresidir ( *binsertable*).

*dwMiscStatus*<br/>
Aşağıdaki durum bayraklarından birini veya daha fazlasını içerir (bayrakların açıklaması için, bkz. Windows SDK OLEMISC Enumeration):

- OLEMISC_RECOMPOSEONRESIZE

- OLEMISC_ONLYICONIC

- OLEMISC_INSERTNOTREPLACE

- OLEMISC_STATIC

- OLEMISC_CANTLINKINSIDE

- OLEMISC_CANLINKBYOLE1

- OLEMISC_ISLINKOBJECT

- OLEMISC_INSIDEOUT

- OLEMISC_ACTIVATEWHENVISIBLE

- OLEMISC_RENDERINGISDEVICEINDEPENDENT

- OLEMISC_INVISIBLEATRUNTIME

- OLEMISC_ALWAYSRUN

- OLEMISC_ACTSLIKEBUTTON

- OLEMISC_ACTSLIKELABEL

- OLEMISC_NOUIACTIVATE

- OLEMISC_ALIGNABLE

- OLEMISC_IMEMODE

- OLEMISC_SIMPLEFRAME

- OLEMISC_SETCLIENTSITEFIRST

*tlıd*<br/>
Denetim sınıfının benzersiz KIMLIĞI.

*Wverana*<br/>
Denetim sınıfının ana sürüm numarası.

*wVerMinor*<br/>
Denetim sınıfının ikincil sürüm numarası.

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, denetimin OLE denetimi kullanan kapsayıcılar tarafından kullanılmasını sağlar. `AfxOleRegisterControlClass` kayıt defterini sistemdeki denetim adı ve konumuyla güncelleştirir ve ayrıca, denetimin desteklediği iş parçacığı modelini ayarlar. Daha fazla bilgi için, bkz. [Teknik not64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "OLE denetimlerinde apartman modeli iş parçacığı" ve Windows SDK [süreçler ve iş parçacıkları hakkında](/windows/win32/ProcThread/about-processes-and-threads) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

Yukarıdaki örnek, `AfxOleRegisterControlClass` Insertable için bayrağıyla nasıl çağrılacağını ve altıncı parametre oluşturmak için Apartment model ORed bayrağını birlikte gösterir:

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

Denetim, etkin kapsayıcılar için nesne Ekle iletişim kutusunda görünür ve Grup modeli kullanan bir işlem olur. Grup modeli kullanan denetimler, statik sınıf verilerinin kilitler tarafından korunduğundan emin olmak için, bir grupta bir denetim statik verilere erişirken, bu, bitmeden önce Zamanlayıcı tarafından devre dışı bırakılmadığından ve aynı sınıfın başka bir örneği aynı statik verileri kullanmaya başladıktan sonra. Statik verilere olan erişimler, kritik bölüm kodu ile çevrelenebilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a> AfxOleRegisterPropertyPageClass

Özellik sayfası sınıfını Windows kayıt veritabanına kaydeder.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Özellik sayfası sınıfıyla ilişkili modülün örnek tanıtıcısı.

*in*<br/>
Özellik sayfasının benzersiz sınıf KIMLIĞI.

*ıdtypename*<br/>
Özellik sayfası için Kullanıcı tarafından okunabilen bir ad içeren dizenin kaynak KIMLIĞI.

*nRegFlags*<br/>
Şu bayrağı içerebilir:

- `afxRegApartmentThreading` Kayıt defterindeki iş parçacığı modelini ThreadingModel = Apartment olarak ayarlar.

> [!NOTE]
> MFC 4,2 ' den önceki MFC sürümlerinde **`int`** *nregflags* parametresi yoktu. Ayrıca, `afxRegInsertable` bayrağın Özellik sayfaları için geçerli bir seçenek olmadığını ve AYARLANDıYSA MFC 'de BIR onaylama yapılmasına neden olacağını unutmayın.

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu özellik sayfasının OLE denetimi kullanan kapsayıcılar tarafından kullanılmasını sağlar. `AfxOleRegisterPropertyPageClass` kayıt defterini, özellik sayfası adı ve sistemdeki konumu ile güncelleştirir ve ayrıca denetim kayıt defterinde denetim tarafından desteklenen iş parçacığı modelini ayarlar. Daha fazla bilgi için, bkz. [Teknik not64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "OLE denetimlerinde apartman modeli iş parçacığı" ve Windows SDK [süreçler ve iş parçacıkları hakkında](/windows/win32/ProcThread/about-processes-and-threads) .

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a> AfxOleRegisterTypeLib

Tür kitaplığını Windows kayıt veritabanına kaydeder ve tür kitaplığının OLE denetimi kullanan diğer kapsayıcılar tarafından kullanılmasına izin verir.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Tür kitaplığıyla ilişkili uygulamanın örnek tanıtıcısı.

*tlıd*<br/>
Tür kitaplığının benzersiz KIMLIĞI.

*pszFileName*<br/>
Yerelleştirilmiş bir tür kitaplığının isteğe bağlı dosya adına işaret eder (. TLB) dosyasını denetleyin.

*pszHelpDir*<br/>
Tür kitaplığı için yardım dosyasının bulunabileceği dizinin adı. NULL ise, yardım dosyasının tür kitaplığının kendisiyle aynı dizinde olduğu varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığı kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, kayıt defterini tür kitaplığı adı ve sistemdeki konumu ile güncelleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a> AfxOleUnregisterClass

Windows kayıt veritabanından denetim veya özellik sayfası sınıfı girdisini kaldırır.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>Parametreler

*In*<br/>
Denetim veya özellik sayfasının benzersiz sınıf KIMLIĞI.

*Pszprogıd*<br/>
Denetim veya özellik sayfasının benzersiz program KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim veya özellik sayfası sınıfının kaydı başarıyla silindi ise sıfır dışında; Aksi takdirde 0.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a> AfxOleUnregisterTypeLib

Windows kayıt veritabanından tür kitaplığı girişini kaldırmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>Parametreler

*Tlıd*<br/>
Tür kitaplığının benzersiz KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığının kaydı başarıyla silindi ise sıfır dışında; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
