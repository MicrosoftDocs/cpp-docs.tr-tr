---
title: CException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: e27802e05c832d28d848d9eb1235d6ef5980b306
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841564"
---
# <a name="cexception-class"></a>CException sınıfı

Microsoft Foundation Class Kitaplığı tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CException:: CException](#cexception)|Bir `CException` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CException::D Sil](#delete)|Bir `CException` nesneyi siler.|
|[CException:: ReportError](#reporterror)|Kullanıcıya ileti kutusunda bir hata mesajı bildirir.|

## <a name="remarks"></a>Açıklamalar

`CException`Soyut bir temel sınıf olduğundan, `CException` nesneleri doğrudan oluşturamazsınız; türetilmiş sınıfların nesnelerini oluşturmanız gerekir. Kendi `CException` Stil sınıfınızı oluşturmanız gerekiyorsa, yukarıda listelenen türetilmiş sınıflardan birini model olarak kullanın. Türetilmiş sınıfınızın da kullandığından emin olun `IMPLEMENT_DYNAMIC` .

Türetilmiş sınıflar ve açıklamaları aşağıda listelenmiştir:

|Ad|Açıklama|
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Kaynak açısından kritik MFC özel durumları için temel sınıf|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken özel durum koşulu|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem isteği|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Arşive özgü özel durum|
|[CFileException](../../mfc/reference/cfileexception-class.md)|Dosyaya özgü özel durum|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows kaynağı bulunamadı veya oluşturulabilir değil|
|[Colet özel durumu](../../mfc/reference/coleexception-class.md)|OLE özel durumu|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Veritabanı özel durumu (diğer bir deyişle, açık veritabanı bağlantısını temel alan MFC veritabanı sınıfları için doğan özel durum koşulları)|
|[Cotadispatchexception](../../mfc/reference/coledispatchexception-class.md)|OLE dağıtma (Otomasyon) özel durumu|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Bir kaynağın bulunamadığını belirten özel durum|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Veri erişimi nesnesi özel durumu (diğer bir deyişle, DAO sınıfları için doğan özel durum koşulları)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Internet özel durumu (diğer bir deyişle, Internet sınıfları için doğan özel durum koşulları).|

Bu özel durumlar [throw](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [TRY](exception-processing.md#try), [catch](exception-processing.md#catch), [AND_CATCH](exception-processing.md#and_catch)ve [END_CATCH](exception-processing.md#end_catch) makrolarıyla birlikte kullanılmak üzere tasarlanmıştır. Özel durumlar hakkında daha fazla bilgi için bkz. [özel durum işleme](exception-processing.md)veya bkz. Makale [özel durum işleme (MFC)](../exception-handling-in-mfc.md).

Belirli bir özel durumu yakalamak için uygun türetilmiş sınıfı kullanın. Tüm özel durumların türlerini yakalamak için kullanın `CException` ve ardından, arasında türetilmiş sınıfları ayırt etmek Için [CObject:: IsKindOf](cobject-class.md#iskindof) kullanın `CException` . `CObject::IsKindOf`Dinamik tür denetlemesinin avantajlarından yararlanmak için yalnızca [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) makroıyla tanımlanmış sınıflar için geçerlidir. Oluşturduğunuz herhangi bir `CException` türetilmiş sınıf `IMPLEMENT_DYNAMIC` , makrosunu da kullanmalıdır.

Özel durumlar hakkındaki ayrıntıları, [GetErrorMessage](cfileexception-class.md#geterrormessage) veya [ReportError](#reporterror)' ı çağırarak ve herhangi bir türetilmiş sınıftan çalışan iki üye işlevini çağırarak bildirebilirsiniz `CException` .

Makrolardan biri tarafından bir özel durum yakalanmışsa, `CException` nesne otomatik olarak silinir; kendiniz silmeyin. Bir özel durum anahtar sözcüğü kullanılarak yakalanmışsa **`catch`** , otomatik olarak silinmez. Bir hata ayıklanın ne zaman silineceği hakkında daha fazla bilgi için bkz. [özel durum işleme (MFC)](../exception-handling-in-mfc.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cexceptioncexception"></a><a name="cexception"></a> CException:: CException

Bu üye işlevi bir `CException` nesnesi oluşturur.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*b_AutoDelete*<br/>
`CException`Nesnenin belleği yığında ayrılmışsa TRUE değerini belirtin. Bu, `CException` `Delete` özel durumu silmek için üye işlevi çağrıldığında nesnenin silinmesine neden olur. `CException`Nesne Stack içindeyse veya genel bir nesnese, false belirtin. Bu durumda, `CException` `Delete` üye işlevi çağrıldığında nesne silinmez.

### <a name="remarks"></a>Açıklamalar

Normalde bu oluşturucuyu doğrudan çağırmanız gerekmez. Özel durum oluşturan bir işlev `CException` , türetilmiş bir sınıfın örneğini oluşturmalı ve oluşturucusunu çağırmalıdır ya da önceden tanımlanmış bir tür oluşturmak Için [AFXTHROWFILEEXCEPTION](exception-processing.md#afxthrowfileexception)gibi MFC throw işlevlerinden birini kullanmalıdır. Bu belge yalnızca tamamlayıcı için sağlanır.

## <a name="cexceptiondelete"></a><a name="delete"></a> CException::D Sil

Bu işlev, `CException` nesnenin yığında oluşturulup oluşturulmadığını denetler ve varsa, **`delete`** nesne üzerindeki işlecini çağırır.

```cpp
void Delete();
```

### <a name="remarks"></a>Açıklamalar

Bir nesne silinirken `CException` , `Delete` özel durumu silmek için üye işlevini kullanın. **`delete`** `CException` Nesne genel bir nesne veya yığında oluşturulmuş olabileceği için doğrudan işlecini kullanmayın.

Nesne oluşturulduğunda nesnenin silinip silinmeyeceğini belirtebilirsiniz. Daha fazla bilgi için bkz. [CException:: CException](#cexception).

Yalnızca `Delete` C++ mekanizmasını kullanıyorsanız bu çağrıyı yapmanız gerekir **`try`** -  **`catch`** . MFC makrolarını kullanıyorsanız, **deneyin** ve **yakalayın**, bu makrolar otomatik olarak bu işlevi çağırır.

### <a name="example"></a>Örnek

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

## <a name="cexceptionreporterror"></a><a name="reporterror"></a> CException:: ReportError

Kullanıcıya bir ileti kutusunda hata metnini raporlamak için bu üye işlevi çağırın.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
İleti kutusunun stilini belirtir. [İleti kutusu stillerinin](styles-used-by-mfc.md#message-box-styles) herhangi bir birleşimini kutuya uygulayın. Bu parametreyi belirtmezseniz, varsayılan MB_OK.

*Nmessageıd*<br/>
Özel durum nesnesi bir hata mesajı içermiyorsa görüntülenecek bir iletinin kaynak KIMLIĞINI (dize tablosu girişi) belirtir. 0 ise, "hata iletisi yok" iletisi görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Bir `AfxMessageBox` değer; ileti kutusunu göstermek için yeterli bellek yoksa 0. Olası dönüş değerleri için bkz. [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) .

### <a name="example"></a>Örnek

Öğesinin kullanımına bir örnek aşağıda verilmiştir `CException::ReportError` . Başka bir örnek için bkz. [catch](exception-processing.md#catch)örneği.

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](cobject-class.md)<br/>
[Hiyerarşi grafiği](../hierarchy-chart.md)<br/>
[Özel durum Işleme](exception-processing.md)<br/>
[Nasıl yapılır: kendi özel özel durum sınıflarımı oluşturma](https://go.microsoft.com/fwlink/p/?linkid=128045)
