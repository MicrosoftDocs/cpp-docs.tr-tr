---
title: Özel Durum İşleme
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.exceptions
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
ms.openlocfilehash: 8b40afbfcc453a4908b434dc53b7b86959673453
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851688"
---
# <a name="exception-processing"></a>Özel Durum İşleme

Bir programı yürütüldüğünde, bir dizi anormal koşullar ve "özel durumlar" adlı hataları oluşabilir. Bu işlem, bellek, kaynak ayırma hatalarını ve dosyaları bulmak için hata bitmesi içerebilir.

Microsoft Foundation Class Kitaplığı, C++ için ANSI standartları komitesi tarafından önerilen sonra yakından modellenmiş bir özel durum işleme düzeni kullanır. Bir işlevi çağırmak, olağan dışı bir durum karşılaşabilirsiniz önce bir özel durum işleyicisi ayarlanması gerekir. İşlev olağan dışı bir koşul karşılaşırsa, bir özel durum oluşturur ve denetimi özel durum işleyicisine geçirilir.

Microsoft Foundation Class Kitaplığı ile dahil çeşitli makrolar, özel durum işleyicileri ' ayarlanır. Gerekirse, özelleştirilmiş özel durumlar oluşturma ve programları, sonlandırma için çok sayıda diğer genel işlev yardımcı olur. Bu makrolar ve genel işlevler aşağıdaki kategorilere ayrılır:

- Yapısı, özel durum işleyicisi özel durum makroları.

- İşlevleri Exception-throwing), belirli bir tür özel durumlar oluşturun.

- Program sonlandırma neden sonlandırma işlevleri.

Örnekler ve daha fazla ayrıntı için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="exception-macros"></a>Özel durum makroları

