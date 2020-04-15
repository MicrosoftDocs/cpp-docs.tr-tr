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
ms.openlocfilehash: 2d1025ca33d5641982ba52f1ac539db85df3bfd5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373889"
---
# <a name="cfileexception-class"></a>CFileException Sınıfı

Dosyayla ilgili özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CFileException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFileException::CFileException](#cfileexception)|Bir `CFileException` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|Çalışma zamanı hata numarasına karşılık gelen neden kodunu döndürür.|
|[CFileException::GetErrorMessage](#geterrormessage)|Özel bir durumu açıklayan iletiyi alır.|
|[CfileException::OsErrortoException](#oserrortoexception)|İşletim sistemi hata koduna karşılık gelen bir neden kodu verir.|
|[CFileException::ThrowErrno](#throwerrno)|Çalışma zamanı hata numarasını temel alan bir dosya özel durum oluşturur.|
|[CFileException::throwoserror](#throwoserror)|İşletim sistemi hata numarasını temel alan bir dosya özel durum oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|Özel durum nedenine karşılık gelen taşınabilir kodu içerir.|
|[CFileException::m_lOsError](#m_loserror)|İlgili işletim sistemi hata numarasını içerir.|
|[CFileException::m_strFileName](#m_strfilename)|Bu özel durum için dosyanın adını içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CFileException` taşınabilir neden kodunu ve işletim sistemine özgü hata numarasını tutan ortak veri üyelerini içerir. Sınıf ayrıca dosya özel durumlarını atmak ve hem işletim sistemi hataları hem de C çalışma zamanı hataları için neden kodlarını döndürmek için statik üye işlevler de sağlar.

`CFileException`nesneler, üye işlevlerde `CFile` ve türemiş sınıfların üye işlevlerinde oluşturulur ve atılır. Catch **ifadesi** kapsamında bu nesnelere erişebilirsiniz. Taşınabilirlik için, bir özel durum nedenini almak için yalnızca neden kodunu kullanın. Özel durumlar hakkında daha fazla bilgi için [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a>CFileException::CFileException

Nesnede `CFileException` neden kodu ve işletim sistemi kodunu depolayan bir nesne oluşturuyor.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*Neden*<br/>
Özel durum nedenini gösteren numaralandırılmış bir tür değişkeni. Bkz. [CFileException::m_cause](#m_cause) olası değerlerin listesi için.

*lOsError*<br/>
Varsa, özel durum için işletim sistemine özgü bir neden. *lOsError* parametresi *nedenden* daha fazla bilgi sağlar.

*lpszArchiveName*<br/>
Özel durum neden `CFile` nesnenin adını içeren bir dize işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, daha çok global işlevi [AfxThrowFileException'ı](exception-processing.md#afxthrowfileexception)arayın.

> [!NOTE]
> Değişken *lOsError* yalnızca ve `CFile` `CStdioFile` nesneler için geçerlidir. Sınıf `CMemFile` bu hata kodunu işlemez.

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>CFileException::ErrnoToException

Belirli bir çalışma zamanı kitaplığı hata `CFileException` değerini numaralandırılmış bir hata değerine dönüştürür.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
Çalışma süresinde tanımlandığı gibi bir bir hata kodu dosya ERRNO içerir. H.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir çalışma zamanı kitaplığı hata değerine karşılık gelen numaralandırılmış değer.

### <a name="remarks"></a>Açıklamalar

[Bkz. CFileException::m_cause](#m_cause) olası numaralandırılmış değerlerin listesi için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>CFileException::GetErrorMessage

Özel durumu açıklayan metni alır.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpszHata*<br/>
[içinde, dışarı] Hata iletisi alan bir arabellek için işaretçi.

*nMaxHatası*<br/>
[içinde] Belirtilen arabellek tutabilir karakter maksimum sayısı. Bu sonlandırıcı null karakteri içerir.

*pnHelpContext*<br/>
[içinde, dışarı] Yardım bağlamı kimliğini alan imzasız bir alıcıyı işaretçi. `NULL`, kimlik döndürülmezse.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabellek çok küçükse, hata iletisi kesilir.

### <a name="example"></a>Örnek

Aşağıdaki örnekkullanır. `CFileException::GetErrorMessage`

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a>CFileException::m_cause

Numaralandırılmış bir `CFileException` tür tarafından tanımlanan değerleri içerir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi, **int**türünden genel bir değişkendir. Sayısallaştırıcılar ve anlamları aşağıdaki gibidir:

- `CFileException::none`0: Hata oluşmadı.

- `CFileException::genericException`1: Belirtilmeyen bir hata oluştu.

- `CFileException::fileNotFound`2: Dosya bulunamadı.

- `CFileException::badPath`3: Yolun tamamı veya bir kısmı geçersizdir.

- `CFileException::tooManyOpenFiles`4: İzin verilen açık dosya sayısı aşıldı.

- `CFileException::accessDenied`5: Dosyaya erişilenemedi.

- `CFileException::invalidFile`6: Geçersiz bir dosya tanıtıcısı kullanma girişimi oldu.

- `CFileException::removeCurrentDir`7: Geçerli çalışma dizini kaldırılamaz.

- `CFileException::directoryFull`8: Artık dizin girişi yok.

- `CFileException::badSeek`9: Dosya işaretçisini ayarlamaya çalışan bir hata oluştu.

- `CFileException::hardIO`10: Bir donanım hatası oluştu.

- `CFileException::sharingViolation`11: PAYLAŞ. EXE yüklü değildi veya paylaşılan bir bölge kilitlendi.

- `CFileException::lockViolation`12: Zaten kilitli olan bir bölgeyi kilitleme girişimi yapıldı.

- `CFileException::diskFull`14: Disk dolu.

- `CFileException::endOfFile`15: Dosyanın sonuna ulaşıldı.

    > [!NOTE]
    >  Bu `CFileException` neden sayısallaştırıcılar `CArchiveException` neden sayısalatörler farklıdır.

    > [!NOTE]
    > `CArchiveException::generic`amortismana lı. Bunun yerine `genericException` kullanın. **Genel bir** uygulamada kullanılır ve /clr ile oluşturulmuşsa, ortaya çıkan sözdizimi hatalarını çözmek kolay değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a>CFileException::m_lOsError

Bu özel durum için işletim sistemi hata kodunu içerir.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Açıklamalar

Hata kodlarının listesi için işletim sistemi teknik kılavuzuna bakın. Bu veri üyesi, UZUN türünde ortak bir değişkendir.

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a>CFileException::m_strFileName

Bu özel durum koşulu için dosyanın adını içerir.

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>CfileException::OsErrortoException

Belirli bir *lOsError* değerine karşılık gelen bir sayısallaştırıcı döndürür. Hata kodu bilinmiyorsa, işlev `CFileException::generic`döndürür.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
İşletim sistemine özgü bir hata kodu.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir işletim sistemi hata değerine karşılık gelen numaralandırılmış değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a>CFileException::ThrowErrno

Belirli bir `CFileException` *nErrno* değerine karşılık gelen bir nesne oluşturur, sonra özel durum atar.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*nErrno*<br/>
Çalışma süresinde tanımlandığı gibi bir bir hata kodu dosya ERRNO içerir. H.

*lpszFileName*<br/>
Varsa, özel durum neden dosyanın adını içeren dize için bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a>CFileException::throwoserror

Belirli bir `CFileException` *lOsError* değerine karşılık gelen atar. Hata kodu bilinmiyorsa, işlev ' in '' `CFileException::generic`olarak kodlanmış bir özel durum atışı

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lOsError*<br/>
İşletim sistemine özgü bir hata kodu.

*lpszFileName*<br/>
Varsa, özel durum neden dosyanın adını içeren dize için bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
