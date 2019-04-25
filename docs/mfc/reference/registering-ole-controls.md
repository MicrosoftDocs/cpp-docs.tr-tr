---
title: OLE Denetimlerini Kaydetme
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.ole
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 9c480696bdec3591f0509cbad04051a2b3af4070
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310142"
---
# <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

OLE denetimleri, diğer OLE server nesneleri gibi OLE kullanan diğer uygulamalar tarafından erişilebilir. Bu, denetimin tür kitaplığı ve sınıf kaydederek sağlanır.

Aşağıdaki işlevleri ekleyin ve denetimin sınıf, özellik sayfaları ve tür kitaplığı Windows kayıt defteri veritabanındaki çıkarmanıza izin ver:

### <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme

|||
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Denetimin sınıf kaydı veritabanına ekler.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Bir denetimi özellik sayfası kayıt veritabanına ekler.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Denetimin tür kitaplığı kaydı veritabanına ekler.|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Bir denetim sınıf veya özellik sayfası sınıfının kayıt veritabanından kaldırır.|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Denetimin tür kitaplığını kayıt veritabanından kaldırır.|

`AfxOleRegisterTypeLib` genellikle bir denetim DLL'nin uygulamasında olarak da adlandırılır `DllRegisterServer`. Benzer şekilde, `AfxOleUnregisterTypeLib` tarafından çağrılır `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, ve `AfxOleUnregisterClass` genellikle adlandırılır `UpdateRegistry` denetimin sınıf fabrikası veya özellik sayfasının üye işlevi.

##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass

İle Windows kayıt defteri veritabanında control sınıfı kaydeder.

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
Örnek tanıtıcısını denetimi sınıfıyla ilişkili modülü.

*CLSID*<br/>
Denetim sınıfı benzersiz kimliği.

*pszProgID*<br/>
Denetim programı benzersiz kimliği.

*idTypeName*<br/>
Denetim için bir kullanıcı tarafından okunabilen tür adını içeren dize kaynak kimliği.

*idBitmap*<br/>
OLE denetimi araç çubuğu veya paletini göstermek için kullanılan bit eşlemi kaynak kimliği.

*nRegFlags*<br/>
Bir veya daha fazla aşağıdaki bayraklar içerir:

- `afxRegInsertable` OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesini sağlar.

- `afxRegApartmentThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar Grup =.

- `afxRegFreeThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar ücretsiz =.

   İki bayrak birleştirebilirsiniz `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel ayarlamak için her ikisi =. Bkz: [Inprocserver32](/windows/desktop/com/inprocserver32) model kaydı iş parçacığı oluşturma hakkında daha fazla bilgi için Windows SDK.

> [!NOTE]
>  MFC 4.2 önce MFC sürümlerinde **int** *nRegFlags* parametresi olan bir Boole parametresi *bInsertable*, izin verilen veya izin verilmeyen INSERT eklenecek denetimin Nesne iletişim kutusu.

*dwMiscStatus*<br/>
Bir veya daha fazla aşağıdaki durum bayrakları (bayrakları, bkz: OLEMISC Windows SDK'sı numaralandırmada açıklamasını) içerir:

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
Denetim sınıfı benzersiz kimliği.

*wVerMajor*<br/>
Denetim sınıfı ana sürüm sayısı.

*wVerMinor*<br/>
Denetim sınıfı alt sürüm sayısı.

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kaydedildiği olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu denetimi kullanan OLE kapsayıcıları tarafından kullanılmak üzere denetim sağlar. `AfxOleRegisterControlClass` denetimin adı ve konumu sistem üzerindeki kayıt defterini güncelleştirir ve ayrıca kayıt defterinde denetimini destekleyen iş parçacığı modelini ayarlar. Daha fazla bilgi için [Teknik Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartman modeli iş parçacığı içinde OLE denetimleri," ve [ilgili işlemler ve iş parçacıkları](/windows/desktop/ProcThread/about-processes-and-threads) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

Yukarıdaki örnek gösterir nasıl `AfxOleRegisterControlClass` bayrağı Insertable çağrılır ve bayrağı apartman modeli ORed altıncı parametrenin birlikte oluşturmak için:

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

Denetimin etkin kapsayıcılar için Nesne Ekle iletişim kutusunda gösterilir ve apartman modeli uyumlu olacaktır. Böylece bir grup denetiminde statik veri eriştiği sırada Zamanlayıcı tarafından işlemi tamamlanana ve kullanarak aynı sınıf başka bir örneğini başlatır. önce devre dışı değil apartman modeli kullanan denetimler bu statik sınıf verileri kilit tarafından korunuyor emin olmanız gerekir aynı statik veriler. Statik veri herhangi bir erişimin kritik bölüm kodla çevrelenir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxctl.h

##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass

Özellik sayfası sınıfının Windows kayıt veritabanı ile kaydeder.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Örnek tanıtıcısını özellik sayfası sınıfının ile ilişkili modülü.

*CLSID*<br/>
Özellik sayfası sınıfı benzersiz kimliği.

*idTypeName*<br/>
Özellik sayfası için bir kullanıcı tarafından okunabilen ad içeren dize kaynak kimliği.

*nRegFlags*<br/>
Bayrağı içerebilir:

- `afxRegApartmentThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar Grup =.

