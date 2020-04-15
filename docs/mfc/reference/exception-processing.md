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
ms.openlocfilehash: d819c170f47ea259e776bce6db0a6971e3f54bec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365711"
---
# <a name="exception-processing"></a>Özel Durum İşleme

Bir program yürütüldüğünde, "özel durumlar" adı verilen bir dizi anormal durum ve hata oluşabilir. Bunlar arasında bellek tükenen çalışma, kaynak ayırma hataları ve dosyaların bulunamaması sayılabilir.

Microsoft Hazırlık Sınıf Kitaplığı, C++için ANSI standartları komitesi tarafından önerilen den sonra yakından modellenen bir özel durum işleme düzeni kullanır. Anormal bir durumla karşılaşabilecek bir işlevi çağırmadan önce bir özel durum işleyicisi ayarlanmalıdır. İşlev anormal bir durumla karşılaşırsa, bir özel durum atar ve denetim özel durum işleyicisine geçirilir.

Microsoft Foundation Class Library ile birlikte verilen çeşitli makrolar özel durum işleyicileri ayarlar. Diğer genel işlevlerin bir dizi özel özel durumlar atmak ve gerekirse programları sonlandırmak için yardımcı olur. Bu makrolar ve genel işlevler aşağıdaki kategorilere ayrılır:

- Özel durum işleyicinizi yapılandıran özel durum makroları.

- Özel durum atma işlevleri), belirli türlerin özel durumları oluşturur.

- Program sonlandırmaneden sonlandırma işlevleri.

