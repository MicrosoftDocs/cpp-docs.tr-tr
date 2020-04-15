---
title: CException Sınıfı
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
ms.openlocfilehash: c3742db7475e626b18e9c073a0b7417a8034863f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373949"
---
# <a name="cexception-class"></a>CException Sınıfı

Microsoft Hazırlık Sınıfı Kitaplığı'ndaki tüm özel durumlar için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CException::CException](#cexception)|Bir `CException` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CException::Delete](#delete)|Bir `CException` nesneyi siler.|
|[CException::ReportError](#reporterror)|İleti kutusundaki bir hata iletisini kullanıcıya bildirir.|

## <a name="remarks"></a>Açıklamalar

Soyut `CException` bir taban sınıf olduğundan, nesneleri doğrudan oluşturamazsınız; `CException` türemiş sınıfların nesnelerini oluşturmanız gerekir. Kendi `CException`stil sınıfınızı oluşturmanız gerekiyorsa, yukarıda model olarak listelenen türemiş sınıflardan birini kullanın. Türemiş sınıfında da `IMPLEMENT_DYNAMIC`'.

Türemiş sınıflar ve açıklamaları aşağıda listelenmiştir:

|||
|-|-|
|[Csimpleexception](../../mfc/reference/csimpleexception-class.md)|Kaynak açısından kritik MFC özel durumları için bir taban sınıf|
|[CInvalidArgİst](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken özel durum durumu|
|[Cmemoryexception](../../mfc/reference/cmemoryexception-class.md)|Bellek dışı özel durum|
|[Cnotsupportedexception](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem isteği|
|[Carchiveexception](../../mfc/reference/carchiveexception-class.md)|Arşive özgü özel durum|
|[Cfileexception](../../mfc/reference/cfileexception-class.md)|Dosyaya özgü özel durum|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows kaynağı bulunamadı veya güvenilir değil|
|[Coleexception](../../mfc/reference/coleexception-class.md)|OLE özel durumu|
|[Cdbexception](../../mfc/reference/cdbexception-class.md)|Veritabanı özel durumu (diğer bir şekilde Açık Veritabanı Bağlantısına dayalı MFC veritabanı sınıfları için ortaya çıkan özel durum koşulları)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE sevk (otomasyon) istisnası|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Kaynağın bulunamadıgini belirten özel durum|
|[Cdaoexception](../../mfc/reference/cdaoexception-class.md)|Veri erişim nesnesi özel durumu (diğer bir süre DAO sınıfları için ortaya çıkan özel durum koşulları)|
|[Cınternetexception](../../mfc/reference/cinternetexception-class.md)|Internet özel durumu (diğer bir süre, Internet sınıfları için ortaya çıkan özel durum koşulları).|

Bu özel durumlar [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [denemek](exception-processing.md#try), [yakalamak](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch)ve [end_catch](exception-processing.md#end_catch) makroları ile kullanılmak üzere tasarlanmıştır. Özel durumlar hakkında daha fazla bilgi için [Özel Durum İşleme'ye](exception-processing.md)bakın veya [Özel Durum İşleme (MFC)](../exception-handling-in-mfc.md)makalesine bakın.

Belirli bir özel durumu yakalamak için uygun türemiş sınıfı kullanın. Her türlü özel durum türünü `CException`yakalamak için CObject'i kullanın ve `CException`ardından [CObject::IsKindOf'u](cobject-class.md#iskindof) türetilmiş sınıflar arasında ayırt etmek için kullanın. Dinamik `CObject::IsKindOf` tür denetiminden yararlanmak için yalnızca [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) makrosuyla bildirilen sınıflar için çalıştığını unutmayın. Oluşturduğunuz herhangi bir `CException`türemiş `IMPLEMENT_DYNAMIC` sınıf da makro yu kullanmalıdır.

Özel durumlar hakkındaki ayrıntıları, 'türetilmiş sınıflardan herhangi biriyle `CException`çalışan iki üye işlev olan [GetErrorMessage](cfileexception-class.md#geterrormessage) veya [ReportError'ı](#reporterror)arayarak kullanıcıya bildirebilirsiniz.

Bir özel durum makrolardan biri tarafından `CException` yakalanırsa, nesne otomatik olarak silinir; kendiniz silmeyin. Bir özel durum **catch** anahtar sözcüğü kullanılarak yakalanırsa, otomatik olarak silinmez. Bir exeption nesnesinin ne zaman silindiği hakkinda daha fazla bilgi için [ısıtım Kullanımına (MFC)](../exception-handling-in-mfc.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](cobject-class.md)

`CException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cexceptioncexception"></a><a name="cexception"></a>CException::CException

Bu üye işlev `CException` bir nesne oluşturuyor.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*b_AutoDelete*<br/>
Nesnenin belleği yığına ayrılmışsa `CException` DOĞRU'yu belirtin. Bu, üye `CException` işlev özel durumu `Delete` silmek için çağrıldığında nesnenin silinmesine neden olur. `CException` Nesne yığındaysa veya genel bir nesneyse FALSE belirtin. Bu durumda, `CException` `Delete` üye işlev çağrıldığında nesne silinmez.

### <a name="remarks"></a>Açıklamalar

Normalde bu yapıcıyı doğrudan aramanız gerekmez. Özel durum atan bir işlev, türemiş bir `CException`sınıfın bir örneğini oluşturmalı ve oluşturucuyu çağırmalıdır veya önceden tanımlanmış bir tür atmak için [AfxThrowFileException](exception-processing.md#afxthrowfileexception)gibi MFC atma işlevlerinden birini kullanmalıdır. Bu dokümantasyon yalnızca tamlık için sağlanır.

## <a name="cexceptiondelete"></a><a name="delete"></a>CException::Delete

Bu işlev, nesnenin `CException` yığında oluşturulup oluşturulmamasını denetler ve eğer öyleyse, nesneüzerindeki **silme** işleciçağırır.

```
void Delete();
```

### <a name="remarks"></a>Açıklamalar

Bir `CException` nesneyi silerken, `Delete` özel durumu silmek için üye işlevi kullanın. Nesne genel bir nesne olabileceğinden veya yığında oluşturulmuş olabileceğinden, silme işlecinin doğrudan kullanılmasın. **delete** `CException`

Nesne oluşturulduğunda nesnenin silinip silinmeyeceğini belirtebilirsiniz. Daha fazla bilgi için [Bkz. CException::CException](#cexception).

Yalnızca C++ `Delete` **try**- **catch** mekanizmasını kullanıyorsanız aramanız gerekir. MFC makroları **TRY** ve **CATCH**kullanıyorsanız, bu makrolar otomatik olarak bu işlevi çağırır.

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

## <a name="cexceptionreporterror"></a><a name="reporterror"></a>CException::ReportError

İleti kutusundaki hata metnini kullanıcıya bildirmek için bu üye işlevini arayın.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Parametreler

*nTipi*<br/>
İleti kutusunun stilini belirtir. [İleti kutusu stillerinin](styles-used-by-mfc.md#message-box-styles) herhangi bir birleşimini kutuya uygulayın. Bu parametreyi belirtmezseniz, varsayılan MB_OK.

*nMessageID*<br/>
Özel durum nesnesinin hata iletisi yoksa görüntülenecek iletinin kaynak kimliğini (string table entry) belirtir. 0 ise, "Hata iletisi yok" iletisi görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Bir `AfxMessageBox` değer; aksi takdirde ileti kutusunu görüntülemek için yeterli bellek yoksa 0. Olası iade değerleri için [AfxMessageBox'a](cstring-formatting-and-message-box-display.md#afxmessagebox) bakın.

### <a name="example"></a>Örnek

Burada kullanımı bir `CException::ReportError`örnektir. Başka bir örnek için, [CATCH](exception-processing.md#catch)örneğine bakın.

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

[CObject Sınıfı](cobject-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Özel Durum İşleme](exception-processing.md)<br/>
[Nasıl Yaparım: Kendi Özel Özel Durum Sınıflarımı Oluşturun](https://go.microsoft.com/fwlink/p/?linkid=128045)
