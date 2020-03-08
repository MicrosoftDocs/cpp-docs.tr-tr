---
title: Özel Durum İşleme
ms.date: 11/04/2016
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
ms.openlocfilehash: d33da7a9bc81f9733df840a87fbbbeca1e02cc04
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855372"
---
# <a name="exception-processing"></a>Özel Durum İşleme

Bir program yürütüldüğünde, "özel durumlar" adlı bir dizi olağan dışı koşul ve hata oluşabilir. Bunlar bellek yetersiz, kaynak ayırma hataları ve dosya bulma hatası içerebilir.

Microsoft Foundation Class Kitaplığı, için C++ANSI standartları komite tarafından önerilmiş bir şekilde modellenen bir özel durum işleme düzeni kullanır. Olağan dışı bir durumla karşılaşabilecekleri bir işlev çağrılmadan önce bir özel durum işleyicisi ayarlanmalıdır. İşlev olağan dışı bir koşulla karşılaşırsa, bir özel durum oluşturur ve denetim özel durum işleyicisine geçirilir.

Microsoft Foundation Class Kitaplığı eklenen birkaç makro özel durum işleyicilerini ayarlar. Gerekirse, özel özel durumlar oluşturma ve programları sonlandırma konusunda çok sayıda genel işlev vardır. Bu makrolar ve genel işlevler aşağıdaki kategorilere ayrılır:

- Özel durum işleyicinizi oluşturan özel durum makroları.

- Belirli türlerin özel durumlarını oluşturan özel durum oluşturma işlevleri.

- Sonlandırma işlevleri, program sonlandırmasına neden olur.

Örnekler ve daha fazla ayrıntı için bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="exception-macros"></a>Özel durum makroları

