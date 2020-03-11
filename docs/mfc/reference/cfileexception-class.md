---
title: CFileException Sınıfı
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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855383"
---
# <a name="cfileexception-class"></a>CFileException Sınıfı

Dosya ile ilgili özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CFileException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFileException:: CFileException](#cfileexception)|`CFileException` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileException:: Errnotoözel durumu](#errnotoexception)|Çalışma zamanı hata numarasına karşılık gelen nedeni kodu döndürür.|
|[CFileException:: GetErrorMessage](#geterrormessage)|Özel durumu açıklayan iletiyi alır.|
|[CFileException:: OsErrorToException](#oserrortoexception)|Bir işletim sistemi hata koduna karşılık gelen bir neden kodu döndürür.|
|[CFileException:: ThrowErrno](#throwerrno)|Çalışma zamanı hata numarasına göre bir dosya özel durumu oluşturur.|
|[CFileException:: ThrowOsError](#throwoserror)|Bir işletim sistemi hata numarasına göre bir dosya özel durumu oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFileException:: m_cause](#m_cause)|Özel durum nedenine karşılık gelen taşınabilir kodu içerir.|
|[CFileException:: m_lOsError](#m_loserror)|İlgili işletim sistemi hata numarasını içerir.|
|[CFileException:: m_strFileName](#m_strfilename)|Bu özel durum için dosyanın adını içerir.|

## <a name="remarks"></a>Açıklamalar

`CFileException` sınıfı, taşınabilir neden kodunu ve işletim sistemine özgü hata numarasını tutan ortak veri üyelerini içerir. Sınıfı ayrıca, dosya özel durumları oluşturmak için statik üye işlevleri ve hem işletim sistemi hataları hem de C çalışma zamanı hataları için neden kodları döndürüyor.

`CFileException` nesneler `CFile` üye işlevlerinde ve türetilen sınıfların üye işlevlerinde oluşturulur ve oluşturulur. Bu nesnelere bir **catch** ifadesinin kapsamı içinde erişebilirsiniz. Taşınabilirlik için, bir özel durumun nedenini almak üzere yalnızca neden kodunu kullanın. Özel durumlar hakkında daha fazla bilgi için bkz. [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="cfileexception"></a>CFileException:: CFileException

Nesnenin neden kodunu ve işletim sistemi kodunu depolayan bir `CFileException` nesnesi oluşturur.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*sağlamak*<br/>
Özel durumun nedenini gösteren numaralandırılmış tür değişkeni. Olası değerlerin listesi için bkz. [CFileException:: m_cause](#m_cause) .

*lOsError*<br/>
Özel durum varsa, işletim sistemine özgü bir neden. *LOsError* parametresi, *neden olmasına* göre daha fazla bilgi sağlar.

*lpszArchiveName*<br/>
Özel duruma neden olan `CFile` nesnesinin adını içeren bir dizeye işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, ancak [AfxThrowFileException](exception-processing.md#afxthrowfileexception)genel işlevini çağırın.

> [!NOTE]
>  *LOsError* değişkeni yalnızca `CFile` ve `CStdioFile` nesneleri için geçerlidir. `CMemFile` sınıfı bu hata kodunu işlemez.

##  <a name="errnotoexception"></a>CFileException:: Errnotoözel durumu

Verilen bir çalışma zamanı kitaplığı hata değerini `CFileException` numaralandırılmış hata değerine dönüştürür.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
Çalışma zamanı içerme dosyası ERRNO 'da tanımlanan bir tamsayı hata kodu. Olsun.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir çalışma zamanı kitaplığı hata değerine karşılık gelen Enum değeri.

### <a name="remarks"></a>Açıklamalar

Olası numaralandırılmış değerlerin listesi için bkz. [CFileException:: m_cause](#m_cause) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>CFileException:: GetErrorMessage

Özel durumu açıklayan metni alır.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszError*<br/>
[in, out] Bir hata iletisi alan arabelleğin işaretçisi.

*nMaxError*<br/>
'ndaki Belirtilen arabelleğin tutabilecek en fazla karakter sayısı. Bu, Sonlandırıcı null karakterini içerir.

*pnHelpContext*<br/>
[in, out] Yardım bağlamı KIMLIĞINI alan işaretsiz tamsayıya yönelik işaretçi. `NULL`, KIMLIK döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabellek çok küçükse hata iletisi kesilir.

### <a name="example"></a>Örnek

Aşağıdaki örnek `CFileException::GetErrorMessage`kullanır.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>CFileException:: m_cause

`CFileException` numaralandırılmış bir tür tarafından tanımlanan değerleri içerir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi **int**türünde ortak bir değişkendir. Numaralandırıcılar ve anlamları aşağıdaki gibidir:

- `CFileException::none` 0: hata oluşmadı.

- `CFileException::genericException` 1: belirtilmeyen bir hata oluştu.

- `CFileException::fileNotFound` 2: dosya bulunamadı.

- `CFileException::badPath` 3: yolun tamamı veya bir kısmı geçersiz.

- `CFileException::tooManyOpenFiles` 4: izin verilen açık dosya sayısı aşıldı.

- `CFileException::accessDenied` 5: dosyaya erişilemedi.

- `CFileException::invalidFile` 6: geçersiz bir dosya tanıtıcısı kullanma girişimi vardı.

- `CFileException::removeCurrentDir` 7: geçerli çalışma dizini kaldırılamıyor.

- `CFileException::directoryFull` 8: başka dizin girişi yok.

- `CFileException::badSeek` 9: dosya işaretçisi ayarlanmaya çalışılırken bir hata oluştu.

- 10 `CFileException::hardIO`: bir donanım hatası vardı.

- 11. `CFileException::sharingViolation`: paylaşma. EXE yüklenmedi veya paylaşılan bir bölge kilitli.

- `CFileException::lockViolation` 12: zaten kilitli olan bir bölgeyi kilitleme girişimi vardı.

- `CFileException::diskFull` 14: disk dolu.

- `CFileException::endOfFile` 15: dosya sonuna ulaşıldı.

    > [!NOTE]
    >  Bu `CFileException` numaralandırıcıların nedeni, `CArchiveException` neden numaralandırıcılarından farklıdır.

    > [!NOTE]
    > `CArchiveException::generic` kullanım dışıdır. Bunun yerine `genericException` kullanın. **Genel** bir uygulamada kullanılırsa ve/clr ile derlense, sonuçta elde edilen söz dizimi hatalarının şifre kolayca engellenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>CFileException:: m_lOsError

Bu özel durum için işletim sistemi hata kodunu içerir.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Açıklamalar

Hata kodlarının listelenmesi için işletim sistemi teknik kılavuzuna bakın. Bu veri üyesi LONG türünde ortak bir değişkendir.

##  <a name="m_strfilename"></a>CFileException:: m_strFileName

Bu özel durum koşulunun dosya adını içerir.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>CFileException:: OsErrorToException

Verilen *lOsError* değerine karşılık gelen bir Numaralandırıcı döndürür. Hata kodu bilinmiyorsa, işlev `CFileException::generic`döndürür.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
İşletim sistemine özgü bir hata kodu.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir işletim sistemi hata değerine karşılık gelen Enum değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>CFileException:: ThrowErrno

Belirli bir *nErrno* değerine karşılık gelen bir `CFileException` nesnesi oluşturur, sonra özel durumu oluşturur.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
Çalışma zamanı içerme dosyası ERRNO 'da tanımlanan bir tamsayı hata kodu. Olsun.

*lpszFileName*<br/>
Varsa, özel duruma neden olan dosyanın adını içeren dizeye yönelik bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>CFileException:: ThrowOsError

Verilen *lOsError* değerine karşılık gelen bir `CFileException` oluşturur. Hata kodu bilinmiyorsa, işlev `CFileException::generic`olarak kodlanmış bir özel durum oluşturur.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
İşletim sistemine özgü bir hata kodu.

*lpszFileName*<br/>
Varsa, özel duruma neden olan dosyanın adını içeren dizeye yönelik bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
