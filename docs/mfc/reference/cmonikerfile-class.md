---
description: 'Daha fazla bilgi edinin: CMonikerFile Class'
title: CMonikerFile sınıfı
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
ms.openlocfilehash: d59de05f688c10d3dbfa6682777d5fd11d4f53ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331588"
---
# <a name="cmonikerfile-class"></a>CMonikerFile sınıfı

Bir [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)tarafından adlandırılan veri akışını ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) temsil eder.

## <a name="syntax"></a>Syntax

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Bir `CMonikerFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMonikerFile:: Close](#close)|Akışı ayırır ve yayınlar ve bilinen adı yayınlar.|
|[CMonikerFile::D etach](#detach)|`IMoniker`Bu `CMonikerFile` nesneden ayırır.|
|[CMonikerFile:: Getbilinen ad](#getmoniker)|Geçerli bilinen adı döndürür.|
|[CMonikerFile:: Open](#open)|Bir akış almak için belirtilen dosyayı açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMonikerFile:: CreateBindContext](#createbindcontext)|Bağlama bağlamını alır veya varsayılan bir başlatılmış bağlama bağlamı oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bilinen ad, bir dosyanın yol adı gibi bilgileri içerir. Bilinen ad nesnesinin arabirimine yönelik bir işaretçiniz varsa `IMoniker` , dosyanın aslında bulunduğu konum hakkında başka herhangi bir bilgi sahibi olmadan tanımlı dosyaya erişim sağlayabilirsiniz.

Öğesinden türetilmiş `COleStreamFile` , bilinen `CMonikerFile` bir ad veya dize temsili alır ve bilinen adın adı olduğu akışa bağlanır. Daha sonra bu akışı okuyabilir ve yazabilirsiniz. ' Nin gerçek amacı, `CMonikerFile` `IStream` `IMoniker` ' a bir akışa bağlanmak zorunda kalmaması, ancak `CFile` akışa işlevsellik sağlamanız gerekmez.

`CMonikerFile` Stream dışında bir şeye bağlamak için kullanılamaz. Depolama alanı veya bir nesneye bağlamak istiyorsanız, `IMoniker` arabirimi doğrudan kullanmanız gerekir.

Akışlar ve takma adlar hakkında daha fazla bilgi için, Windows SDK *MFC başvurusu* ve [ıstreamve](/windows/win32/api/objidl/nn-objidl-istream) [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) Içindeki [coperstreamfile](../../mfc/reference/colestreamfile-class.md) ' a bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[Cotastreamfile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="cmonikerfileclose"></a><a name="close"></a> CMonikerFile:: Close

Akışı ayırmak ve serbest bırakmak ve bilinen adı bırakmak için bu işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açık olmayan veya zaten kapalı akışlar üzerinde çağrılabilir.

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a> CMonikerFile::CMonikerFile

Bir `CMonikerFile` nesnesi oluşturur.

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a> CMonikerFile:: CreateBindContext

Varsayılan bir başlatılmış bağlama bağlamı oluşturmak için bu işlevi çağırın.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Parametreler

*pError*<br/>
Bir dosya özel durumunun işaretçisi. Bir hata durumunda, nedeni olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bağlama bağlamı [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) için bir işaretçi; Aksi takdirde NULL. Örnek bir arabirim ile açılırsa, `IBindHost` bağlama bağlamı öğesinden alınır `IBindHost` . `IBindHost`Arabirim yoksa veya arabirim bir bağlama bağlamı döndürmediğinde, bir bağlama bağlamı oluşturulur. [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\)) arabiriminin açıklaması için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

Bağlama bağlamı, belirli bir bilinen ad bağlama işlemi hakkında bilgi depolayan bir nesnedir. Özel bir bağlama bağlamı sağlamak için bu işlevi geçersiz kılabilirsiniz.

## <a name="cmonikerfiledetach"></a><a name="detach"></a> CMonikerFile::D etach

Akışı kapatmak için bu işlevi çağırın.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pError*<br/>
Bir dosya özel durumunun işaretçisi. Bir hata durumunda, nedeni olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a> CMonikerFile:: Getbilinen ad

Geçerli bilinen bir işaretçi almak için bu işlevi çağırın.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bilinen ad arabirimine ( [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)) yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CMonikerFile`Bir arabirim olmadığından, döndürülen işaretçi başvuru sayısını ( [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)aracılığıyla) artırmaz ve bu ad, nesne serbest bırakıldığında serbest bırakılır `CMonikerFile` . Bilinen ad üzerinde tutmak veya kendiniz yayınlamak istiyorsanız, bunu yapmanız gerekir `AddRef` .

## <a name="cmonikerfileopen"></a><a name="open"></a> CMonikerFile:: Open

Bir dosya veya bilinen ad nesnesini açmak için bu üye işlevini çağırın.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
Açılacak dosyanın URL 'SI veya dosya adı.

*pError*<br/>
Bir dosya özel durumunun işaretçisi. Bir hata durumunda, nedeni olarak ayarlanır.

*Pbilinen*<br/>
Bir akış elde etmek için kullanılacak bilinen ad arabirimine yönelik bir işaretçi `IMoniker` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpszURL* parametresi bir Macintosh üzerinde kullanılamaz. Bir Macintosh üzerinde yalnızca *Pbilinen* biçimi `Open` kullanılabilir.

*LpszURL* parametresi IÇIN bir URL veya dosya adı kullanabilirsiniz. Örneğin:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- veya

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Cotastreamfile sınıfı](../../mfc/reference/colestreamfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