|||
|-|-|
|[ALMAYA](#try)|Özel durum işleme için bir kod bloğu belirler.|
|[YAKALAYA](#catch)|Önceki **TRY** bloğundan özel durum yakalamak için bir kod bloğu belirler.|
|[CATCH_ALL](#catch_all)|Önceki **TRY** bloğundan tüm özel durumları yakalamak için bir kod bloğu belirler.|
|[AND_CATCH](#and_catch)|Önceki **TRY** bloğundan ek özel durum türlerini yakalamak için bir kod bloğu belirler.|
|[AND_CATCH_ALL](#and_catch_all)|Önceki **TRY** bloğunda oluşturulan diğer tüm ek özel durum türlerini yakalamak için bir kod bloğu belirler.|
|[END_CATCH](#end_catch)|Son **catch** veya **AND_CATCH** kod bloğunu sonlandırır.|
|[END_CATCH_ALL](#end_catch_all)|Son **CATCH_ALL** kod bloğunu sonlandırır.|
|[YARATıR](#throw)|Belirtilen özel durumu oluşturur.|
|[THROW_LAST](#throw_last)|Şu anda işlenmiş özel durumu sonraki dış işleyiciye atar.|

### <a name="exception-throwing-functions"></a>Özel durum atma Işlevleri

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Bir arşiv özel durumu oluşturur.|
|[AfxThrowFileException](#afxthrowfileexception)|Bir dosya özel durumu oluşturur.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Geçersiz bir bağımsız değişken özel durumu oluşturur.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Bir bellek özel durumu oluşturur.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Desteklenmeyen bir özel durum oluşturur.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows kaynak bulunamadı özel durumu oluşturur.|
|[AfxThrowUserException](#afxthrowuserexception)|Kullanıcı tarafından başlatılan bir program eyleminde özel durum oluşturur.|

MFC özellikle OLE özel durumları için iki özel durum atma işlevi sağlar:

### <a name="ole-exception-functions"></a>OLE özel durum Işlevleri

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE Otomasyonu işlevi içinde bir özel durum oluşturur.|
|[AfxThrowOleException](#afxthrowoleexception)|OLE özel durumu oluşturur.|

Veritabanı sınıfları, veritabanı özel durumlarını desteklemek için, özel durum türlerini desteklemek üzere iki özel durum sınıfı, `CDBException` ve `CDaoException`ve genel işlevler sağlar:

### <a name="dao-exception-functions"></a>DAO özel durum Işlevleri

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|Kendi kodunuzda bir [Cdaoözel durumu](../../mfc/reference/cdaoexception-class.md) oluşturur.|
|[AfxThrowDBException](#afxthrowdbexception)|Kendi kodınızdan bir [CDBException](../../mfc/reference/cdbexception-class.md) oluşturur.|

MFC aşağıdaki sonlandırma işlevini sağlar:

### <a name="termination-functions"></a>Sonlandırma Işlevleri

|||
|-|-|
|[AfxAbort](#afxabort)|Önemli bir hata oluştuğunda bir uygulamayı sonlandırmak için çağırılır.|

##  <a name="try"></a>ALMAYA

Bir **TRY** bloğu ayarlar.

```
TRY
```

### <a name="remarks"></a>Açıklamalar

**TRY** bloğu özel durum oluşturabilecek bir kod bloğunu tanımlar. Bu özel durumlar aşağıdaki **catch** ve **AND_CATCH** bloklarıyla işlenir. Özyineleme için izin verildi: özel durumlar, bir dış **TRY** bloğuna, onları yoksayarak veya THROW_LAST makrosu kullanılarak geçirilebilir. **TRY** bloğunu bir END_CATCH veya END_CATCH_ALL makrosu ile sonlandırın.

Daha fazla bilgi için bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

[Catch](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

Üstbilgi: AFX. h

##  <a name="catch"></a>YAKALAYA

Önceki **TRY** bloğunda oluşturulan ilk özel durum türünü yakalayan bir kod bloğunu tanımlar.

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test edilecek özel durum türünü belirtir. Standart özel durum sınıflarının listesi için bkz. Class [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak özel durum nesnesi işaretçisi için bir ad belirtir. **Catch** bloğu içindeki özel durum nesnesine erişmek için işaretçi adını kullanabilirsiniz. Bu değişken sizin için bildirilmiştir.

### <a name="remarks"></a>Açıklamalar

Özel durumun özel nedeni hakkında daha fazla bilgi almak için özel durum işleme kodu uygunsa özel durum nesnesini sorgulanamıyor olabilir. İşlemeyi bir sonraki dış özel durum çerçevesine kaydırmak için THROW_LAST makrosunu çağırın. **TRY** bloğunu bir END_CATCH makrosu ile sonlandırın.

Sınıf `CException`*Exception_class* , tüm özel durum türleri yakalanacaktır. Hangi özel durumun oluşturulduğunu öğrenmek için [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) üye işlevini kullanabilirsiniz. Çeşitli özel durumları yakalamak için daha iyi bir yol, her biri farklı bir özel durum türüne sahip sıralı **AND_CATCH** deyimlerini kullanmaktır.

Özel durum nesnesi işaretçisi makro tarafından oluşturulur. Kendiniz bildirmeniz gerekmez.

> [!NOTE]
>  **Catch** bloğu, küme ayraçları tarafından belirlenen C++ bir kapsam olarak tanımlanır. Bu kapsamda değişkenler bildirirseniz, bunlar yalnızca o kapsam içinde erişilebilir. Bu, *exception_object_pointer_name*için de geçerlidir.

Özel durumlar ve CATCH makrosu hakkında daha fazla bilgi için, bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

##  <a name="catch_all"></a>CATCH_ALL

Önceki **TRY** bloğunda oluşan tüm özel durum türlerini yakalayan bir kod bloğunu tanımlar.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak özel durum nesnesi işaretçisi için bir ad belirtir. İşaretçi adını `CATCH_ALL` bloğundaki özel durum nesnesine erişmek için kullanabilirsiniz. Bu değişken sizin için bildirilmiştir.

### <a name="remarks"></a>Açıklamalar

Özel durumun özel nedeni hakkında daha fazla bilgi almak için özel durum işleme kodu uygunsa özel durum nesnesini sorgulanamıyor olabilir. İşlemeyi bir sonraki dış özel durum çerçevesine kaydırmak için `THROW_LAST` makrosunu çağırın. **CATCH_ALL**kullanıyorsanız, **TRY** bloğunu bir END_CATCH_ALL makrosu ile sonlandırın.

> [!NOTE]
>  **CATCH_ALL** bloğu, küme ayraçları tarafından belirlenen C++ bir kapsam olarak tanımlanır. Bu kapsamda değişkenler bildirirseniz, bunlar yalnızca o kapsam içinde erişilebilir.

Özel durumlar hakkında daha fazla bilgi için, bkz. [özel durumlar](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

[CFile:: Abort](../../mfc/reference/cfile-class.md#abort)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="and_catch"></a>AND_CATCH

Önceki **TRY** bloğunda oluşturulan ek özel durum türlerini yakalamak için bir kod bloğu tanımlar.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test edilecek özel durum türünü belirtir. Standart özel durum sınıflarının listesi için bkz. Class [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak özel durum nesnesi işaretçisi için bir ad. İşaretçi adını **AND_CATCH** bloğundaki özel durum nesnesine erişmek için kullanabilirsiniz. Bu değişken sizin için bildirilmiştir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum türünü yakalamak için CATCH makrosunu, sonra da her bir sonraki türü yakalamak için AND_CATCH makrosunu kullanın. **TRY** bloğunu bir END_CATCH makrosu ile sonlandırın.

Özel durumun özel nedeni hakkında daha fazla bilgi almak için özel durum işleme kodu uygunsa özel durum nesnesini sorgulanamıyor olabilir. Bir sonraki dış özel durum çerçevesine kaydırmak için **AND_CATCH** bloğunda THROW_LAST makrosunu çağırın. **AND_CATCH** önceki **catch** veya **AND_CATCH** bloğunun sonunu işaretler.

> [!NOTE]
>  **AND_CATCH** bloğu bir C++ kapsam olarak tanımlanır (küme ayraçları tarafından ayırıcı). Bu kapsamda değişkenler bildirirseniz, bunların yalnızca o kapsam içinde erişilebilir olduğunu unutmayın. Bu, *exception_object_pointer_name* değişkeni için de geçerlidir.

### <a name="example"></a>Örnek

[Catch](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h
##  <a name="and_catch_all"></a>AND_CATCH_ALL

Önceki **TRY** bloğunda oluşturulan ek özel durum türlerini yakalamak için bir kod bloğu tanımlar.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak özel durum nesnesi işaretçisi için bir ad. İşaretçi adını **AND_CATCH_ALL** bloğundaki özel durum nesnesine erişmek için kullanabilirsiniz. Bu değişken sizin için bildirilmiştir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum türü yakalamak için **catch** makrosunu kullanın, sonra diğer sonraki tüm türleri yakalamak için AND_CATCH_ALL makrosu. AND_CATCH_ALL kullanıyorsanız, **TRY** bloğunu bir END_CATCH_ALL makrosu ile sonlandırın.

Özel durumun özel nedeni hakkında daha fazla bilgi almak için özel durum işleme kodu uygunsa özel durum nesnesini sorgulanamıyor olabilir. Bir sonraki dış özel durum çerçevesine kaydırmak için **AND_CATCH_ALL** bloğunda THROW_LAST makrosunu çağırın. **AND_CATCH_ALL** önceki **catch** veya **AND_CATCH_ALL** bloğunun sonunu işaretler.

> [!NOTE]
>  **AND_CATCH_ALL** bloğu C++ kapsam olarak tanımlanır (küme ayraçları tarafından belirlenir). Bu kapsamda değişkenler bildirirseniz, bunların yalnızca o kapsam içinde erişilebilir olduğunu unutmayın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="end_catch"></a>END_CATCH

Son **catch** veya **AND_CATCH** bloğunun sonunu işaretler.

```
END_CATCH
```

### <a name="remarks"></a>Açıklamalar

END_CATCH makrosu hakkında daha fazla bilgi için, bkz. [özel durumlar](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="end_catch_all"></a>END_CATCH_ALL

Son **CATCH_ALL88** veya **AND_CATCH_ALL** bloğunun sonunu işaretler.

```
END_CATCH_ALL
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="throw"></a>THROW (MFC)

Belirtilen özel durumu oluşturur.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer*<br/>
`CException`türetilen bir özel durum nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir kesme programı yürütmesi **oluşturun** ve denetim, programınızda ilişkili **catch** bloğuna geçer. **Catch** bloğunu sağlamadıysanız, denetim bir hata iletisi yazdıran ve çıkış yapan bir Microsoft Foundation Class Kitaplığı modüle geçirilir.

Daha fazla bilgi için bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="throw_last"></a>THROW_LAST

Bir sonraki dış **catch** bloğuna geri dönüş özel durumunu oluşturur.

```
THROW_LAST()
```

### <a name="remarks"></a>Açıklamalar

Bu makro yerel olarak oluşturulan bir özel durum oluşturmanıza olanak sağlar. Az önce yakalandığı bir özel durum yapmayı denerseniz, normalde kapsam dışına gider ve silinir. **THROW_LAST**, özel durum sonraki **catch** işleyicisine doğru şekilde geçirilir.

Daha fazla bilgi için bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Örnek

[CFile:: Abort](../../mfc/reference/cfile-class.md#abort)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowarchiveexception"></a>AfxThrowArchiveException

Bir arşiv özel durumu oluşturur.

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Parametreler

*sağlamak*<br/>
Özel durumun nedenini gösteren bir tamsayı belirtir. Olası değerlerin listesi için bkz. [CArchiveException:: m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
Özel duruma neden olan `CArchive` nesnesinin adını içeren bir dizeye işaret eder (varsa).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowfileexception"></a>AfxThrowFileException

Bir dosya özel durumu oluşturur.

```
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*sağlamak*<br/>
Özel durumun nedenini gösteren bir tamsayı belirtir. Olası değerlerin listesi için bkz. [CFileException:: m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsError*<br/>
Özel durumun nedenini belirten işletim sistemi hata numarasını (varsa) içerir. Hata kodlarının listelenmesi için bkz. işletim sistemi el kitabı.

*lpszFileName*<br/>
Özel duruma neden olan dosyanın adını içeren bir dizeye işaret eder (varsa).

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata koduna göre nedeni belirlemekten siz sorumlusunuz.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

## <a name="afxthrowinvalidargexception"></a>AfxThrowInvalidArgException

Geçersiz bir bağımsız değişken özel durumu oluşturur.

### <a name="syntax"></a>Sözdizimi

```
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Açıklamalar

Geçersiz bağımsız değişkenler kullanıldığında bu işlev çağrılır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="afxthrowmemoryexception"></a>AfxThrowMemoryException

Bir bellek özel durumu oluşturur.

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Temeldeki sistem bellek ayırıcıları ( **malloc** ve [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows işlevi) çağrıları başarısız olursa bu işlevi çağırın. Bellek ayırma başarısız olursa **Yeni** bir bellek özel durumu otomatik olarak **oluşturabileceğinden yeni** için bu dosyayı çağırmanız gerekmez.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException

Desteklenmeyen bir özellik için isteğin sonucu olan bir özel durum oluşturur.

```
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowresourceexception"></a>AfxThrowResourceException

Bir kaynak özel durumu oluşturur.

```
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, normalde bir Windows kaynağı yüklenemediğinde çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowuserexception"></a>AfxThrowUserException

Son Kullanıcı işlemini durdurmak için bir özel durum oluşturur.

```
void AfxThrowUserException();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle `AfxMessageBox` kullanıcıya bir hata bildirdikten hemen sonra çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException

OLE Otomasyonu işlevi içinde bir özel durum oluşturmak için bu işlevi kullanın.

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

*wCode*<br/>
Uygulamanıza özel bir hata kodu.

*lpszDescription*<br/>
Hatanın cobilanço açıklaması.

*Ndescriptionıd*<br/>
Cobilanço hata açıklaması için kaynak KIMLIĞI.

*Nhelpıd*<br/>
Uygulamanızın yardımı için yardım bağlamı (. HLP) dosyası.

### <a name="remarks"></a>Açıklamalar

Bu işleve sunulan bilgiler, itici uygulama (Microsoft Visual Basic veya başka bir OLE Otomasyon istemci uygulaması) tarafından görüntülenebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxthrowoleexception"></a>AfxThrowOleException

`COleException` türünde bir nesne oluşturur ve bir özel durum oluşturur.

```
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*SC*<br/>
Özel durumun nedenini gösteren bir OLE durum kodu.

*HR*<br/>
Özel durumun nedenini gösteren bir sonuç kodu için tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bir HRESULT bağımsız değişkeni olarak alan sürüm, bu sonuç kodunu ilgili SCODE 'a dönüştürür. HRESULT ve SCODE hakkında daha fazla bilgi için, bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="afxthrowdaoexception"></a>AfxThrowDaoException

Kendi kodunuzda [CDaoException](../../mfc/reference/cdaoexception-class.md) türünde bir özel durum oluşturmak için bu işlevi çağırın.

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Parametreler

*nAfxDaoError*<br/>
Bir DAO genişletilmiş hata kodunu temsil eden bir tamsayı değeri, bu, [CDaoException:: m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)altında listelenen değerlerden biri olabilir.

*SCODE*<br/>
SCODE türünde bir DAO 'dan OLE hata kodu. Bilgi için bkz. [CDaoException:: m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Açıklamalar

Çerçeve `AfxThrowDaoException`de çağırır. Çağrın içinde, parametrelerden birini veya her ikisini de geçirebilirsiniz. Örneğin, **CDaoException:: nAfxDaoError** içinde tanımlanan hatalardan birini yükseltmek istiyorsanız ancak *SCODE* parametresini ilgilenmezseniz, *nAfxDaoError* parametresinde geçerli bir kod geçirin ve *SCODE*için varsayılan değeri kabul edin.

MFC DAO sınıflarıyla ilgili özel durumlar hakkında daha fazla bilgi için bu kitapta sınıf `CDaoException` ve makale [özel durumları: veritabanı özel](../../mfc/exceptions-database-exceptions.md)durumları ' na bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

##  <a name="afxthrowdbexception"></a>AfxThrowDBException

Kendi kodunuzda `CDBException` türünde bir özel durum oluşturmak için bu işlevi çağırın.

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*Nekcode*<br/>
Özel durumun oluşturulmasına neden olan hata türünü tanımlayarak, RETCODE türünde bir değer.

*pdb*<br/>
Özel durumun ilişkilendirildiği veri kaynağı bağlantısını temsil eden `CDatabase` nesnesine yönelik bir işaretçi.

*bağlayıcıları*<br/>
Özel durumun ilişkilendirildiği deyim tanıtıcısını belirten bir ODBC HSTMT tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Çerçeve, ODBC API işlevine yapılan çağrıdan bir ODBC EKCODE aldığında `AfxThrowDBException` çağırır ve expectable hatası yerine REDıCODE 'u olağanüstü bir durum olarak yorumlar. Örneğin, bir disk okuma hatası nedeniyle bir veri erişim işlemi başarısız olabilir.

ODBC tarafından tanımlanan EKCODE değerleri hakkında daha fazla bilgi için, Windows SDK bölümünde "durum ve hata bilgilerini alma" başlıklı Bölüm 8 ' i inceleyin. Bu kodlara MFC uzantıları hakkında daha fazla bilgi için bkz. Class [CDBException](../../mfc/reference/cdbexception-class.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

##  <a name="afxabort"></a>AfxAbort

MFC tarafından sağlanan varsayılan sonlandırma işlevi.

```
void  AfxAbort();
```

### <a name="remarks"></a>Açıklamalar

`AfxAbort`, işlenmeyen bir yakalanamayan özel durum gibi önemli bir hata olduğunda MFC üye işlevleri tarafından dahili olarak çağrılır. Kurtulamadığında çok zararlı bir hatayla karşılaştığınızda `AfxAbort` nadir bir durumda çağırabilirsiniz.

### <a name="example"></a>Örnek

[Catch](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AFX. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CException Sınıfı](cexception-class.md)<br/>
[CInvalidArgException Sınıfı](cinvalidargexception-class.md)
