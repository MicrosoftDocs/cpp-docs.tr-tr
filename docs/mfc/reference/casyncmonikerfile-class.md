---
title: CAsyncMonikerFile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: 57ab463445f249b4e9393f19af103b7588962d5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377004"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile Sınıfı

ActiveX kontrollerinde (eski adıyla OLE kontrolleri) eşzamanlı moniker kullanımı için işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Bir `CAsyncMonikerFile` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile::Kapat](#close)|Tüm kaynakları kapatır ve serbest bırakır.|
|[CAsyncMonikerFile::GetBinding](#getbinding)|Eşenkron aktarım bağlama için bir işaretçi alır.|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Akıştaki verilerin biçimini alır.|
|[CAsyncMonikerFile::Aç](#open)|Bir dosyayı eş senkronize olarak açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Uygulayan bir COM nesnesi oluşturur. `IBindStatusCallback`|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Oluşturulacak bağlama türü hakkında bilgi istemek için OLE sistem kitaplığı tarafından çağrılır.|
|[CAsyncMonikerFile::GetPriority](#getpriority)|Bağlama önceliğini almak için OLE sistem kitaplığı tarafından çağrılır.|
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Eşiş bağlama işlemleri sırasında istemci tarafından kullanılabilir hale gelir gibi veri sağlamak için çağrılır.|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Kaynaklar düşük olduğunda çağrılır.|
|[CAsyncMonikerFile::İlerleme](#onprogress)|Veri indirme işleminde ilerlemeyi belirtmek için çağrıldı.|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Bağlama başlatıldığında denir.|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Eşzamanlı aktarım durdurulduğunda çağrılır.|

## <a name="remarks"></a>Açıklamalar

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)türetilmiştir , sırayla [COleStreamFile](../../mfc/reference/colestreamfile-class.md)türetilmiştir , `CAsyncMonikerFile` bir URL'den eşit olarak dosya yükleme de dahil olmak üzere, eşzamanlı olarak herhangi bir veri akışı erişmek için [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimini kullanır. Dosyalar ActiveX denetimlerinin veri yolu özellikleri olabilir.

Asynchronous monikers dosya aktarımları sırasında duyarlı bir kullanıcı arabirimi sağlamak için internet özellikli uygulamalar ve ActiveX denetimleri öncelikle kullanılır. Bunun en önemli örneklerinden biri, ActiveX denetimleri için eşzamanlı özellikler sağlamak için [CDataPathProperty'in](../../mfc/reference/cdatapathproperty-class.md) kullanılmasıdır. Nesne, `CDataPathProperty` uzun bir özellik değiştirme işlemi sırasında yeni verilerin kullanılabilirliğini belirtmek için sürekli olarak geri çağrı alır.

Internet uygulamalarında eşzamanlı monikers ve ActiveX denetimlerinin nasıl kullanılacağı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [İnternet İlk Adımlar: Asynchronous Monikers](../../mfc/asynchronous-monikers-on-the-internet.md)

- [İnternet İlk Adımlar: ActiveX Denetimleri](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerDosya](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile

Bir `CAsyncMonikerFile` nesne inşa eder.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Açıklamalar

`IBindHost` Arabirimi oluşturmaz. `IBindHost`yalnızca `Open` üye işlevde sağlarsanız kullanılır.

`IBindHost` Arabirimin açıklaması için Windows SDK'ya bakın.

## <a name="casyncmonikerfileclose"></a><a name="close"></a>CAsyncMonikerFile::Kapat

Tüm kaynakları kapatmak ve serbest bırakmak için bu işlevi arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açılmamış veya zaten kapalı olan dosyalara çağrılabilir.

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback

Uygulayan bir COM nesnesi oluşturur. `IBindStatusCallback`

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Parametreler

*pUnkKontroling*<br/>
Toplama kullanılmıyorsa, bilinmeyen `IUnknown`(dış) veya NULL denetimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*pUnkControlling* NULL değilse, işlev destekleyen yeni bir `IUnknown` COM nesnesi `IBindStatusCallback`üzerinde iç bir işaretçi döndürür. NULL `pUnkControlling` ise, işlev yeni bir `IUnknown` COM nesnesi `IBindStatusCallback`destekleyen bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`CAsyncMonikerFile`uygulayan bir COM nesnesi `IBindStatusCallback`gerektirir. MFC böyle bir nesne uygular ve toplanır. Kendi COM `CreateBindStatusCallback` nesnenizi döndürmek için geçersiz kılabilirsiniz. COM nesneniz, COM nesnenizin `CreateBindStatusCallback` denetleme bilinmeyeniyle arayarak MFC uygulamasını toplayabilir. `CCmdTarget` COM desteği kullanılarak uygulanan COM nesneleri kullanarak `CCmdTarget::GetControllingUnknown`kontrol bilinmeyen alabilir.

Alternatif olarak, COM nesneniz arayarak `CreateBindStatusCallback( NULL )`MFC'nin uygulamasına temsilci verebilir.

[CAsyncMonikerFile::Aramaları aç.](#open) `CreateBindStatusCallback`

Asynchronous monikers ve asynchronous bağlama hakkında daha fazla bilgi için, [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) arabirimi ve [nasıl Asynchronous Ciltleme ve Depolama İş](/windows/win32/Stg/how-asynchronous-binding-and-storage-work)bakın. Toplama tartışması için [bkz.](/windows/win32/com/aggregation) Üç konu da Windows SDK'dadır.

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo

Asynchronous lakabının istemcisinden asynchronous lakabını nasıl bağlamak istediğini söylemek için çağrıldı.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Dönüş Değeri

Için ayarları `IBindStatusCallBack`alır. `IBindStatusCallback` Arabirimin açıklaması için Windows SDK'ya bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bağlamayı bir depolama ortamı (akış) kullanmak ve veri itme modelini kullanmak üzere asynchronous olarak ayarlar. Bağlama davranışını değiştirmek istiyorsanız bu işlevi geçersiz kılın.

Bunu yapmanın bir nedeni, veri itme modeli yerine veri çekme modelini kullanarak bağlamak olacaktır. Veri çekme modelinde, istemci bağlama işlemini kullanır ve takma adı yalnızca okunduğunda istemciye veri sağlar. Bir veri itme modelinde, takma adı asynchronous bağlama işlemini yönlendirir ve yeni veriler kullanılabilir olduğunda istemciyi sürekli olarak haber verirken.

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsyncMonikerFile::GetBinding

Asynchronous aktarım bağlama için bir işaretçi almak için bu işlevi arayın.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı aktarım `IBinding` başladığında sağlanan arabirime işaretçi. Herhangi bir nedenle aktarım eşzamanlı olarak yapılamıyorsa NULL'u döndürür.

### <a name="remarks"></a>Açıklamalar

Bu, veri aktarım işlemini `IBinding` arayüz üzerinden kontrol `IBinding::Abort`etmenizi `IBinding::Pause`sağlar, örneğin , , ve `IBinding::Resume`.

`IBinding` Arabirimin açıklaması için Windows SDK'ya bakın.

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc

Akıştaki verilerin biçimini almak için bu işlevi arayın.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda açılan akış için Windows yapısı [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) için bir işaretçi. Takma aparat bağlı değilse, eşkron değilse veya eşyokkron işlem başlatılmışsa NULL'u döndürür.

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMonikerFile::GetPriority

Bağlama işlemi bağlama işlemi için iş parçacığına verilen önceliği almaya başladığında, bir eşzamanlı takma ad istemcisinden çağrılır.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşkron transferin yapılacağı öncelik. Standart iş parçacığı öncelik bayraklarından biri: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL ve THREAD_PRIORITY_TIME_CRITICAL. Bu değerlerin açıklaması için Windows işlevi [SetThreadPriority'e](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bakın.

### <a name="remarks"></a>Açıklamalar

`GetPriority`doğrudan çağrılmamalıdır. THREAD_PRIORITY_NORMAL varsayılan uygulama tarafından döndürülür.

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable

Bir eşzamanlı takma ad, kullanılabilir `OnDataAvailable` olduğunda istemciye, eşzamanlı bağlama işlemleri sırasında veri sağlamak için çağırır.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Parametreler

*dwSize*<br/>
Bağlamanın başlangıcından bu yana kullanılabilen verilerin kümülatif tutarı (baytlar içinde). Veri miktarının işlemle ilgili olmadığını veya belirli bir miktarın kullanılabilir olmadığını belirten sıfır olabilir.

*bscfBayrak*<br/>
Bir BSCF numaralandırma değeri. Aşağıdaki değerlerden biri veya birkaçı olabilir:

- BSCF_FIRSTDATANOTIFICATION Belirli bir `OnDataAvailable` bağlama işlemi için ilk çağrıyı tanımlar.

- BSCF_INTERMEDIATEDATANOTIFICATION Bağlama işlemi için `OnDataAvailable` bir ara çağrı tanımlar.

- BSCF_LASTDATANOTIFICATION Bağlama işlemi `OnDataAvailable` için yapılan son çağrıyı tanımlar.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Örnek uygulama için aşağıdaki örneğe bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource

Kaynaklar düşük olduğunda lakap tarafından çağrılır.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama `GetBinding( )-> Abort( )`çağırır.

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsyncMonikerFile::İlerleme

Bu bağlama işleminin geçerli ilerlemesini belirtmek için takma ad tarafından genellikle uzun bir işlem sırasında makul aralıklarla çağrılır.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Parametreler

*ulProgress*<br/>
*UlProgressMax'te*belirtilen maksimuma göre bağlama işleminin geçerli ilerlemesini gösterir.

*ulProgressMax*<br/>
Bu işlem `OnProgress` için yapılan çağrılar süresince *ulProgress'in* beklenen maksimum değerini gösterir.

*ulStatusCode*<br/>
Bağlama işleminin ilerlemesiyle ilgili ek bilgiler sağlar. Geçerli değerler numaralandırmadan `BINDSTATUS` alınır. Olası değerler için Açıklamalar'a bakın.

*szStatusText*<br/>
*UlStatusCode*değerine bağlı olarak, mevcut ilerleme hakkında bilgi. Olası değerler için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

*ulStatusCode* (ve her değer için *szStatusText)* için olası değerler şunlardır:

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |Bağlama işlemi, bağlı olan nesneyi veya depolamayı tutan kaynağı bulmaktır. *szStatusText,* aranmakta olan kaynağın görüntü adını sağlar (örneğin, "www.microsoft.com").  |
|BINDSTATUS_CONNECTING  |Bağlama işlemi, bağlı olan nesneyi veya depolamayı tutan kaynağa bağlanır. *szStatusText* bağlı olan kaynağın görüntü adını (örneğin, bir IP adresi) sağlar.  |
|BINDSTATUS_SENDINGREQUEST|Bağlama işlemi, bağlı olan nesneyi veya depolamayı talep ediyor. *szStatusText* nesnenin görüntü adını (örneğin, bir dosya adı) sağlar.|
|BINDSTATUS_REDIRECTING  |Bağlama işlemi farklı bir veri konumuna yönlendirildi. *szStatusText* yeni veri konumunun görüntü adını sağlar.  |
|BINDSTATUS_USINGCACHEDCOPY  |Bağlama işlemi, istenen nesneyi veya depolamayı önbelleğe alınmış bir kopyadan alıyor. *szStatusText* NULL'dur.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |Bağlama işlemi, bağlı olan nesneyi veya depolamayı almaya başladı. *szStatusText* veri konumunun görüntü adını sağlar.|
|BINDSTATUS_DOWNLOADINGDATA  |Bağlama işlemi, bağlı olan nesneyi veya depolamayı almaya devam ediyor. *szStatusText* veri konumunun görüntü adını sağlar.  |
|BINDSTATUS_ENDDOWNLOADDATA  |Bağlama işlemi, bağlanılan nesneyi veya depolamayı almayı tamamladı. *szStatusText* veri konumunun görüntü adını sağlar.  |
|BINDSTATUS_CLASSIDAVAILABLE  |Bağlanan nesnenin bir örneği oluşturulmak üzere. *szStatusText,* yeni nesnenin CLSID'sini dize biçiminde sağlayarak istemciye istenirse bağlama işlemini iptal etme fırsatı verir.  |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding

Bağlama başlatılırken eylemleri gerçekleştirmek için türetilmiş sınıflarınızda bu işlevi geçersiz kılın.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev lakap tarafından geri çağrılır. Varsayılan uygulama hiçbir şey yapmaz.

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding

Bağlama işleminin sonunda lakap tarafından çağrılır.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Parametreler

*Hresult*<br/>
Hata veya uyarı değeri olan bir HRESULT.

*szErrort*<br/>
Hatayı açıklayan bir karakter dizesi.

### <a name="remarks"></a>Açıklamalar

Aktarım durdurulduğunda eylemleri gerçekleştirmek için bu işlevi geçersiz kılın. Varsayılan olarak, işlev `IBinding`salgılar.

`IBinding` Arabirimin açıklaması için Windows SDK'ya bakın.

## <a name="casyncmonikerfileopen"></a><a name="open"></a>CAsyncMonikerFile::Aç

Bir dosyayı eşsenkronize olarak açmak için bu üye işlevi arayın.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
Eşsenkronize olarak açılacak dosya işaretçisi. Dosya geçerli bir URL veya dosya adı olabilir.

*pHata*<br/>
Dosya özel durumlar için bir işaretçi. Bir hata durumunda, neden olarak ayarlanır.

*pMoniker*<br/>
Asynchronous takma arabirimine `IMoniker`işaretçi, belgenin kendi lakabının `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`birleşimi olan ve yol adından oluşturulan bir takma ad. Denetim bağlamak için bu takma adı kullanabilirsiniz, ancak bu denetim kaydetmesi gereken takma adı değildir.

*pBindHost*<br/>
Potansiyel olarak `IBindHost` göreli bir yol adından lakap oluşturmak için kullanılacak arabirimeye işaretçi. Bağlama ana bilgisayarı geçersizse veya takma adı sağlamazsa, arama varsayılan `Open(lpszFileName,pError)`olarak . `IBindHost` Arabirimin açıklaması için Windows SDK'ya bakın.

*pServiceProvider*<br/>
Arabirimin işaretçisi. `IServiceProvider` Hizmet sağlayıcısı geçersizse veya hizmeti `IBindHost`sağlayamazsa, arama `Open(lpszFileName,pError)`varsayılan olarak .

*pBilinmeyen*<br/>
Arabirimin işaretçisi. `IUnknown` `IServiceProvider` Bulunursa, işlev sorguları `IBindHost`. Hizmet sağlayıcısı geçersizse veya hizmeti `IBindHost`sağlayamazsa, arama `Open(lpszFileName,pError)`varsayılan olarak .

### <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla açılırsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu çağrı bağlama işlemini başlatır.

*LPSZURL* parametresi için bir URL veya dosya adı kullanabilirsiniz. Örneğin:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\-veya -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CMonikerFile Sınıfı](../../mfc/reference/cmonikerfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMonikerFile Sınıfı](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
