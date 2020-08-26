---
title: CAsyncMonikerFile sınıfı
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
ms.openlocfilehash: 259d31b9c1e198b326ba616481dbbf5315225546
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845945"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile sınıfı

ActiveX denetimlerinde (eski adıyla OLE denetimleri) zaman uyumsuz adların kullanılması için işlevsellik sağlar.

## <a name="syntax"></a>Syntax

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Bir `CAsyncMonikerFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile:: Close](#close)|Tüm kaynakları kapatır ve serbest bırakır.|
|[CAsyncMonikerFile:: GetBinding](#getbinding)|Zaman uyumsuz aktarım bağlamasının işaretçisini alır.|
|[CAsyncMonikerFile:: GetFormatEtc](#getformatetc)|Akıştaki verilerin biçimini alır.|
|[CAsyncMonikerFile:: Open](#open)|Bir dosyayı zaman uyumsuz olarak açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAsyncMonikerFile:: CreateBindStatusCallback](#createbindstatuscallback)|Uygulayan bir COM nesnesi oluşturur `IBindStatusCallback` .|
|[CAsyncMonikerFile:: GetBindInfo](#getbindinfo)|Oluşturulacak bağlama türü hakkında bilgi istemek için OLE sistem kitaplığı tarafından çağırılır.|
|[CAsyncMonikerFile:: GetPriority](#getpriority)|Bağlamanın önceliğini almak için OLE sistem kitaplığı tarafından çağırılır.|
|[CAsyncMonikerFile:: OnDataAvailable](#ondataavailable)|Zaman uyumsuz bağlama işlemleri sırasında istemci tarafından kullanılabilir hale geldiği için verileri sağlamak üzere çağırılır.|
|[CAsyncMonikerFile:: OnLowResource](#onlowresource)|Kaynaklar azaldığında çağırılır.|
|[CAsyncMonikerFile:: OnProgress](#onprogress)|Veri indirme işlemindeki ilerlemeyi göstermek için çağırılır.|
|[CAsyncMonikerFile:: OnStartBinding](#onstartbinding)|Bağlama başlatıldığında çağırılır.|
|[CAsyncMonikerFile:: OnStopBinding](#onstopbinding)|Zaman uyumsuz aktarım durdurulduğunda çağırılır.|

## <a name="remarks"></a>Açıklamalar

[Cotastreamfile](../../mfc/reference/colestreamfile-class.md)'dan elde edilen [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)ÖĞESINDEN türetilmiş, `CAsyncMonikerFile` bir URL 'den zaman uyumsuz olarak dosya yükleme de dahil olmak üzere herhangi bir veri akışına zaman uyumsuz olarak erişmek için [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimini kullanır. Dosyalar, ActiveX denetimlerinin DataPath özellikleri olabilir.

Zaman uyumsuz adlar öncelikle Internet etkin uygulamalar ve ActiveX denetimlerinde, dosya aktarımları sırasında yanıt veren bir kullanıcı arabirimi sağlamak için kullanılır. Bunun ana örneği, ActiveX denetimleri için zaman uyumsuz özellikler sağlamak üzere [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) öğesinin kullanılması örneğidir. `CDataPathProperty`Nesne, uzun bir özellik değişim işlemi sırasında yeni verilerin kullanılabilirliğini göstermek için tekrar tekrar bir geri arama alır.

Internet uygulamalarında zaman uyumsuz bilinen adlar ve ActiveX denetimleri kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Internet Ilk adımları: zaman uyumsuz bilinen adlar](../../mfc/asynchronous-monikers-on-the-internet.md)

- [Internet Ilk adımları: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[Cotastreamfile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a> CAsyncMonikerFile::CAsyncMonikerFile

Bir `CAsyncMonikerFile` nesnesi oluşturur.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Açıklamalar

`IBindHost`Arabirimini oluşturmaz. `IBindHost` yalnızca onu `Open` üye işlevinde sağlarsanız kullanılır.

Arabirimin açıklaması için `IBindHost` bkz. Windows SDK.

## <a name="casyncmonikerfileclose"></a><a name="close"></a> CAsyncMonikerFile:: Close

Tüm kaynakları kapatmak ve serbest bırakmak için bu işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açık olmayan veya zaten kapatılmış dosyalar üzerinde çağrılabilir.

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a> CAsyncMonikerFile:: CreateBindStatusCallback

Uygulayan bir COM nesnesi oluşturur `IBindStatusCallback` .

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Parametreler

*Punkdenetleyen*<br/>
Bilinmeyen denetim işaretçisi (dıştaki `IUnknown` ) veya toplama KULLANıLMıYORSA null.

### <a name="return-value"></a>Dönüş Değeri

*Punkdenetlemesini* null değilse, işlev, `IUnknown` Yeni bir com nesnesi destekleyen, iç öğesine bir işaretçi döndürür `IBindStatusCallback` . `pUnkControlling`Null ise, işlev `IUnknown` destekleyen yenı bir com nesnesi üzerinde bir işaretçi döndürür `IBindStatusCallback` .

### <a name="remarks"></a>Açıklamalar

`CAsyncMonikerFile` uygulayan bir COM nesnesi gerektirir `IBindStatusCallback` . MFC böyle bir nesnesi uygular ve toplanabilir. `CreateBindStatusCallback`Kendı com nesneniz döndürmek için geçersiz kılabilirsiniz. COM nesneniz `CreateBindStatusCallback` , com nesnenizin bilinmeyen denetim ile ÇAĞıRARAK MFC 'nin uygulamasını toplayabilir. Com desteği kullanılarak uygulanan COM nesneleri `CCmdTarget` , kullanılarak bilinmeyen denetim elde edebilir `CCmdTarget::GetControllingUnknown` .

Alternatif olarak, COM nesneniz çağırarak MFC 'nin uygulamasına temsilci seçebilir `CreateBindStatusCallback( NULL )` .

[CAsyncMonikerFile:: Open](#open) çağrıları `CreateBindStatusCallback` .

Zaman uyumsuz adlar ve zaman uyumsuz bağlama hakkında daha fazla bilgi için, bkz. [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) arabirimi ve [zaman uyumsuz bağlama ve depolama çalışma](/windows/win32/Stg/how-asynchronous-binding-and-storage-work). Toplama ile ilgili bir tartışma için bkz. [toplama](/windows/win32/com/aggregation). Üç konunun hepsi Windows SDK.

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a> CAsyncMonikerFile:: GetBindInfo

Zaman uyumsuz bilinen bir bilinen ad istemcisinden, nasıl bağlamak istediği hakkında bilgi vermek için çağırılır.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayarlarını alır `IBindStatusCallBack` . Arabirimin açıklaması için `IBindStatusCallback` bkz. Windows SDK.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bağlamayı zaman uyumsuz olacak şekilde, bir depolama ortamı (Stream) kullanacak şekilde ayarlar ve veri gönderim modelini kullanır. Bağlamanın davranışını değiştirmek istiyorsanız bu işlevi geçersiz kılın.

Bunu yapmanın bir nedeni veri gönderim modeli yerine veri çekme modeli kullanılarak bağlanmalıdır. Bir veri çekme modelinde, istemci bağlama işlemini ve bilinen ad yalnızca istemciye okurken verileri sağlar. Veri gönderim modelinde, bilinen ad zaman uyumsuz bağlama işlemini ve yeni veriler kullanılabilir her seferinde sürekli olarak istemciye bildirir.

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a> CAsyncMonikerFile:: GetBinding

Zaman uyumsuz aktarım bağlamasının işaretçisini almak için bu işlevi çağırın.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Dönüş Değeri

`IBinding`Zaman uyumsuz aktarım başladığında belirtilen arabirime yönelik bir işaretçi. Aktarımın zaman uyumsuz olarak yapılılamazsa NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu, örneğin, ve ile veri aktarımı işlemini arabirim üzerinden denetlemenize olanak tanır `IBinding` `IBinding::Abort` `IBinding::Pause` `IBinding::Resume` .

Arabirimin açıklaması için `IBinding` bkz. Windows SDK.

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a> CAsyncMonikerFile:: GetFormatEtc

Akıştaki verilerin biçimini almak için bu işlevi çağırın.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda açık olan akış için Windows yapısı [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) işaretçisi. Bilinen ad, zaman uyumsuz değilse veya zaman uyumsuz işlem başlatılmazsa NULL değerini döndürür.

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a> CAsyncMonikerFile:: GetPriority

Bağlama işlemi, bağlama işlemi için iş parçacığına verilen önceliği almaya başladığı için, zaman uyumsuz bir bilinen ad istemcisinden çağırılır.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman uyumsuz aktarmanın gerçekleşcede olacağı öncelik. Standart iş parçacığı öncelik bayraklarından biri: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL ve THREAD_PRIORITY_TIME_CRITICAL. Bu değerlerin bir açıklaması için bkz. [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows işlevi.

### <a name="remarks"></a>Açıklamalar

`GetPriority` doğrudan çağrılmamalıdır. THREAD_PRIORITY_NORMAL, varsayılan uygulama tarafından döndürülür.

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a> CAsyncMonikerFile:: OnDataAvailable

Zaman uyumsuz bir bilinen ad `OnDataAvailable` , istemciye, zaman uyumsuz bağlama işlemleri sırasında kullanılabilir hale geldiğinde veri sağlamak için çağırır.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Parametreler

*dwSize*<br/>
Bağlamanın başlangıcından bu yana kullanılabilir verilerin birikmeli miktarı (bayt cinsinden). Sıfır olabilir, bu da veri miktarının işlemle ilgili olmadığını veya belirli bir tutarın kullanılabilir olmadığını gösterir.

*bscfFlag*<br/>
Bir BSCF numaralandırma değeri. Aşağıdaki değerlerden biri veya daha fazlası olabilir:

- BSCF_FIRSTDATANOTIFICATION, `OnDataAvailable` belirli bir bağlama işlemi için ilk çağrıyı tanımlar.

- BSCF_INTERMEDIATEDATANOTIFICATION, bağlama işlemi için bir ara çağrı tanımlar `OnDataAvailable` .

- BSCF_LASTDATANOTIFICATION, `OnDataAvailable` bağlama işlemi için son çağrıyı tanımlar.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. Örnek uygulama için aşağıdaki örneğe bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a> CAsyncMonikerFile:: OnLowResource

Kaynaklar düşük olduğunda bilinen ad tarafından çağırılır.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama çağrıları `GetBinding( )-> Abort( )` .

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a> CAsyncMonikerFile:: OnProgress

Genellikle uzun bir işlem sırasında makul aralıklarla bu bağlama işleminin geçerli ilerlemesini göstermek için bilinen ad tarafından çağırılır.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Parametreler

*ulProgress*<br/>
Bağlama işleminin, *ulProgressMax*içinde gösterilen beklenen maksimum sınıra göre geçerli ilerlemesini gösterir.

*ulProgressMax*<br/>
Bu işlem için çağrı süresince beklenen en büyük değer olan *ulProgress* değerini gösterir `OnProgress` .

*ulStatusCode*<br/>
Bağlama işleminin ilerleme durumuyla ilgili ek bilgi sağlar. Geçerli değerler `BINDSTATUS` numaralandırmasından alınır. Olası değerler için bkz. açıklamalar.

*szStatusText*<br/>
Geçerli ilerleme hakkında, *ulStatusCode*değerine bağlı olarak bilgiler. Olası değerler için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

*UlStatusCode* için olası değerler (ve her bir değer Için *szStatusText* ):

| Değer | Açıklama |
|--|--|
| BINDSTATUS_FINDINGRESOURCE | Bağlama işlemi, bağlı olan nesneyi veya depolamayı tutan kaynağı buluyor. *SzStatusText* , aranan kaynağın görünen adını (örneğin, "www.Microsoft.com") sağlar. |
| BINDSTATUS_CONNECTING | Bağlama işlemi, bağlı olan nesneyi veya depolamayı tutan kaynağa bağlanıyor. *SzStatusText* , bağlanılan kaynağın görünen adını (örneğin, bir IP adresi) sağlar. |
| BINDSTATUS_SENDINGREQUEST | Bağlama işlemi, bağlanan nesne veya depolamayı istiyor. *SzStatusText* nesnenin görünen adını (örneğin, bir dosya adı) sağlar. |
| BINDSTATUS_REDIRECTING | Bağlama işlemi farklı bir veri konumuna yeniden yönlendirildi. *SzStatusText* , yeni veri konumunun görünen adını sağlar. |
| BINDSTATUS_USINGCACHEDCOPY | Bağlama işlemi, önbellekteki bir kopyadan istenen nesneyi veya depolamayı alıyor. *SzStatusText* null. |
| BINDSTATUS_BEGINDOWNLOADDATA | Bağlama işlemi, bağlı olan nesne veya depolamayı almaya başladı. *SzStatusText* , veri konumunun görünen adını sağlar. |
| BINDSTATUS_DOWNLOADINGDATA | Bağlama işlemi, bağlanan nesne veya depolamayı almaya devam eder. *SzStatusText* , veri konumunun görünen adını sağlar. |
| BINDSTATUS_ENDDOWNLOADDATA | Bağlama işlemi, bağlanan nesne veya depolama alanını almayı tamamladı. *SzStatusText* , veri konumunun görünen adını sağlar. |
| BINDSTATUS_CLASSIDAVAILABLE | Bağlanmakta olan nesnenin bir örneği yalnızca oluşturulması için. *SzStatusText* , dize biçiminde yeni nesnenin CLSID değerini sağlar ve isterseniz, bağlantı işlemini iptal etmek için istemciye izin verir. |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a> CAsyncMonikerFile:: OnStartBinding

Bağlama başlatıldığında eylemler gerçekleştirmek için türetilmiş sınıflarınızda bu işlevi geçersiz kılın.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev ad tarafından geri çağırılır. Varsayılan uygulama hiçbir şey yapmaz.

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a> CAsyncMonikerFile:: OnStopBinding

Bağlama işleminin sonundaki bilinen ad tarafından çağırılır.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Parametreler

*HRESULT*<br/>
Hata veya uyarı değeri olan bir HRESULT.

*szErrort*<br/>
Hatayı açıklayan bir karakter dizesi.

### <a name="remarks"></a>Açıklamalar

Aktarım durdurulduğunda işlemleri gerçekleştirmek için bu işlevi geçersiz kılın. Varsayılan olarak işlev yayınlar `IBinding` .

Arabirimin açıklaması için `IBinding` bkz. Windows SDK.

## <a name="casyncmonikerfileopen"></a><a name="open"></a> CAsyncMonikerFile:: Open

Bir dosyayı zaman uyumsuz olarak açmak için bu üye işlevini çağırın.

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

*lpszURL*<br/>
Dosyanın zaman uyumsuz olarak açılmasını sağlamak için bir işaretçi. Dosya herhangi bir geçerli URL veya dosya adı olabilir.

*pError*<br/>
Dosya özel durumlarına yönelik bir işaretçi. Bir hata durumunda, nedeni olarak ayarlanır.

*Pbilinen*<br/>
Zaman uyumsuz bilinen ad arabirimine yönelik bir işaretçi `IMoniker` , belgenin kendi bilinen adının birleşimi olan, ile alabileceğiniz `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)` ve yol adından oluşturulan bir ad olan kesin bir addır. Denetim, bu bilinen adı bağlamak için kullanabilir, ancak bu, denetimin kaydetmesi gereken addır.

*pBindHost*<br/>
`IBindHost`Potansiyel olarak göreli bir yol adındaki bilinen adı oluşturmak için kullanılacak arabirime yönelik bir işaretçi. Bağlama Konağı geçersizse veya bir ad sağlamıyorsa, çağrının varsayılan değeri olarak ayarlanır `Open(lpszFileName,pError)` . Arabirimin açıklaması için `IBindHost` bkz. Windows SDK.

*pServiceProvider*<br/>
Arabirime yönelik bir işaretçi `IServiceProvider` . Hizmet sağlayıcısı geçersiz veya hizmeti sağlayamazsa `IBindHost` , arama varsayılan olarak olur `Open(lpszFileName,pError)` .

*pUnknown*<br/>
Arabirime yönelik bir işaretçi `IUnknown` . `IServiceProvider`Bulunursa, işlevi için sorgular `IBindHost` . Hizmet sağlayıcısı geçersiz veya hizmeti sağlayamazsa `IBindHost` , arama varsayılan olarak olur `Open(lpszFileName,pError)` .

### <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla açılırsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu çağrı bağlama işlemini başlatır.

*LpszURL* parametresi IÇIN bir URL veya dosya adı kullanabilirsiniz. Örnek:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- veya

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPathProperty sınıfı](../../mfc/reference/cdatapathproperty-class.md)
