---
title: CFileException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: a3514c76d4136fe2bc0b096cc382e6f7f4dd3392
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305126"
---
# <a name="cfileexception-class"></a>CFileException sınıfı

Bir dosya ile ilgili özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CFileException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileException::CFileException](#cfileexception)|Oluşturur bir `CFileException` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|Döndürür bir çalışma zamanı hata numarasına karşılık gelen kod neden.|
|[CFileException::GetErrorMessage](#geterrormessage)|Bir özel durumu açıklayan ileti alır.|
|[CFileException::OsErrorToException](#oserrortoexception)|Bir işletim sistemi hata koduna karşılık gelen bir neden kodu döndürür.|
|[CFileException::ThrowErrno](#throwerrno)|Bir çalışma zamanı hatası sayısına göre bir dosya özel durum oluşturur.|
|[CFileException::ThrowOsError](#throwoserror)|Bir işletim sistemi hata numarasına göre bir dosya özel durum oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|Özel durum neden karşılık gelen taşınabilir kod içerir.|
|[CFileException::m_lOsError](#m_loserror)|İlgili işletim sistemi hata numarasını içermektedir.|
|[CFileException::m_strFileName](#m_strfilename)|Bu özel durumun dosya adını içerir.|

## <a name="remarks"></a>Açıklamalar

`CFileException` Sınıfı taşınabilir neden kodu ve işletim sistemine özgü hata numarası tutun genel veri üyelerini içerir. Sınıf dosyası özel durumları atma ve işletim sistemi hataları hem C çalışma zamanı hatalarına neden kodları döndürme için statik üye işlevleri de sağlar.

`CFileException` nesneleri oluşturulur ve oluşturulan `CFile` üye işlevleri ve türetilmiş sınıflarının üye işlevleri. Bu nesneler kapsamında erişebileceğiniz bir **CATCH** ifade. Taşınabilirlik için neden kodu olarak yalnızca bir özel durum nedeni almak için kullanın. Özel durumları hakkında daha fazla bilgi için bkz [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cfileexception"></a>  CFileException::CFileException

Oluşturur bir `CFileException` nesnesini neden kodu ve işletim sistemi kodunu depolar.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*Bunun nedeni*<br/>
Özel durumun nedenini gösteren bir listeden seçimli türü değişkeni. Bkz: [CFileException::m_cause](#m_cause) olası değerler listesi.

*lOsError*<br/>
Varsa özel durumun bir işletim sistemine özgü açıklaması. *LOsError* parametresini daha fazla bilgi sağlayan *neden* yapar.

*lpszArchiveName*<br/>
İşaret adı içeren bir dizeye `CFile` özel duruma neden olan nesne.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan kullanmaz, bunun yerine genel işlev çağrısı [AfxThrowFileException](exception-processing.md#afxthrowfileexception).

> [!NOTE]
>  Değişken *lOsError* yalnızca geçerli `CFile` ve `CStdioFile` nesneleri. `CMemFile` Sınıfı, bu hata kodu işlemez.

##  <a name="errnotoexception"></a>  CFileException::ErrnoToException

Belirtilen çalışma zamanı kitaplığı hata değerine dönüştürür bir `CFileException` numaralandırılmış hata değeri.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
ERRNO çalışma zamanı içerme dosyasında tanımlanan bir tamsayı hata kodu. H

### <a name="return-value"></a>Dönüş Değeri

Belirtilen çalışma zamanı kitaplığı hata değerine karşılık gelen numaralandırılmış değer.

### <a name="remarks"></a>Açıklamalar

Bkz: [CFileException::m_cause](#m_cause) olası bir listesi için listeden seçimli değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage

Bir özel durumu açıklayan metni alır.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszError*<br/>
[out içinde] Bir hata iletisi alan arabellek için işaretçi.

*nMaxError*<br/>
[in] Belirtilen arabellek tutabilir karakter sayısı. Bu sondaki boş karakter içerir.

*pnHelpContext*<br/>
[out içinde] Yardım içeriği kimliği alır, işaretsiz bir tamsayı işaretçisi Varsa `NULL`, hiçbir kimliği döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Hata iletisinde belirtilen arabellek çok küçük ise kesilir.

### <a name="example"></a>Örnek

Aşağıdaki örnekte `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>  CFileException::m_cause

Tarafından tanımlanan değerleri içeren bir `CFileException` listelenmiş türü.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi türünün genel bir değişkendir **int**. Numaralandırıcılar ve bunların anlamlarını açıklayan aşağıdaki gibidir:

- `CFileException::none` 0: Herhangi bir hata oluştu.

- `CFileException::genericException` 1: Belirtilmeyen bir hata oluştu.

- `CFileException::fileNotFound` 2: Dosya bulunamadı.

- `CFileException::badPath` 3: Yolun bir bölümünü veya tümünü geçersiz.

- `CFileException::tooManyOpenFiles` 4: İzin verilen açık dosya sayısı aşıldı.

- `CFileException::accessDenied` 5: Dosyaya erişilemedi.

- `CFileException::invalidFile` 6: Geçersiz bir dosya işlemesi kullanma girişimi oldu.

- `CFileException::removeCurrentDir` 7: Geçerli çalışma dizini kaldırılamıyor.

- `CFileException::directoryFull` 8: Başka dizin girdisi yok vardır.

- `CFileException::badSeek` 9: Dosya işaretçisini ayarlamaya çalışırken bir hata oluştu.

- `CFileException::hardIO` 10: Bir donanım hatası oluştu.

- `CFileException::sharingViolation` 11: Paylaş. EXE yüklü değildi veya paylaşılan bölge kilitliydi.

- `CFileException::lockViolation` 12: Zaten kilitli olan bölge kilitlenmeye girişimi oldu.

- `CFileException::diskFull` 14: Disk dolu.

- `CFileException::endOfFile` 15: Dosya sonuna ulaşıldı.

    > [!NOTE]
    >  Bunlar `CFileException` neden numaralandırıcılar kodundan `CArchiveException` numaralandırıcılar neden olur.

    > [!NOTE]
    > `CArchiveException::generic` kullanım dışı bırakılmıştır. Bunun yerine `genericException` kullanın. Varsa **genel** bir uygulamada kullanılan ve yerleşik/CLR ile sonuçta elde edilen sözdizimi hataları çözmek kolay değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>  CFileException::m_lOsError

Bu özel işletim sistemi hata kodunu içerir.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Açıklamalar

İşletim sistemi teknik kılavuzunuza hata kodlarının listesi için bkz. Bu veri türü bir genel değişken uzun üyesidir.

##  <a name="m_strfilename"></a>  CFileException::m_strFileName

Bu özel durum koşulunu için dosya adını içerir.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException

Karşılık gelen bir numaralandırıcı döndürür bir verilen *lOsError* değeri. Hata kodu bilinmiyor sonra işlevi döndürür `CFileException::generic`.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
Bir işletim sistemine özgü hata kodu.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen işletim sistemi hata değerine karşılık gelen numaralandırılmış değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>  CFileException::ThrowErrno

Oluşturur bir `CFileException` nesne karşılık gelen bir verilen *nErrno* değerini ve özel durum oluşturur.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
ERRNO çalışma zamanı içerme dosyasında tanımlanan bir tamsayı hata kodu. H

*lpszFileName*<br/>
Dosya adını içeren dize işaretçisi varsa özel durum neden.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>  CFileException::ThrowOsError

Oluşturur bir `CFileException` karşılık gelen bir verilen *lOsError* değeri. Hata kodu bilinmiyor sonra işlevi olarak kodlanmış bir özel durum oluşturduğunda `CFileException::generic`.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
Bir işletim sistemine özgü hata kodu.

*lpszFileName*<br/>
Dosya adını içeren dize işaretçisi varsa özel durum neden.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
