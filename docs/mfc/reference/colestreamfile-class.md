---
title: COleStreamFile Sınıfı
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
ms.openlocfilehash: 202f8381361881ce3b8b62f81da5bfb81a1f952d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753750"
---
# <a name="colestreamfile-class"></a>COleStreamFile Sınıfı

OLE Structured Storage'ın bir parçası olarak bileşik dosyadaki veri akışını ( )`IStream`temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleStreamFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleStreamFile::COleStreamFile](#colestreamfile)|Bir `COleStreamFile` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleStreamFile::Ekle](#attach)|Akışı nesneyle ilişkilendirer.|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Genel bellekten bir akış oluşturur ve nesneyle ilişkilendirer.|
|[COleStreamFile::CreateStream](#createstream)|Bir akış oluşturur ve nesneyle ilişkilendirer.|
|[COleStreamFile::Detach](#detach)|Nesneydeki akışı silkeler.|
|[COleStreamFile::GetStream](#getstream)|Geçerli akışı döndürür.|
|[COleStreamFile::OpenStream](#openstream)|Güvenli bir şekilde bir akış açar ve nesne ile ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

Bir `IStorage` bellek akışı olmadığı sürece akış açılabilir veya oluşturulabilir önce bir nesne var olmalıdır.

`COleStreamFile`nesneler [cfile](../../mfc/reference/cfile-class.md) nesneleri gibi tam olarak manipüle edilir.

Akışları ve depolama ları manipüle etme hakkında daha fazla bilgi için [Kapsayıcılar: Bileşik Dosyalar](../../mfc/containers-compound-files.md)makalesine bakın...

Daha fazla bilgi için Windows SDK'daki [IStream](/windows/win32/api/objidl/nn-objidl-istream) ve [IStorage'a](/windows/win32/api/objidl/nn-objidl-istorage) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="colestreamfileattach"></a><a name="attach"></a>COleStreamFile::Ekle

Sağlanan OLE akışını `COleStreamFile` nesneyle ilişkilendirer.

```cpp
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
Nesneyle ilişkilendirilecek OLE akışına (`IStream`) işaret eder. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Nesne zaten bir OLE akışı ile ilişkili olmamalıdır.

Daha fazla bilgi için Windows SDK'daki [IStream'e](/windows/win32/api/objidl/nn-objidl-istream) bakın.

## <a name="colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>COleStreamFile::COleStreamFile

Bir `COleStreamFile` nesnesi oluşturur.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
Nesneyle ilişkilendirilecek OLE akışına işaretçi.

### <a name="remarks"></a>Açıklamalar

*lpStream* NULL ise, nesne bir OLE akışı ile ilişkili değildir, aksi takdirde, nesne sağlanan OLE akışı ile ilişkilidir.

Daha fazla bilgi için Windows SDK'daki [IStream'e](/windows/win32/api/objidl/nn-objidl-istream) bakın.

## <a name="colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream

Güvenli bir şekilde bir hata normal, beklenen bir durum olduğu genel, paylaşılan bellek ten yeni bir akış oluşturur.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pHata*<br/>
Oluşturma işleminin tamamlanma durumunu gösteren bir [CFileException](../../mfc/reference/cfileexception-class.md) nesnesine veya NULL'a işaret edin. Akışı oluşturmaya çalışarak oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi verin.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturulursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bellek OLE alt sistemi tarafından ayrılır.

Daha fazla bilgi için Windows SDK'daki [CreateStreamOnHGlobal'a](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal) bakın.

## <a name="colestreamfilecreatestream"></a><a name="createstream"></a>COleStreamFile::CreateStream

Güvenli bir şekilde bir hata normal, beklenen durum olduğu sağlanan depolama nesnesinde yeni bir akış oluşturur.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpDepolama*<br/>
Oluşturulacak akışı içeren OLE depolama nesnesine işaret ediyor. NULL olamaz.

*lpszStreamName*<br/>
Oluşturulacak akışın adı. NULL olamaz.

*nOpen Bayraklar*<br/>
Akışı açarken kullanılacak erişim modu. Özel, okuma/yazma ve oluşturma modları varsayılan olarak kullanılır. Kullanılabilir modların tam listesi için [Bkz. CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pHata*<br/>
[CFileException](../../mfc/reference/cfileexception-class.md) nesnesine veya NULL'a işaret edin. Akışı oluşturmaya çalışarak oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi verin.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturulursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Açık başarısız olursa ve *pError* NULL değilse bir dosya özel durum atılır.

Daha fazla bilgi için Bkz. [IStorage::Windows](/windows/win32/api/objidl/nf-objidl-istorage-createstream) SDK'da CreateStream.

## <a name="colestreamfiledetach"></a><a name="detach"></a>COleStreamFile::Detach

Akışı kapatmadan nesneyi uzaklaştırın.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili akış`IStream`( ) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Program sona ermeden önce akış başka bir şekilde kapatılmalıdır.

Daha fazla bilgi için Windows SDK'daki [IStream'e](/windows/win32/api/objidl/nn-objidl-istream) bakın.

## <a name="colestreamfilegetstream"></a><a name="getstream"></a>COleStreamFile::GetStream

Bir işaretçiyi geçerli akışa döndürmek için bu işlevi çağırın.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli akış arabirimi [(IStream)](/windows/win32/api/objidl/nn-objidl-istream)için bir işaretçi.

## <a name="colestreamfileopenstream"></a><a name="openstream"></a>COleStreamFile::OpenStream

Varolan bir akışı açar.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpDepolama*<br/>
Açılacak akışı içeren OLE depolama nesnesine işaret ediyor. NULL olamaz.

*lpszStreamName*<br/>
Açılacak akışın adı. NULL olamaz.

*nOpen Bayraklar*<br/>
Akışı açarken kullanılacak erişim modu. Özel ve okuma/yazma modları varsayılan olarak kullanılır. Kullanılabilir modların tam listesi için [Bkz. CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pHata*<br/>
[CFileException](../../mfc/reference/cfileexception-class.md) nesnesine veya NULL'a işaret edin. Akışı açmaya çalışarak oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi verin.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla açılırsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Açık başarısız olursa ve *pError* NULL değilse bir dosya özel durum atılır.

Daha fazla bilgi için [Bkz. IStorage::Windows](/windows/win32/api/objidl/nf-objidl-istorage-openstream) SDK'da OpenStream.

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
