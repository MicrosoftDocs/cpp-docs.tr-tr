---
title: CMonikerFile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: fc74ad2499fcde63faa2c5859a87fd9ffd2846eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319781"
---
# <a name="cmonikerfile-class"></a>CMonikerFile Sınıfı

Bir [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)tarafından adlandırılan bir veri akışını [(IStream)](/windows/win32/api/objidl/nn-objidl-istream)temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Bir `CMonikerFile` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMonikerFile::Kapat](#close)|Akışı ayırır ve serbest bırakır ve lakabı serbest bırakır.|
|[CMonikerDosya::Detach](#detach)|Bu `CMonikerFile` nesneden `IMoniker` ayırın.|
|[CMonikerFile::GetMoniker](#getmoniker)|Geçerli takma adacını döndürür.|
|[CMonikerFile::Aç](#open)|Akış almak için belirtilen dosyayı açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|Bağlama bağlamını alır veya varsayılan başharf bağlama bağlamı oluşturur.|

## <a name="remarks"></a>Açıklamalar

Takma ad, dosyaya giden yol adı gibi bilgiler içerir. Bir takma adın nesnesinin `IMoniker` arabirimine işaretçiniz varsa, dosyanın gerçekte nerede bulunduğu hakkında başka özel bilgilere sahip olmadan tanımlanan dosyaya erişebilirsiniz.

`COleStreamFile`Türetilen, `CMonikerFile` bir takma ad veya bir takma ad içine yapabilir ve takma ad bir ad olduğu akışına bağlar bir dize gösterimi alır. Daha sonra okuyup bu akışa yazabilirsiniz. Gerçek amacı, `CMonikerFile` bir akışa `IStream`kendiniz bağlamak `IMoniker`zorunda kalmamak, ancak akışa işlevsellik sağlamak `CFile` için s tarafından adlandırılan s basit erişim sağlamaktır.

`CMonikerFile`akış tan başka bir şeye bağlamak için kullanılamaz. Depolama alanına veya bir nesneye bağlamak istiyorsanız, `IMoniker` arabirimi doğrudan kullanmanız gerekir.

Akışlar ve monikerler hakkında daha fazla bilgi için, Windows SDK'daki *MFC Reference'da* [COleStreamFile](../../mfc/reference/colestreamfile-class.md) ve [IStream](/windows/win32/api/objidl/nn-objidl-istream) ve [IMoniker'a](/windows/win32/api/objidl/nn-objidl-imoniker) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="cmonikerfileclose"></a><a name="close"></a>CMonikerFile::Kapat

Akışı ayırmak ve serbest bırakmak ve lakabı serbest bırakmak için bu işlevi arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açılmamış veya zaten kapalı olan akışlara çağrılabilir.

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>CMonikerFile::CMonikerFile

Bir `CMonikerFile` nesne inşa eder.

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>CMonikerFile::CreateBindContext

Varsayılan başharf bağlama bağlamı oluşturmak için bu işlevi çağırın.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Parametreler

*pHata*<br/>
Dosya özel durum için bir işaretçi. Bir hata durumunda, neden olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Bağlama bağlamı [IBindCtx'in](/windows/win32/api/objidl/nn-objidl-ibindctx) başarılı olursa ile bağdatmak için işaretçisi; aksi takdirde NULL. Örnek bir `IBindHost` arabirimle açıldıysa, bağlama bağlamı `IBindHost`. Arabirim yoksa `IBindHost` veya arabirim bağlama bağlamını döndürmezse, bağlama bağlamı oluşturulur. [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\)) arabiriminin açıklaması için Windows SDK'ya bakın.

### <a name="remarks"></a>Açıklamalar

Bağlama bağlamı, belirli bir takma alma bağlama işlemi hakkında bilgi depolayan bir nesnedir. Özel bağlama bağlamı sağlamak için bu işlevi geçersiz kılabilirsiniz.

## <a name="cmonikerfiledetach"></a><a name="detach"></a>CMonikerDosya::Detach

Akışı kapatmak için bu işlevi arayın.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pHata*<br/>
Dosya özel durum için bir işaretçi. Bir hata durumunda, neden olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a>CMonikerFile::GetMoniker

Geçerli takma alaişaret almak için bu işlevi çağırın.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli takma arabirimi [(IMoniker)](/windows/win32/api/objidl/nn-objidl-imoniker)için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Arabirim olmadığından, döndürülen işaretçi başvuru sayısını [(AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)aracılığıyla) artımaz ve `CMonikerFile` nesne serbest bırakıldığında takma adı serbest bırakılır. `CMonikerFile` Lakabını tutmak ya da kendiniz serbest bırakmak istiyorsanız, `AddRef` bunu yapmalısınız.

## <a name="cmonikerfileopen"></a><a name="open"></a>CMonikerFile::Aç

Bir dosya veya takma adlandırma nesnesi açmak için bu üye işlevi arayın.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
Açılacak dosyanın URL'si veya dosya adı.

*pHata*<br/>
Dosya özel durum için bir işaretçi. Bir hata durumunda, neden olarak ayarlanır.

*pMoniker*<br/>
Bir akış elde etmek için `IMoniker` kullanılacak takma abiriara bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpszURL* parametresi Macintosh'ta kullanılamaz. Macintosh'ta sadece *pMoniker* formu `Open` kullanılabilir.

*LPSZURL* parametresi için bir URL veya dosya adı kullanabilirsiniz. Örneğin:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\-veya -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[COleStreamFile Sınıfı](../../mfc/reference/colestreamfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
