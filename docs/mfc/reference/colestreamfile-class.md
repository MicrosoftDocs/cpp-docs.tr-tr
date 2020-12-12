---
description: 'Daha fazla bilgi edinin: Cotastreamfile sınıfı'
title: Cotastreamfile sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: b856dc5b408c43f61a11f7c68035587bc16bbeaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226642"
---
# <a name="colestreamfile-class"></a>Cotastreamfile sınıfı

Birleşik dosyadaki bir veri akışını `IStream` OLE yapılandırılmış depolamanın bir parçası olarak temsil eder.

## <a name="syntax"></a>Syntax

```
class COleStreamFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotastreamfile:: Copastreamfile](#colestreamfile)|Bir `COleStreamFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotastreamfile:: Attach](#attach)|Bir akışı nesneyle ilişkilendirir.|
|[Cotastreamfile:: CreateMemoryStream](#creatememorystream)|Genel bellekten bir akış oluşturur ve nesneyle ilişkilendirir.|
|[Cotastreamfile:: CreateStream](#createstream)|Bir akış oluşturur ve nesneyle ilişkilendirir.|
|[Cotastreamfile::D etach](#detach)|Akışın nesneden ilişkilendirmesini kaldırır.|
|[Cotastreamfile:: GetStream](#getstream)|Geçerli akışı döndürür.|
|[Cotastreamfile:: OpenStream](#openstream)|Güvenli bir şekilde akış açar ve nesneyle ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

`IStorage`Bir nesne, bir bellek akışı olmadığı takdirde, akışın açılabilmesi veya oluşturulabilmesi için mevcut olmalıdır.

`COleStreamFile` nesneler, tam olarak [CFile](../../mfc/reference/cfile-class.md) nesneleri gibi işlenir.

Akışları ve depolarını düzenleme hakkında daha fazla bilgi için bkz. [kapsayıcı: bileşik dosyalar](../../mfc/containers-compound-files.md)..

Daha fazla bilgi için Windows SDK bkz. [IStream](/windows/win32/api/objidl/nn-objidl-istream) ve [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="colestreamfileattach"></a><a name="attach"></a> Cotastreamfile:: Attach

Sağlanan OLE akışını `COleStreamFile` nesnesiyle ilişkilendirir.

```cpp
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
Nesneyle ilişkilendirilecek OLE akışına () işaret eder `IStream` . NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Nesne zaten bir OLE akışıyla ilişkilendirilmemiş olmalıdır.

Daha fazla bilgi için Windows SDK [IStream](/windows/win32/api/objidl/nn-objidl-istream) bölümüne bakın.

## <a name="colestreamfilecolestreamfile"></a><a name="colestreamfile"></a> Cotastreamfile:: Copastreamfile

Bir `COleStreamFile` nesnesi oluşturur.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
Nesneyle ilişkilendirilecek OLE akışının işaretçisi.

### <a name="remarks"></a>Açıklamalar

*LPSTREAM* null ise, nesne OLE akışıyla ilişkilendirilmez, aksi takdirde nesne sağlanan ole akışıyla ilişkilendirilir.

Daha fazla bilgi için Windows SDK [IStream](/windows/win32/api/objidl/nn-objidl-istream) bölümüne bakın.

## <a name="colestreamfilecreatememorystream"></a><a name="creatememorystream"></a> Cotastreamfile:: CreateMemoryStream

Güvenli bir şekilde, bir hatanın normal, beklenen bir koşula göre genel, paylaşılan bellek dışında yeni bir akış oluşturur.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pError*<br/>
Oluşturma işleminin tamamlanma durumunu gösteren bir [CFileException](../../mfc/reference/cfileexception-class.md) NESNESINE veya null öğesine işaret eder. Akışı oluşturmaya çalışırken oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturulursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bellek, OLE alt sistemi tarafından ayrılır.

Daha fazla bilgi için Windows SDK bkz. [CreateStreamOnHGlobal](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal) .

## <a name="colestreamfilecreatestream"></a><a name="createstream"></a> Cotastreamfile:: CreateStream

Güvenli bir şekilde, bir hatanın normal, beklenen bir koşul olduğu belirtilen depolama nesnesinde yeni bir akış oluşturur.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStorage*<br/>
Oluşturulacak akışı içeren OLE Storage nesnesine işaret eder. NULL olamaz.

*lpszStreamName*<br/>
Oluşturulacak akışın adı. NULL olamaz.

*nOpenFlags*<br/>
Akış açılırken kullanılacak erişim modu. Dışlamalı, okuma/yazma ve oluşturma modları varsayılan olarak kullanılır. Kullanılabilir modların tüm listesi için bkz. [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Bir [CFileException](../../mfc/reference/cfileexception-class.md) NESNESINE veya null öğesine işaret eder. Akışı oluşturmaya çalışırken oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturulursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Open başarısız olursa ve *pError* null değilse bir dosya özel durumu oluşturulur.

Daha fazla bilgi için Windows SDK [IStorage:: CreateStream](/windows/win32/api/objidl/nf-objidl-istorage-createstream) bölümüne bakın.

## <a name="colestreamfiledetach"></a><a name="detach"></a> Cotastreamfile::D etach

Akışı kapatmadan akışı nesneden ilişkilendirir.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili akışa () yönelik bir işaretçi `IStream` .

### <a name="remarks"></a>Açıklamalar

Program sonlandırılmadan önce akışın başka bir şekilde kapatılması gerekir.

Daha fazla bilgi için Windows SDK [IStream](/windows/win32/api/objidl/nn-objidl-istream) bölümüne bakın.

## <a name="colestreamfilegetstream"></a><a name="getstream"></a> Cotastreamfile:: GetStream

Geçerli akışa bir işaretçi döndürmek için bu işlevi çağırın.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli akış arabirimine ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) yönelik bir işaretçi.

## <a name="colestreamfileopenstream"></a><a name="openstream"></a> Cotastreamfile:: OpenStream

Mevcut bir akışı açar.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStorage*<br/>
Açılacak akışı içeren OLE Storage nesnesine işaret eder. NULL olamaz.

*lpszStreamName*<br/>
Açılacak akışın adı. NULL olamaz.

*nOpenFlags*<br/>
Akış açılırken kullanılacak erişim modu. Özel ve okuma/yazma modları varsayılan olarak kullanılır. Kullanılabilir modların tüm listesi için bkz. [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Bir [CFileException](../../mfc/reference/cfileexception-class.md) NESNESINE veya null öğesine işaret eder. Akışı açmaya çalışırken oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla açılırsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Open başarısız olursa ve *pError* null değilse bir dosya özel durumu oluşturulur.

Daha fazla bilgi için Windows SDK [IStorage:: OpenStream](/windows/win32/api/objidl/nf-objidl-istorage-openstream) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