Örnekler ve daha fazla ayrıntı için [Özel Durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="exception-macros"></a>Özel Durum Makroları

|||
|-|-|
|[Deneyin](#try)|Özel durum işleme için bir kod bloğu belirler.|
|[Yakalamak](#catch)|Önceki **TRY** bloğundan bir özel durum yakalamak için bir kod bloğu belirler.|
|[CATCH_ALL](#catch_all)|Önceki **TRY** bloğundan tüm özel durumları yakalamak için bir kod bloğu belirler.|
|[And_catch](#and_catch)|Önceki **TRY** bloğundan ek özel durum türlerini yakalamak için bir kod bloğu belirler.|
|[AND_CATCH_ALL](#and_catch_all)|Önceki **TRY** bloğunda atılan diğer tüm ek özel durum türlerini yakalamak için bir kod bloğu belirler.|
|[End_catch](#end_catch)|Son **CATCH** veya **AND_CATCH** kod bloğunu sona erdirer.|
|[END_CATCH_ALL](#end_catch_all)|Son **CATCH_ALL** kod bloğunu sona erdiriyor.|
|[Atmak](#throw)|Belirtilen bir özel durum atar.|
|[Throw_last](#throw_last)|Şu anda işlenen özel durumu sonraki dış işleyiciye atar.|

### <a name="exception-throwing-functions"></a>Özel Durum Atma Fonksiyonları

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Arşiv özel durumu atar.|
|[AfxThrowFileException](#afxthrowfileexception)|Bir dosya özel durum atar.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Geçersiz bir bağımsız değişken özel durumu atar.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Bir bellek özel durum atar.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Desteklenmeyen bir özel durum atar.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows kaynak bulunmayan bir özel durum atar.|
|[AfxThrowUserException](#afxthrowuserexception)|Kullanıcı tarafından başlatılan program eyleminde bir özel durum atar.|

MFC, OLE özel durumları için özel olarak iki özel durum atma işlevi sağlar:

### <a name="ole-exception-functions"></a>OLE Özel Durum Fonksiyonları

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE otomasyon işlevi içinde bir özel durum atar.|
|[AfxThrowOleException](#afxthrowoleexception)|OLE özel durumu atar.|

Veritabanı özel durumlarını desteklemek için veritabanı sınıfları iki özel durum sınıfı `CDBException` ve `CDaoException`özel durum türlerini desteklemek için genel işlevler sağlar:

### <a name="dao-exception-functions"></a>DAO Özel Durum Fonksiyonları

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|Kendi kodunuzdan bir [CDaoException](../../mfc/reference/cdaoexception-class.md) atar.|
|[AfxThrowDBException](#afxthrowdbexception)|Kendi kodunuzdan bir [CDBException](../../mfc/reference/cdbexception-class.md) atar.|

MFC aşağıdaki sonlandırma işlevini sağlar:

### <a name="termination-functions"></a>Sonlandırma Fonksiyonları

|||
|-|-|
|[AfxAbort](#afxabort)|Önemli bir hata oluştuğunda bir uygulamayı sonlandırmak için çağrıldı.|

## <a name="try"></a><a name="try"></a>Deneyin

**TRY** bloğu kurar.

```
TRY
```

### <a name="remarks"></a>Açıklamalar

**TRY** bloğu, özel durumlar atabilecek bir kod bloğunu tanımlar. Bu özel durumlar aşağıdaki **CATCH** ve **AND_CATCH** bloklarda işlenir. Yinelemeye izin verilir: özel durumlar, bunları yok saymak veya THROW_LAST makrosu kullanılarak dış **try** bloğuna geçirilebilir. **TRY** bloğunu END_CATCH veya END_CATCH_ALL makrosuyla sonlayın.

Daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="example"></a>Örnek

[CATCH](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

Üstbilgi: afx.h

## <a name="catch"></a><a name="catch"></a>Yakalamak

Önceki **TRY** bloğunda atılan ilk özel durum türünü yakalayan bir kod bloğu tanımlar.

```
CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test etmek için özel durum türünü belirtir. Standart özel durum sınıflarının listesi için [CException](../../mfc/reference/cexception-class.md)sınıfına bakın.

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak bir özel durum nesnesi işaretçisi için bir ad belirtir. **Catch** bloğundaki özel durum nesnesine erişmek için işaretçi adını kullanabilirsiniz. Bu değişken sizin için beyan ediilebedilir.

### <a name="remarks"></a>Açıklamalar

Özel durum işleme kodu, özel durum belirli nedeni hakkında daha fazla bilgi almak için, uygunsa özel durum nesnesini sorgulayabilir. İşlemeyi bir sonraki dış özel durum çerçevesine kaydırmak için THROW_LAST makroyu çağırın. **TRY** bloğunu END_CATCH bir makro ile sonlayın.

*exception_class* sınıfsa, `CException`tüm özel durum türleri yakalanır. [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) üye işlevini kullanarak hangi özel durum ların atıldığını belirleyebilirsiniz. Çeşitli özel durumlar yakalamanın daha iyi bir yolu, her biri farklı bir özel durum türüne sahip sıralı **AND_CATCH** deyimleri kullanmaktır.

Özel durum nesnesi işaretçisi makro tarafından oluşturulur. Kendin beyan etmene gerek yok.

> [!NOTE]
> **CATCH** bloğu, ayraçlar tarafından tanımlanan C++ kapsamı olarak tanımlanır. Bu kapsamda değişkenleri bildirirseniz, bunlara yalnızca bu kapsamda erişilebilir. Bu exception_object_pointer_name *için*de geçerlidir.

Özel durumlar ve CATCH makrosu hakkında daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

## <a name="catch_all"></a><a name="catch_all"></a>CATCH_ALL

Önceki **TRY** bloğunda atılan tüm özel durum türlerini yakalayan bir kod bloğu tanımlar.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak bir özel durum nesnesi işaretçisi için bir ad belirtir. `CATCH_ALL` Blok içindeki özel durum nesnesine erişmek için işaretçi adını kullanabilirsiniz. Bu değişken sizin için beyan ediilebedilir.

### <a name="remarks"></a>Açıklamalar

Özel durum işleme kodu, özel durum belirli nedeni hakkında daha fazla bilgi almak için, uygunsa özel durum nesnesini sorgulayabilir. İşlemeyi `THROW_LAST` bir sonraki dış özel durum çerçevesine kaydırmak için makroyu çağırın. **CATCH_ALL**kullanıyorsanız TRY **bloğunu** END_CATCH_ALL bir makro ile sonlayın.

> [!NOTE]
> **CATCH_ALL** bloğu, ayraçlar tarafından tanımlanan C++ kapsamı olarak tanımlanır. Bu kapsamda değişkenleri bildirirseniz, bunlara yalnızca bu kapsamda erişilebilir.

Özel durumlar hakkında daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="example"></a>Örnek

CFile örneğine [bakın:Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="and_catch"></a><a name="and_catch"></a>And_catch

**Önceki** TRY bloğuna atılan ek özel durum türlerini yakalamak için bir kod bloğu tanımlar.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_class*<br/>
Test etmek için özel durum türünü belirtir. Standart özel durum sınıflarının listesi için [CException](../../mfc/reference/cexception-class.md)sınıfına bakın.

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak bir özel durum nesnesi işaretçisi için bir ad. **AND_CATCH** bloğundaki özel durum nesnesine erişmek için işaretçi adını kullanabilirsiniz. Bu değişken sizin için beyan ediilebedilir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum türünü yakalamak için CATCH makrosu, ardından her bir türü yakalamak için makroAND_CATCH kullanın. **TRY** bloğunu END_CATCH bir makro ile sonlayın.

Özel durum işleme kodu, özel durum belirli nedeni hakkında daha fazla bilgi almak için, uygunsa özel durum nesnesini sorgulayabilir. İşlemeyi bir sonraki dış özel durum çerçevesine kaydırmak için **AND_CATCH** bloğu içindeki THROW_LAST makrosunu çağırın. **AND_CATCH** önceki **CATCH** veya **AND_CATCH** bloğun un sonunu işaretler.

> [!NOTE]
> **AND_CATCH** bloğu C++ kapsamı (kıvırcık ayraçlarla tanımlanan) olarak tanımlanır. Bu kapsamda değişkenleri bildirirseniz, yalnızca bu kapsamda erişilebilir olduklarını unutmayın. Bu, *exception_object_pointer_name* değişkeni için de geçerlidir.

### <a name="example"></a>Örnek

[CATCH](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="and_catch_all"></a><a name="and_catch_all"></a>AND_CATCH_ALL

**Önceki** TRY bloğuna atılan ek özel durum türlerini yakalamak için bir kod bloğu tanımlar.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer_name*<br/>
Makro tarafından oluşturulacak bir özel durum nesnesi işaretçisi için bir ad. **AND_CATCH_ALL** bloğundaki özel durum nesnesine erişmek için işaretçi adını kullanabilirsiniz. Bu değişken sizin için beyan ediilebedilir.

### <a name="remarks"></a>Açıklamalar

Bir özel durum türünü yakalamak için **CATCH** makrosu, ardından gelen tüm türleri yakalamak için makroAND_CATCH_ALL kullanın. AND_CATCH_ALL kullanıyorsanız, **TRY** bloğunu END_CATCH_ALL bir makro ile sonlayın.

Özel durum işleme kodu, özel durum belirli nedeni hakkında daha fazla bilgi almak için, uygunsa özel durum nesnesini sorgulayabilir. İşlemeyi bir sonraki dış özel durum çerçevesine kaydırmak için **AND_CATCH_ALL** bloğu içindeki THROW_LAST makroyu çağırın. **AND_CATCH_ALL** önceki **CATCH** veya **AND_CATCH_ALL** bloğun un sonunu işaretler.

> [!NOTE]
> **AND_CATCH_ALL** bloğu C++ kapsamı (ayraçlarla tanımlanan) olarak tanımlanır. Bu kapsamda değişkenleri bildirirseniz, yalnızca bu kapsamda erişilebilir olduklarını unutmayın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="end_catch"></a><a name="end_catch"></a>End_catch

Son **CATCH** veya **AND_CATCH** bloğunun sonunu işaretler.

```
END_CATCH
```

### <a name="remarks"></a>Açıklamalar

makro END_CATCH hakkında daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="end_catch_all"></a><a name="end_catch_all"></a>END_CATCH_ALL

Son **CATCH_ALL88** veya **AND_CATCH_ALL** bloğun sonunu işaretler.

```
END_CATCH_ALL
```

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="throw-mfc"></a><a name="throw"></a>ATMA (MFC)

Belirtilen özel durumu atar.

```
THROW(exception_object_pointer)
```

### <a name="parameters"></a>Parametreler

*exception_object_pointer*<br/>
Türetilen bir özel `CException`durum nesnesine işaret etmek.

### <a name="remarks"></a>Açıklamalar

**THROW,** programınızdaki ilişkili **CATCH** bloğuna denetimi geçirerek program yürütmesini kesintiye uğrattı. **CATCH** bloğunu sağlamadıysanız, denetim bir hata iletisi yazdıran ve çıkan bir Microsoft Foundation Class Library modülüne geçirilir.

Daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="throw_last"></a><a name="throw_last"></a>Throw_last

Özel durumu bir sonraki dış **CATCH** bloğuna geri atar.

```
THROW_LAST()
```

### <a name="remarks"></a>Açıklamalar

Bu makro, yerel olarak oluşturulan bir özel durum atmanıza olanak tanır. Yeni yakaladığınız bir özel durum atmaya çalışırsanız, normalde kapsam dışına çıkar ve silinir. **THROW_LAST,** özel durum bir sonraki **CATCH** işleyicisine doğru bir şekilde aktarılır.

Daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

### <a name="example"></a>Örnek

CFile örneğine [bakın:Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException

Arşiv özel durumu atar.

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Parametreler

*Neden*<br/>
Özel durum nedenini gösteren bir arayıcı belirtir. Olası değerlerin listesi için [Bkz. CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
Özel durum (varsa) neden `CArchive` nesnenin adını içeren bir dize işaret eder.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException

Bir dosya özel durum atar.

```
void AfxThrowFileException(
    int cause,
    LONG lOsError = -1,
    LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Parametreler

*Neden*<br/>
Özel durum nedenini gösteren bir arayıcı belirtir. Olası değerlerin listesi için [Bkz. CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsError*<br/>
Özel durum nedenini belirten işletim sistemi hata numarasını (varsa) içerir. Hata kodlarının listelenmesi için işletim sistemi kılavuzuna bakın.

*lpszFileName*<br/>
Özel durum (varsa) neden dosyanın adını içeren bir dize işaret eder.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata kodunu temel alan nedeni belirlemekten siz sorumlusunuz.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowinvalidargexception"></a><a name="afxthrowinvalidargexception"></a>AfxThrowInvalidArgException

Geçersiz bir bağımsız değişken özel durumu atar.

### <a name="syntax"></a>Sözdizimi

```
void AfxThrowInvalidArgException( );
```

### <a name="remarks"></a>Açıklamalar

Geçersiz bağımsız değişkenler kullanıldığında bu işlev çağrılır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException

Bir bellek özel durum atar.

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Altta yatan sistem bellek ayırıcılarına **(malloc** ve [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows işlevi gibi) yapılan çağrılar başarısız olursa bu işlevi arayın. Yeni bellek ayırma başarısız olursa otomatik olarak bir bellek özel durum **atacaktır,** çünkü **yeni** aramak gerekmez.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException

Desteklenmeyen bir özellik isteğinin sonucu olan bir özel durum atar.

```
void AfxThrowNotSupportedException();
```

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException

Kaynak özel durumu atar.

```
void  AfxThrowResourceException();
```

### <a name="remarks"></a>Açıklamalar

Windows kaynağı yüklenemediğinde bu işlev normal olarak çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException

Son kullanıcı işlemini durdurmak için bir özel durum atar.

```
void AfxThrowUserException();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev normalde kullanıcıya `AfxMessageBox` bir hata bildirdikten hemen sonra çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException

OLE otomasyon işlevi içinde bir özel durum atmak için bu işlevi kullanın.

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
Uygulamanıza özgü bir hata kodu.

*lpszAçıklama*<br/>
Hatanın sözlü açıklaması.

*nDescriptionID*<br/>
Sözel hata açıklaması için kaynak kimliği.

*nHelpID*<br/>
Uygulamanızın yardımı için bir yardım bağlamı (. HLP) dosyası.

### <a name="remarks"></a>Açıklamalar

Bu işleve sağlanan bilgiler sürüş uygulaması (Microsoft Visual Basic veya başka bir OLE otomasyon istemcisi uygulaması) tarafından görüntülenebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException

Türde `COleException` bir nesne oluşturur ve bir özel durum atar.

```
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*Sc*<br/>
Özel durumun nedenini gösteren bir OLE durum kodu.

*Hr*<br/>
Özel durum nedenini gösteren bir sonuç koduna işle.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olarak Bir HRESULT alan sürüm, bu sonuç kodunu ilgili SCODE'a dönüştürür. HRESULT ve SCODE hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException

Kendi kodunuzdan [CDaoException](../../mfc/reference/cdaoexception-class.md) türünden bir özel durum atmak için bu işlevi arayın.

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Parametreler

*nAfxDaoError*<br/>
CDaoException altında listelenen değerlerden biri olabilir DAO genişletilmiş hata kodu temsil eden bir tamsayı [değeri::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*Scode*<br/>
DAO'dan bir OLE hata kodu, SCODE türü. Bilgi için [CDaoException::m_scode.](../../mfc/reference/cdaoexception-class.md#m_scode)

### <a name="remarks"></a>Açıklamalar

Çerçeve de `AfxThrowDaoException`çağırır . Aramanızda, parametrelerden birini veya her ikisini de geçebilirsiniz. Örneğin, **CDaoException::nAfxDaoError'ta** tanımlanan hatalardan birini yükseltmek istiyorsanız, ancak *kod* parametresini umursamıyorsanız, *nAfxDaoError* parametresinde geçerli bir kod geçirin ve *scode*için varsayılan değeri kabul edin.

MFC DAO sınıfları ile ilgili özel durumlar `CDaoException` hakkında bilgi için, bu kitaptaki sınıfa ve [Özel Durumlar: Veritabanı Özel Durumları](../../mfc/exceptions-database-exceptions.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdb.h

## <a name="afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException

Kendi kodunuzdan tür bir `CDBException` özel durum atmak için bu işlevi arayın.

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
Özel durum atılmasına neden olan hata türünü tanımlayan, tür RETCODE değeri.

*Pdb*<br/>
Özel durum `CDatabase` ilişkili veri kaynağı bağlantısını temsil eden nesneye bir işaretçi.

*Hstmt*<br/>
Özel durum ilişkili deyimi işletmek belirten bir ODBC HSTMT kolu.

### <a name="remarks"></a>Açıklamalar

Çerçeve, `AfxThrowDBException` bir çağrıdan ODBC API işlevine Bir ODBC RETCODE aldığında çağırır ve RETCODE'u beklenen bir hata dan ziyade istisnai bir durum olarak yorumlar. Örneğin, bir disk okuma hatası nedeniyle bir veri erişim işlemi başarısız olabilir.

ODBC tarafından tanımlanan RETCODE değerleri hakkında bilgi için Windows SDK'daki Bölüm 8'e bakın: "Durum ve Hata Bilgileri Alma". Bu kodların MFC uzantıları hakkında bilgi için, sınıf [CDBException](../../mfc/reference/cdbexception-class.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="afxabort"></a><a name="afxabort"></a>AfxAbort

MFC tarafından sağlanan varsayılan sonlandırma işlevi.

```
void  AfxAbort();
```

### <a name="remarks"></a>Açıklamalar

`AfxAbort`gerçekleştirilemeyen bir yakalanmış özel durum gibi önemli bir hata olduğunda, MFC üye işlevleri tarafından dahili olarak çağrılır. Kurtaramayacağınız `AfxAbort` bir felaket hatasıyla karşılaştığınızda nadir durum arayabilirsiniz.

### <a name="example"></a>Örnek

[CATCH](#catch)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afx.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CException Sınıfı](cexception-class.md)<br/>
[CInvalidArgException Sınıf](cinvalidargexception-class.md)