> [!NOTE]
>  MFC 4.2 MFC sürümlerde **int** *nRegFlags* parametre kullanılabilir değil. Ayrıca `afxRegInsertable` bayrağı özellik sayfaları için geçerli bir seçenek değildir ve bu ayarlanırsa bir ONAYLAMADIR MFC'de neden olur

### <a name="return-value"></a>Dönüş Değeri

Denetim sınıfı kaydedildiği olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu özellik sayfası denetimi kullanan OLE kapsayıcıları tarafından kullanılacak sağlar. `AfxOleRegisterPropertyPageClass` özellik sayfası adını ve konumunu sistem üzerindeki kayıt defterini güncelleştirir ve ayrıca kayıt defterinde denetimini destekleyen iş parçacığı modelini ayarlar. Daha fazla bilgi için [Teknik Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartman modeli iş parçacığı içinde OLE denetimleri," ve [ilgili işlemler ve iş parçacıkları](/windows/desktop/ProcThread/about-processes-and-threads) Windows SDK.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxctl.h

##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib

Windows kayıt veritabanıyla tür kitaplığını kaydeder ve OLE-denetimi kullanan diğer kapsayıcı tarafından kullanılacak tür kitaplığını sağlar.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Tür kitaplığı ile ilişkili uygulama örneğinin tutamacını.

*tlid*<br/>
Tür kitaplığının benzersiz kimliği.

*pszFileName*<br/>
Yerelleştirilmiş tür kitaplığının isteğe bağlı dosya adına işaret (. Denetim için TLB) dosyası.

*pszHelpDir*<br/>
Tür kitaplığı için Yardım dosyasına bulunduğu dizinin adı. NULL ise, Yardım dosyası tür kitaplığı ile aynı dizinde olduğu varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığı kayıtlı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tür kitaplığı adı ve konumu sistem üzerindeki kayıt defterini güncelleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass

Denetim veya özellik sayfası sınıfının giriş Windows kayıt veritabanından kaldırır.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
Denetim veya özellik sayfası sınıfı benzersiz kimliği.

*pszProgID*<br/>
Denetim veya özellik sayfasının benzersiz program kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim veya özellik sayfası sınıfının kaydı başarıyla silindi olursa sıfır dışı; Aksi durumda 0.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxctl.h

##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib

Tür kitaplığı giriş Windows kayıt veritabanından kaldırmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>Parametreler

*tlID*<br/>
Tür kitaplığının benzersiz kimliği.

### <a name="return-value"></a>Dönüş Değeri

Tür kitaplığı kaydı başarıyla silindi olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
