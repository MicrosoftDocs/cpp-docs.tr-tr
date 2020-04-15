---
title: OLE Denetimlerini Kaydetme
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 2f2d7872e8b9369b5eef283e5b52a54c29afd563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372966"
---
# <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

Diğer OLE sunucu nesneleri gibi OLE denetimlerine de Diğer OLE'ye duyarlı uygulamalar tarafından erişilebilir. Bu, denetimin tür kitaplığı ve sınıfı kaydedilerek elde edilir.

Aşağıdaki işlevler, Denetimin sınıfını, özellik sayfalarını ve windows kayıt veritabanındaki kitaplığını eklemenize ve kaldırmanıza olanak tanır:

### <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

|||
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Denetimin sınıfını kayıt veritabanına ekler.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Kayıt veritabanına bir denetim özelliği sayfası ekler.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Denetimin tür kitaplığını kayıt veritabanına ekler.|
|[AfxOleKayıt DışıSınıf](#afxoleunregisterclass)|Kayıt veritabanından bir denetim sınıfını veya özellik sayfası sınıfını kaldırır.|
|[AfxOleKayıt DışıTypeLib](#afxoleunregistertypelib)|Denetimin tür kitaplığını kayıt veritabanından kaldırır.|

`AfxOleRegisterTypeLib`genellikle bir denetim DLL's uygulamasında `DllRegisterServer`denir. Benzer şekilde, `AfxOleUnregisterTypeLib` tarafından `DllUnregisterServer`çağrılır. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`ve `AfxOleUnregisterClass` genellikle bir denetimin sınıf fabrikası veya özellik sayfasının `UpdateRegistry` üye işlevi tarafından çağrılır.

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass

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

*Hınstance*<br/>
Denetim sınıfıyla ilişkili modülün örnek tutamacı.

*Clsıd*<br/>
Denetimin benzersiz sınıf kimliği.

*pszProgID*<br/>
Denetimin benzersiz program kimliği.

*idTypeName*<br/>
Denetim için kullanıcı tarafından okunabilen bir tür adı içeren dize kaynak kimliği.

*idBitmap*<br/>
Araç çubuğunda veya palette OLE denetimini temsil etmek için kullanılan bit eşlesinin kaynak kimliği.

*nRegFlags*<br/>
Aşağıdaki bayraklardan birini veya birkaçını içerir:

- `afxRegInsertable`Denetimin OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesini sağlar.

- `afxRegApartmentThreading`İş parçacığı modelini threadingModel=Apartment olarak ayarlar.

- `afxRegFreeThreading`Kayıt defterindeki iş parçacığı modelini ThreadingModel=Free olarak ayarlar.

   İki bayrağı `afxRegApartmentThreading` `afxRegFreeThreading` birleştirip ThreadingModel=Her ikisini de ayarlayabilirsiniz. İş parçacığı modeli kaydı hakkında daha fazla bilgi için Windows SDK'da [InprocServer32'ye](/windows/win32/com/inprocserver32) bakın.

> [!NOTE]
> MFC 4.2'den önceki MFC sürümlerinde, **int** *nRegFlags* parametresi, nesne ekleme iletişim kutusundan denetimin eklenmesine izin veren veya izin verilmeyen bir BOOL parametresi, *bInsertable'dır.*

*dwMiscDurum*<br/>
Aşağıdaki durum bayraklarından birini veya birkaçını içerir (bayrakların açıklaması için Windows SDK'daki OLEMISC numaralandırması'na bakın):

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

*tlid*<br/>
Denetim sınıfının benzersiz kimliği.

*wVerMajor*<br/>
Denetim sınıfının ana sürüm numarası.

*wVerMinor*<br/>
Denetim sınıfının küçük sürüm numarası.

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kayıtlıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, denetimin OLE denetimi ne kadar bilinçli olan kapsayıcılar tarafından kullanılmasını sağlar. `AfxOleRegisterControlClass`kayıt defterini denetimin adı ve sistemdeki konumuyla güncelleştirir ve ayrıca denetimin kayıt defterinde desteklediği iş parçacığı modelini ayarlar. Daha fazla bilgi için Teknik [Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "OLE Denetimlerinde Daire-Model İş Parçacığı" ve Windows SDK'daki [İşlemler ve İş Parçacıkları hakkında](/windows/win32/ProcThread/about-processes-and-threads) bilgi verildi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

Yukarıdaki örnek, altıncı `AfxOleRegisterControlClass` parametreyi oluşturmak için eklenen bayrak ve daire modeli ORed için bayrak ile birlikte nasıl çağrıldığını gösterir:

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

Denetim, etkin kapsayıcılar için Nesne Ekle iletişim kutusunda görünür ve daire modeline duyarlı olur. Daire modeli nene denetimleri statik sınıf verilerinin kilitler tarafından korunduğundan emin olmalıdır, böylece bir dairedeki bir denetim statik verilere erişirken, tamamlanmadan önce zamanlayıcı tarafından devre dışı bırakılmaz ve aynı sınıfın başka bir örneği aynı statik verileri kullanmaya başlar. Statik verilere tüm erişimler kritik bölüm kodu ile çevrili olacaktır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass

Özellik sayfası sınıfını Windows kayıt veritabanına kaydeder.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>Parametreler

*Hınstance*<br/>
Özellik sayfası sınıfıyla ilişkili modülün örnek tutamacı.

*Clsıd*<br/>
Özellik sayfasının benzersiz sınıf kimliği.

*idTypeName*<br/>
Özellik sayfası için kullanıcı tarafından okunabilir bir ad içeren dize kaynak kimliği.

*nRegFlags*<br/>
Bayrağı içerebilir:

- `afxRegApartmentThreading`İş parçacığı modelini threadingModel = Apartment olarak ayarlar.

> [!NOTE]
> MFC 4.2'den önceki MFC sürümlerinde **int** *nRegFlags* parametresi kullanılamadı. Bayrağın `afxRegInsertable` özellik sayfaları için geçerli bir seçenek olmadığını ve ayarlanırsa MFC'de bir Assert'a neden olacağını da unutmayın

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kayıtlıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu özellik sayfası ole-denetim farkında kapsayıcılar tarafından kullanılmasını sağlar. `AfxOleRegisterPropertyPageClass`kayıt defterini özellik sayfası adı ve sistemdeki konumuyla güncelleştirir ve denetimin kayıt defterinde desteklediği iş parçacığı modelini ayarlar. Daha fazla bilgi için Teknik [Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "OLE Denetimlerinde Daire-Model İş Parçacığı" ve Windows SDK'daki [İşlemler ve İş Parçacıkları hakkında](/windows/win32/ProcThread/about-processes-and-threads) bilgi verildi.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib

Tür kitaplığını Windows kayıt veritabanına kaydeder ve tür kitaplığı ole denetimi farkında olan diğer kapsayıcılar tarafından kullanılmasına izin verir.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>Parametreler

*Hınstance*<br/>
Tür kitaplığıyla ilişkili uygulamanın örnek tutamacı.

*tlid*<br/>
Tür kitaplığın benzersiz kimliği.

*pszFileName*<br/>
Yerelleştirilmiş bir tür kitaplığın isteğe bağlı dosya adını (. TLB) denetim için dosya.

*pszHelpDir*<br/>
Tür kitaplığı için yardım dosyasının bulunabileceği dizinin adı. NULL ise, yardım dosyasının tür kitaplığıyla aynı dizinde olduğu varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığı kayıtlıysa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, kayıt defterini tür kitaplığı adı ve sistemdeki konumuyla güncelleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a>AfxOleKayıt DışıSınıf

Denetim veya özellik sayfası sınıf girişini Windows kayıt veritabanından kaldırır.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Denetim veya özellik sayfasının benzersiz sınıf kimliği.

*pszProgID*<br/>
Denetim veya özellik sayfasının benzersiz program kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim veya özellik sayfası sınıfı başarıyla kayıt dışı ysa sıfırsız; aksi takdirde 0.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a>AfxOleKayıt DışıTypeLib

Tür kitaplığı girişini Windows kayıt veritabanından kaldırmak için bu işlevi arayın.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>Parametreler

*tlID*<br/>
Tür kitaplığın benzersiz kimliği.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığı başarıyla kayıt dışıysa sıfırsız; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
