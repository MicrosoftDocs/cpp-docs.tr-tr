---
title: COleStreamFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4425732f35b711b052675c3d1a00746c04a1d538
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075053"
---
# <a name="colestreamfile-class"></a>COleStreamFile sınıfı

Veri akışını temsil eder (`IStream`) OLE yapılı depolama bir parçası olarak birleşik bir dosyadaki.

## <a name="syntax"></a>Sözdizimi

```
class COleStreamFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleStreamFile::COleStreamFile](#colestreamfile)|Oluşturur bir `COleStreamFile` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleStreamFile::Attach](#attach)|Bir akış nesnesi ile ilişkilendirir.|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Genel bellekten bir akış oluşturur ve nesnesiyle ilişkilendirir.|
|[COleStreamFile::CreateStream](#createstream)|Bir akış oluşturur ve nesnesiyle ilişkilendirir.|
|[COleStreamFile::Detach](#detach)|Nesne akışından ayırır.|
|[COleStreamFile::GetStream](#getstream)|Geçerli akışı döndürür.|
|[COleStreamFile::OpenStream](#openstream)|Güvenli bir akış açılır ve nesnesi ile ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

Bir `IStorage` nesne akışı açılamıyor veya bellek akışı olmadığı sürece oluşturulan önce bulunmalıdır.

`COleStreamFile` nesneleri yönetilen tıpkı [CFile](../../mfc/reference/cfile-class.md) nesneleri.

Akışları ve depolamayı düzenleme hakkında daha fazla bilgi için bkz [kapsayıcılar: bileşik dosyalar](../../mfc/containers-compound-files.md)...

Daha fazla bilgi için [IStream](/windows/desktop/api/objidl/nn-objidl-istream) ve [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="attach"></a>  COleStreamFile::Attach

Sağlanan OLE akış ile ilişkilendirir `COleStreamFile` nesne.

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
OLE akışa işaret (`IStream`) nesne ile ilişkilendirilecek. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Nesne zaten bir OLE akışı ile ilişkili olmamalıdır.

Daha fazla bilgi için [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK.

##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile

Oluşturur bir `COleStreamFile` nesne.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStream*<br/>
OLE akış nesne ile ilişkilendirilmesi için işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsa *lpStream* null, nesne bir OLE akışı ile ilişkili değil, aksi takdirde, nesne sağlanan OLE akış ile ilişkilidir.

Daha fazla bilgi için [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK.

##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream

Güvenli bir şekilde hata normal, beklenen bir koşulu olduğu yeni bir akışı küresel, paylaşılan bellek yetersiz oluşturur.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pError*<br/>
İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne ya da oluşturma işleminin tamamlanma durumunu gösteren NULL. Akış oluşturma denemesi ile oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlar.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bellek OLE alt sistemi tarafından ayrılır.

Daha fazla bilgi için [CreateStreamOnHGlobal](/windows/desktop/api/combaseapi/nf-combaseapi-createstreamonhglobal) Windows SDK.

##  <a name="createstream"></a>  COleStreamFile::CreateStream

Güvenli bir şekilde yeni bir akış sağlanan depolama nesnesinde bir hata normal, beklenen bir koşulu olduğu oluşturur.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStorage*<br/>
Oluşturulacak akış içeren OLE depolama nesneyi işaret eder. NULL olamaz.

*lpszStreamName*<br/>
Oluşturulacak Akış adı. NULL olamaz.

*nOpenFlags*<br/>
Erişim modu, akış açılırken kullanılacak. Özel, okuma/yazma ve oluşturma modu varsayılan olarak kullanılır. Kullanılabilir modları tam bir listesi için bkz. [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne veya NULL. Akış oluşturma denemesi ile oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlar.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Açık başarısız olursa, bir dosya özel durum oluşturulur ve *pError* NULL değil.

Daha fazla bilgi için [IStorage::CreateStream](/windows/desktop/api/objidl/nf-objidl-istorage-createstream) Windows SDK.

##  <a name="detach"></a>  COleStreamFile::Detach

Nesne akıştan akış kapatmadan ayırır.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Akış için bir işaretçi (`IStream`), nesneyle ilişkili.

### <a name="remarks"></a>Açıklamalar

Akış program sona erdirmeden önce bazı başka bir biçimde kapatılması gerekir.

Daha fazla bilgi için [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK.

##  <a name="getstream"></a>  COleStreamFile::GetStream

Geçerli akışa bir işaretçiyi döndürmek için bu işlevi çağırın.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli akışı arabirim işaretçisi ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)).

##  <a name="openstream"></a>  COleStreamFile::OpenStream

Var olan bir akışı açılır.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpStorage*<br/>
Açılacak akışın içeren OLE depolama nesneyi işaret eder. NULL olamaz.

*lpszStreamName*<br/>
Açılacak akışın adı. NULL olamaz.

*nOpenFlags*<br/>
Erişim modu, akış açılırken kullanılacak. Özel ve okuma/yazma modu, varsayılan olarak kullanılır. Kullanılabilir modları tam listesi için bkz. [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne veya NULL. Akış açmaya tarafından oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlar.

### <a name="return-value"></a>Dönüş Değeri

Akış başarıyla açıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Açık başarısız olursa, bir dosya özel durum oluşturulur ve *pError* NULL değil.

Daha fazla bilgi için [IStorage::OpenStream](/windows/desktop/api/objidl/nf-objidl-istorage-openstream) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

