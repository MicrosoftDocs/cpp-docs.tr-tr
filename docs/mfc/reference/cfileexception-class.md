---
title: CFileException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f94d6fc19879da1dd1dcaa94ab7a177fb86d5186
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cfileexception-class"></a>CFileException sınıfı
Bir dosya ile ilgili özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|Oluşturan bir `CFileException` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|Bir çalışma zamanı hata numarasına karşılık gelen kod döndürür neden.|  
|[CFileException::GetErrorMessage](#geterrormessage)|Bir özel durumu açıklayan ileti alır.|  
|[CFileException::OsErrorToException](#oserrortoexception)|Bir işletim sistemi hata koduna karşılık gelen bir neden kodu döndürür.|  
|[CFileException::ThrowErrno](#throwerrno)|Bir çalışma zamanı hata numarasına göre bir dosya özel durum oluşturur.|  
|[CFileException::ThrowOsError](#throwoserror)|Bir işletim sistemi hata numarasına dayanan bir dosya özel durum oluşturur.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileException::m_cause](#m_cause)|Özel durum neden karşılık gelen taşınabilir kodunu içerir.|  
|[CFileException::m_lOsError](#m_loserror)|İlgili işletim sistemi hata numarasını içermektedir.|  
|[CFileException::m_strFileName](#m_strfilename)|Bu özel durumun dosya adını içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFileException` Sınıfı, taşınabilir neden kodu ve işletim sistemine özgü hata numarası tutun genel veri üyelerini içerir. Sınıfı, ayrıca dosya özel durumları atma ve işletim sistemi hataları ve C çalışma zamanı hataları için neden kodları döndürme için statik üye işlevleri sağlar.  
  
 `CFileException` nesneleri oluşturulan ve durum `CFile` üye işlevleri ve türetilmiş sınıflarının üye işlevleri. Bu nesneler kapsamında erişim bir **CATCH** ifade. Taşınabilirlik için yalnızca neden kodu bir özel durum nedeni almak için kullanın. Özel durumlar hakkında daha fazla bilgi için bkz: [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cfileexception"></a>  CFileException::CFileException  
 Oluşturan bir `CFileException` neden kodu ve işletim sistemi kodu depolar nesnesi.  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cause`  
 Özel durumun nedeni gösteren bir Enum Türü değişkeni. Bkz: [CFileException::m_cause](#m_cause) olası değerler listesi.  
  
 `lOsError`  
 Bir işletim sistemine özgü nedenden dolayı varsa özel durum. `lOsError` Parametresini daha fazla bilgi sağlar `cause` yapar.  
  
 `lpszArchiveName`  
 İşaret adını içeren bir dize `CFile` özel duruma neden nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın, ancak bunun yerine genel bir işlevi çağırmak [AfxThrowFileException](exception-processing.md#afxthrowfileexception).  
  
> [!NOTE]
>  Değişkeni `lOsError` yalnızca geçerli `CFile` ve `CStdioFile` nesneleri. `CMemFile` Sınıfı, bu hata kodu işlemez.  
  
##  <a name="errnotoexception"></a>  CFileException::ErrnoToException  
 Belirtilen çalışma zamanı kitaplığı hata değerine dönüştürür bir `CFileException` hata değerini numaralandırılır.  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrno`  
 Çalışma zamanı içerme dosyası ERRNO tanımlandığı şekilde bir tamsayı hata kodu. H.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen çalışma zamanı kitaplığı hata değerine karşılık gelir Enum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CFileException::m_cause](#m_cause) olası bir listesi için numaralandırılmış değerler.  
  
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
 [içinde out] `lpszError`  
 Bir hata iletisi alır bir arabellek işaretçi.  
  
 [in] `nMaxError`  
 Belirtilen arabellek tutabilir karakter sayısı. Sondaki boş karakter içerir.  
  
 [içinde out] `pnHelpContext`  
 İşaretçi işaretsiz tamsayıya Yardım içerik kimliği alır. Varsa `NULL`, kimliği yok döndürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen arabellek çok küçük ise, hata iletisi kesilir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `CFileException::GetErrorMessage`.  
  
 [!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>  CFileException::m_cause  
 Tarafından tanımlanan değerleri içeren bir `CFileException` numaralandırılmış türü.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veri üyesi tür genel bir değişkendir `int`. Numaralandırmalar ve anlamları şu şekildedir:  
  
- `CFileException::none` 0: herhangi bir hata oluştu.  
  
- `CFileException::genericException` 1: belirlenemeyen bir hata oluştu.  
  
- `CFileException::fileNotFound` 2: dosya bulunamadı.  
  
- `CFileException::badPath` 3: tüm veya yolun bir kısmı geçersiz.  
  
- `CFileException::tooManyOpenFiles` 4: izin verilen açık dosya sayısı aşıldı.  
  
- `CFileException::accessDenied` 5: dosyaya erişilemiyor.  
  
- `CFileException::invalidFile` 6: geçersiz bir dosya tanıtıcısı kullanma girişimi vardı.  
  
- `CFileException::removeCurrentDir` 7: geçerli çalışma dizini kaldırılamıyor.  
  
- `CFileException::directoryFull` 8: dizin girdisi yok vardır.  
  
- `CFileException::badSeek` 9: dosya işaretçisini ayarlamaya çalışırken bir hata oluştu.  
  
- `CFileException::hardIO` 10: bir donanım hatası vardı.  
  
- `CFileException::sharingViolation` 11: PAYLAŞIMI. EXE yüklü değildi veya paylaşılan bölge kilitliydi.  
  
- `CFileException::lockViolation` 12: zaten kilitli olan bölge kilitlenmeye girişimi vardı.  
  
- `CFileException::diskFull` 14: disk dolu.  
  
- `CFileException::endOfFile` 15: dosya sonuna ulaşıldı.  
  
    > [!NOTE]
    >  Bunlar `CFileException` neden numaralandırıcılar ayrı `CArchiveException` numaralandırıcılar neden.  
  
    > [!NOTE]
    > `CArchiveException::generic` kullanım dışı bırakılmıştır. Bunun yerine `genericException` kullanın. Varsa `generic` bir uygulamada kullanılan ve/CLR ile hataları geçirilirse kolay olmayan elde edilen sözdizimini üretilmiştir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>  CFileException::m_lOsError  
 Bu durum işletim sistemi hata kodunu içerir.  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşletim sistemi teknik kılavuzunuza hata kodları listesi için bkz. Bu veri üyesi tür genel bir değişkendir **uzun**.  
  
##  <a name="m_strfilename"></a>  CFileException::m_strFileName  
 Bu özel durum için dosya adını içerir.  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException  
 Karşılık gelen bir numaralandırıcı döndürür bir verilen `lOsError` değer. Hata kodu bilinmiyor sonra işlevi döndürür **CFileException::generic**.  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>Parametreler  
 `lOsError`  
 Bir işletim sistemine özgü hata kodu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen işletim sistemi hata değerine karşılık gelir Enum değeri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>  CFileException::ThrowErrno  
 Oluşturan bir `CFileException` nesne karşılık gelen bir verilen `nErrno` değer sonra özel durum oluşturur.  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nErrno`  
 Çalışma zamanı içerme dosyası ERRNO tanımlandığı şekilde bir tamsayı hata kodu. H.  
  
 `lpszFileName`  
 Dosyanın adını içeren dize için bir işaretçi varsa özel durum neden.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>  CFileException::ThrowOsError  
 Atan bir `CFileException` karşılık gelen bir verilen `lOsError` değer. Hata kodu bilinmiyor sonra işlevi olarak kodlanmış bir özel durum oluşturur **CFileException::generic**.  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lOsError`  
 Bir işletim sistemine özgü hata kodu.  
  
 `lpszFileName`  
 Dosyanın adını içeren dize için bir işaretçi varsa özel durum neden.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Özel Durum İşleme](../../mfc/reference/exception-processing.md)