|||
|-|-|
|[DENEYİN](#try)|Özel durum işleme için bir kod bloğunu belirler.|
|[YAKALAMA](#catch)|Önceki bir özel durum yakalamak için bir kod bloğunu atayan **deneyin** blok.|
|[CATCH_ALL](#catch_all)|Önceki tüm özel durumları yakalama için bir kod bloğunu atayan **deneyin** blok.|
|[AND_CATCH](#and_catch)|Önceki ek özel durum türlerini yakalamak için bir kod bloğunu atayan **deneyin** blok.|
|[AND_CATCH_ALL](#and_catch_all)|Bir önceki durum diğer tüm ek özel durum türlerini yakalamak için bir kod bloğunu atayan **deneyin** blok.|
|[END_CATCH](#end_catch)|Son sona erer **CATCH** veya **AND_CATCH** kod bloğu.|
|[END_CATCH_ALL](#end_catch_all)|Son sona erer **CATCH_ALL** kod bloğu.|
|[THROW](#throw)|Belirtilen bir özel durum oluşturur.|
|[THROW_LAST](#throw_last)|Dış bir sonraki işleyici için şu anda işlenen özel durum oluşturur.|

### <a name="exception-throwing-functions"></a>Özel durum atma işlevleri

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Bir arşiv özel durum oluşturur.|
|[AfxThrowFileException](#afxthrowfileexception)|Dosya özel durum oluşturur.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Geçersiz bağımsız değişken özel durum oluşturur.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Bir bellek özel durumu oluşturur.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Desteklenmeyen bir özel durum oluşturur.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Bir Windows kaynak bulunamadı özel durum oluşturur.|
|[AfxThrowUserException](#afxthrowuserexception)|Program kullanıcı tarafından başlatılan bir eylemde bir özel durum oluşturur.|

MFC özel OLE özel durumları için iki özel durum atma işlevleri sağlar:

### <a name="ole-exception-functions"></a>OLE özel işlevler

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Bir OLE Otomasyon işlevi içinde özel durum oluşturur.|
|[AfxThrowOleException](#afxthrowoleexception)|Bir OLE özel durum oluşturur.|

Veritabanı özel durumları desteklemek için iki özel durum sınıfları, veritabanı sınıfları sağlar `CDBException` ve `CDaoException`ve özel durum türlerini desteklemek için genel işlevler:

### <a name="dao-exception-functions"></a>DAO özel işlevler

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|Oluşturur bir [CDaoException](../../mfc/reference/cdaoexception-class.md) kendi kod.|
|[AfxThrowDBException](#afxthrowdbexception)|Oluşturur bir [CDBException](../../mfc/reference/cdbexception-class.md) kendi kod.|

MFC aşağıdaki sonlandırma işlevi sağlar:

### <a name="termination-functions"></a>Sonlandırma işlevleri

|||
|-|-|
|[AfxAbort](#afxabort)|Önemli bir hata oluştuğunda bir uygulamayı sonlandırmak için çağırılır gerçekleşir.|

##  <a name="try"></a>  DENEYİN

Ayarlayan bir **deneyin** blok.

```
TRY
```

### <a name="remarks"></a>Açıklamalar

A **deneyin** bloğu özel durumları fırlatabilir bir kod bloğunu tanımlar. Bu özel durumların aşağıdaki işlenme **CATCH** ve **AND_CATCH** engeller. Özyineleme izin verilir: özel durumlar geçirilecek bir dış **deneyin** blok, bunları yoksayılıyor veya THROW_LAST makrosu kullanarak. Son **deneyin** bloğu ile bir END_CATCH veya END_CATCH_ALL makrosu.

Daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

Örneğin bakın [CATCH](#catch).

### <a name="requirements"></a>Gereksinimler

Üstbilgi: afx.h

##  <a name="catch"></a>  YAKALAMA

Önceki durum ilk özel durum türü yakalayan bir kod bloğunu tanımlar **deneyin** blok.

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test etmek için özel durum türünü belirtir. Standart özel durum sınıfları listesi için bkz. [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad belirtir. Bir işaretçi adı içinde özel durum nesnesine erişmek için kullanabileceğiniz **CATCH** blok. Bu değişken, size bildirilir.

### <a name="remarks"></a>Açıklamalar

Özel durum işleme kodu özel durum nesnesi uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi almak sorgulayın. Sonraki çerçeveyi dıştaki özel durum işleme kaydırılacak THROW_LAST makrosu çağırın. Son **deneyin** END_CATCH makrosu blok.

Varsa *exception_class* sınıf `CException`, sonra tüm özel durum türleri yakalandı. Kullanabileceğiniz [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) hangi belirli özel durum oluştu belirlemek için üye işlevi. Sıralı kullanmak için çeşitli türlerde özel durumları yakalamak için daha iyi bir yolu olan **AND_CATCH** deyimleri, her biri farklı bir özel durum türü.

Özel durum nesnesi işaretçisini makro tarafından oluşturulur. Kendiniz bildirmek gerekmez.

> [!NOTE]
>  **CATCH** blok ayraçları makaleyle C++ kapsam olarak tanımlanır. Bu kapsam içinde değişkenlere bildirirseniz, sadece ilgili kapsam içinde erişilebilir. Bu durum için de geçerlidir *exception_object_pointer_name*.

Özel durumlar ve CATCH makrosu hakkında daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

##  <a name="catch_all"></a>  CATCH_ALL

Önceki durum tüm özel durum türleri yakalayan bir kod bloğunu tanımlar **deneyin** blok.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad belirtir. Bir işaretçi adı içinde özel durum nesnesine erişmek için kullanabileceğiniz `CATCH_ALL` blok. Bu değişken, size bildirilir.

### <a name="remarks"></a>Açıklamalar

Özel durum işleme kodu özel durum nesnesi uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi almak sorgulayın. Çağırma `THROW_LAST` sonraki çerçeveye dıştaki özel durum işleme kaydırılacak makrosu. Kullanırsanız **CATCH_ALL**, son **deneyin** END_CATCH_ALL makrosu blok.

> [!NOTE]
>  **CATCH_ALL** blok ayraçları makaleyle C++ kapsam olarak tanımlanır. Bu kapsam içinde değişkenlere bildirirseniz, sadece ilgili kapsam içinde erişilebilir.

Özel durumları hakkında daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

Örneğin bakın [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="and_catch"></a>  AND_CATCH

Bir önceki durum ek özel durum türlerini yakalamak için bir kod bloğunu tanımlar **deneyin** blok.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test etmek için özel durum türünü belirtir. Standart özel durum sınıfları listesi için bkz. [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad. Bir işaretçi adı içinde özel durum nesnesine erişmek için kullanabileceğiniz **AND_CATCH** blok. Bu değişken, size bildirilir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum türü yakalamak için CATCH makrosu sonra sonraki her tür yakalamak için AND_CATCH makrosu kullanın. Son **deneyin** END_CATCH makrosu blok.

Özel durum işleme kodu özel durum nesnesi uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi almak sorgulayın. THROW_LAST makrosu içinde çağrı **AND_CATCH** sonraki çerçeveye dıştaki özel durum işleme shift engelleyin. **AND_CATCH** önceki sonunu işaretler **CATCH** veya **AND_CATCH** blok.

> [!NOTE]
>  **AND_CATCH** blok (küme ayraçları işaretleriyle) C++ kapsam olarak tanımlanır. Bu kapsam içinde değişkenlere bildirirseniz, sadece ilgili kapsam içinde erişilebilir olduklarını unutmayın. Bu durum için de geçerlidir *exception_object_pointer_name* değişkeni.

### <a name="example"></a>Örnek

Örneğin bakın [CATCH](#catch).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h
##  <a name="and_catch_all"></a>  AND_CATCH_ALL

Bir önceki durum ek özel durum türlerini yakalamak için bir kod bloğunu tanımlar **deneyin** blok.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad. Bir işaretçi adı içinde özel durum nesnesine erişmek için kullanabileceğiniz **AND_CATCH_ALL** blok. Bu değişken, size bildirilir.

### <a name="remarks"></a>Açıklamalar

Kullanım **CATCH** bir özel durum türü yakalamak için makro ve diğer tüm sonraki türleri yakalamak için AND_CATCH_ALL makrosu. AND_CATCH_ALL kullanırsanız, son **deneyin** END_CATCH_ALL makrosu blok.

Özel durum işleme kodu özel durum nesnesi uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi almak sorgulayın. THROW_LAST makrosu içinde çağrı **AND_CATCH_ALL** sonraki çerçeveye dıştaki özel durum işleme shift engelleyin. **AND_CATCH_ALL** önceki sonunu işaretler **CATCH** veya **AND_CATCH_ALL** blok.

> [!NOTE]
>  **AND_CATCH_ALL** blok (ayraçları işaretleriyle) C++ kapsam olarak tanımlanır. Bu kapsam içinde değişkenlere bildirirseniz, sadece ilgili kapsam içinde erişilebilir olduklarını unutmayın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="end_catch"></a>  END_CATCH

Son sonunu işaretleyen **CATCH** veya **AND_CATCH** blok.

```
END_CATCH
```

### <a name="remarks"></a>Açıklamalar

END_CATCH makrosu hakkında daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="end_catch_all"></a>  END_CATCH_ALL

Son sonunu işaretleyen <strong>CATCH_ALL88 veya ** AND_CATCH_ALL</strong> blok.

```
END_CATCH_ALL
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="throw"></a>  THROW (MFC)

Belirtilen özel durum oluşturur.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer*<br/>
Bir özel durum nesnesini noktalarına türetilen `CException`.

### <a name="remarks"></a>Açıklamalar

**THROW** kesme programı ilişkili denetim geçirme yürütme **CATCH** programınızda engelleyin. Sağlanmadığında **CATCH** denetimi, bir hata iletisi ve çıkar Microsoft Foundation Class Kitaplığı modülü geçirilir sonra engelleyin.

Daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="throw_last"></a>  THROW_LAST

Özel durum geri sonraki oluşturur dış **CATCH** blok.

```
THROW_LAST()
```

### <a name="remarks"></a>Açıklamalar

Bu makro, yerel olarak oluşturulan bir özel durum oluşturmasına olanak tanır. Yalnızca yakalanan bir özel durum denerseniz, normalde kapsam dışına gider ve silinecek. İle **THROW_LAST**, özel durum doğru sonraki geçirilen **CATCH** işleyici.

Daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

Örneğin bakın [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException

Bir arşiv özel durum oluşturur.

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Parametreler

*Bunun nedeni*<br/>
Özel durumun nedenini belirten bir tamsayı belirtir. Olası değerler listesi için bkz. [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
İşaret adı içeren bir dizeye `CArchive` (varsa) özel duruma neden olan nesne.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowfileexception"></a>  AfxThrowFileException

Dosya özel durum oluşturur.

```
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*Bunun nedeni*<br/>
Özel durumun nedenini belirten bir tamsayı belirtir. Olası değerler listesi için bkz. [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsError*<br/>
İşletim sistemi hata numarasına (varsa) içeren özel durumun nedenini belirten. Hata kodlarının listesi için işletim sistemi kılavuzuna bakın.

*lpszFileName*<br/>
(Varsa) özel duruma neden dosya adını içeren bir dize işaret eder.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata koduna göre nedenini belirlemek için sorumlu olursunuz.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

## <a name="afxthrowinvalidargexception"></a>  AfxThrowInvalidArgException

Geçersiz bağımsız değişken özel durum oluşturur.

### <a name="syntax"></a>Sözdizimi

```
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Açıklamalar

Geçersiz bağımsız değişkenler kullanıldığında bu işlev çağrılır.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException

Bir bellek özel durumu oluşturur.

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Varsa bu işlevi çağırın. temel alınan sistem bellek ayırıcılar çağrıları (gibi **malloc** ve [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows işlevi) başarısız. Bunun için çağrı gerekmez **yeni** çünkü **yeni** bellek ayırma başarısız olursa bir bellek özel durumu otomatik olarak atar.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException

Desteklenmeyen bir özellik isteğinden kaynaklanan bir özel durum oluşturur.

```
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowresourceexception"></a>  AfxThrowResourceException

Bir kaynak özel durum oluşturur.

```
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, normalde Windows Kaynak yüklendiğinde çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowuserexception"></a>  AfxThrowUserException

Son kullanıcı işlemini durdurmak için bir özel durum oluşturur.

```
void AfxThrowUserException();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev normalde hemen sonra çağrılır `AfxMessageBox` kullanıcıya bir hata bildirdi.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowoledispatchexception"></a>  AfxThrowOleDispatchException

Bir OLE Otomasyon işlevi içinde bir özel durum oluşturmak için bu işlevi kullanın.

```
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,
    LPCSTR lpszDescription,
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,
    UINT nDescriptionID,
    UINT nHelpID = -1);
```

### <a name="parameters"></a>Parametreler

*WCode*<br/>
Uygulamanıza özgü bir hata kodu.

*lpszDescription*<br/>
Sözlü hatanın açıklaması.

*nDescriptionID*<br/>
Sözlü hata açıklamasını kaynak kimliği.

*nHelpID*<br/>
Uygulamanızın Yardım için Yardım içeriğini (. HLP) dosyası.

### <a name="remarks"></a>Açıklamalar

Bu işlev için sağlanan bilgileri sürüş uygulama (Microsoft Visual Basic veya başka bir OLE Otomasyon istemci uygulaması) tarafından görüntülenebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxthrowoleexception"></a>  AfxThrowOleException

Türünde bir nesne oluşturur `COleException` ve bir özel durum oluşturur.

```
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*sc*<br/>
Özel durumun nedenini gösteren bir OLE durum kodu.

*İK*<br/>
Özel durumun nedenini belirten bir sonuç kodu için işleyin.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olarak bir HRESULT alan sürümü, sonuç kodu karşılık gelen SCODE dönüştürür. HRESULT ve SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException

Özel durum türü için bu işlevi çağırın [CDaoException](../../mfc/reference/cdaoexception-class.md) kendi kod.

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Parametreler

*nAfxDaoError*<br/>
Hata kodu genişletilmiş bir DAO temsil eden bir tamsayı değeri olan değerlerden biri altında listelenebilir [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*SCODE*<br/>
DAO, SCODE türünde bir OLE hata kodu. Bilgi için [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Açıklamalar

Framework de çağırır `AfxThrowDaoException`. Çağrınızda, parametrelerden biri veya her ikisini de geçirebilirsiniz. Aşağıdakilerden birini yükseltmek istiyorsanız, örneğin, hataları tanımlanan **CDaoException::nAfxDaoError** ancak verdiğiniz değil *scode* parametresi, geçerli bir kod geçirmek *nAfxDaoError* parametresi için varsayılan değeri kabul *scode*.

MFC DAO sınıflarına ilgili özel durumları hakkında daha fazla bilgi için bkz. `CDaoException` bu kitap ve makale [özel durumlar: Veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdb.h

##  <a name="afxthrowdbexception"></a>  AfxThrowDBException

Özel durum türü için bu işlevi çağırın `CDBException` kendi kod.

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
Özel durum oluşturulmasına neden olan hata türünü tanımlayan RETCODE, türünde bir değer.

*pdb*<br/>
Bir işaretçi `CDatabase` özel durum olduğu ilişkili veri kaynağı bağlantısını temsil eden nesne.

*hstmt*<br/>
Özel durum ilişkilendirildiği deyim tanıtıcı belirtir bir ODBC HSTMT tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Framework çağrıları `AfxThrowDBException` ne zaman bir ODBC RETCODE bir ODBC API işlevine bir çağrı aldığında ve RETCODE expectable hata yerine olağanüstü bir koşul olarak yorumlar. Örneğin, bir veri erişim işlemi, bir disk okuma hatası nedeniyle başarısız olabilir.

ODBC tarafından tanımlanan RETCODE değerler hakkında daha fazla bilgi için "Alma durumu ve hata bilgileri için" Bölüm 8, Windows SDK'yı bakın. MFC uzantıları için bu kodları hakkında daha fazla bilgi için bkz. [CDBException](../../mfc/reference/cdbexception-class.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

##  <a name="afxabort"></a>  AfxAbort

MFC tarafından sağlanan varsayılan sonlandırma işlevi.

```
void  AfxAbort();
```

### <a name="remarks"></a>Açıklamalar

`AfxAbort` işlenemez yakalanmayan bir özel durum gibi önemli bir hata olduğunda, MFC üye işlevleri tarafından dahili olarak çağrılır. Çağırabilirsiniz `AfxAbort` , olamaz kurtarma işlemi yıkıcı hatayla karşılaşırsanız, nadir durumda.

### <a name="example"></a>Örnek

Örneğin bakın [CATCH](#catch).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afx.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[CException Sınıfı](cexception-class.md)<br/>
[CInvalidArgException Sınıfı](cinvalidargexception-class.md)
