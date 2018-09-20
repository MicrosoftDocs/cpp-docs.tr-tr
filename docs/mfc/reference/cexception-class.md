---
title: CException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
dev_langs:
- C++
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 189a6bd675ef3dec467fac98584abd7edfb49c19
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433955"
---
# <a name="cexception-class"></a>CException sınıfı

Microsoft Foundation Class Kitaplığı'ndaki tüm özel durumlar için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CException::CException](#cexception)|Oluşturur bir `CException` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CException::Delete](#delete)|Siler bir `CException` nesne.|
|[CException::ReportError](#reporterror)|Bir ileti kutusunda bir hata iletisi, kullanıcıya bildirir.|

## <a name="remarks"></a>Açıklamalar

Çünkü `CException` oluşturamazsınız soyut bir temel sınıf `CException` nesneleri doğrudan; türetilen sınıfların nesneleri oluşturmanız gerekir. Kendi oluşturmanız gerekiyorsa `CException`-stil sınıf, model olarak yukarıda listelenen türetilmiş sınıflardan birini kullanın. Türetilmiş sınıfınızın ayrıca kullandığından emin olun `IMPLEMENT_DYNAMIC`.

Türetilmiş sınıfları ve açıklamaları aşağıda listelenmiştir:

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Kaynak kritik MFC özel durumları için temel sınıf|
|[Cınvalidargexception](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken özel durum koşulunu|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem iste|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Arşiv özel durum|
|[CFileException](../../mfc/reference/cfileexception-class.md)|Dosya özgü özel durum|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows kaynak bulunamadı veya değil|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE özel durumu|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Veritabanı özel durumu (açık veritabanı bağlantısı üzerinde göre MFC veritabanı sınıfları için ortaya çıkan diğer bir deyişle, özel durum koşulları)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE gönderme (Otomasyon) özel durumu|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Bir kaynak bulunamadı gösteren durum|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Veri erişim nesnesi özel durumu (DAO sınıfları için ortaya çıkan diğer bir deyişle, özel durum koşulları)|
|[Cınternetexception](../../mfc/reference/cinternetexception-class.md)|İnternet'e özel durum (Internet sınıfları için ortaya çıkan diğer bir deyişle, özel durum koşulları).|

Bu özel durumları ile kullanılmak üzere tasarlanmıştır [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [deneyin](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), ve [end_catch](exception-processing.md#end_catch) makroları. Özel durumları hakkında daha fazla bilgi için bkz. [özel durum işleme](exception-processing.md), veya makaleye göz atın [özel durum işleme (MFC)](../exception-handling-in-mfc.md).

Belirli bir özel durum yakalamak için uygun türetilen sınıfı kullanın. Özel durumları yakalama tüm türleri için kullanın `CException`ve ardından [CObject::IsKindOf](cobject-class.md#iskindof) arasında ayırt etmek için `CException`-türetilmiş sınıflar. Unutmayın `CObject::IsKindOf` sınıfları yalnızca çalışır bildirilen ile [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic) dinamik tür denetimi avantajlarından yararlanmak için makro. Tüm `CException`-oluşturduğunuz türetilmiş bir sınıf kullanması gereken `IMPLEMENT_DYNAMIC` makro çok.

Çağırarak kullanıcıya özel durumları hakkında ayrıntılar bildirebilirsiniz [GetErrorMessage](cfileexception-class.md#geterrormessage) veya [ReportError](#reporterror), iki üye işlevleri herhangi biri ile çalışan `CException`türetilmiş sınıflar.

Bir özel durum makroları biri tarafından yakalandığında `CException` nesne otomatik olarak silinir; kendiniz silmeyin. Kullanarak bir özel durum yakalandığında bir **catch** anahtar sözcüğü, otomatik olarak silinmez. Makaleye göz atın [özel durum işleme (MFC)](../exception-handling-in-mfc.md) ne zaman bir özel durum nesnesini silme hakkında daha fazla bilgi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cexception"></a>  CException::CException

Bu üye işlevi oluşturan bir `CException` nesne.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*b_AutoDelete*<br/>
TRUE ise belirtmek için bellek `CException` nesneyi yığında ayrılmış. Bu neden `CException` ne zaman Silinmiş nesne `Delete` üye işlevi, özel durum silmek için çağrılır. FALSE belirtin `CException` nesne yığında veya genel bir nesnedir. Bu durumda, `CException` nesne olmayacak ne zaman silinmiş `Delete` üye işlevi çağrılır.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan çağırmak hiçbir zaman normalde gerekir. Özel durum oluşturan bir işlev bir örneğini oluşturmanız gerekir bir `CException`-türetilmiş sınıf ve MFC'nin kullanımı throw işlevleri gibi oluşturucu veya çağrı [AfxThrowFileException](exception-processing.md#afxthrowfileexception), önceden tanımlanmış bir tür oluşturmak için. Bu belge, bütünlük açısından sağlanır.

##  <a name="delete"></a>  CException::Delete

Bu işlev olup olmadığını denetler. `CException` nesneyi yığında oluşturuldu ve bu durumda, çağrı **Sil** işlecinin nesne.

```
void Delete();
```

### <a name="remarks"></a>Açıklamalar

Silerken bir `CException` nesnesi `Delete` üye işlevi, özel durumu silinemedi. Kullanmayın **Sil** işleci doğrudan, çünkü `CException` nesne yığın üzerinde oluşturulan veya genel bir nesne olabilir.

Nesne oluşturulduğunda, nesne silinmiş olup olmadığını belirtebilirsiniz. Daha fazla bilgi için [CException::CException](#cexception).

Yalnızca çağırmanız gerekir `Delete` C++ kullanıyorsanız **deneyin**- **catch** mekanizması. MFC makroları kullanıyorsanız **deneyin** ve **CATCH**, sonra da bu makrolar otomatik olarak bu işlevi çağırır.

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

##  <a name="reporterror"></a>  CException::ReportError

Kullanıcıya bir ileti kutusunda rapor hata metni için bu üye işlevini çağırın.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Parametreler

*nTür*<br/>
İleti kutusu stilini belirtir. Herhangi bir birleşimini uygulamak [ileti kutusu stilleri](styles-used-by-mfc.md#message-box-styles) kutusu. Bu parametreyi belirtmezseniz MB_OK varsayılandır.

*nMessageID*<br/>
Özel durum nesnesi bir hata mesajı yoksa, görüntülenecek bir ileti (dize girişi) kaynak Kimliğini belirtir. 0 ise iletisi "hata iletisi yok" görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Bir `AfxMessageBox` değeri; ileti kutusu görüntülemek için yeterli bellek yoksa, aksi durumda 0. Bkz: [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) olası dönüş değerleri için.

### <a name="example"></a>Örnek

İşte bir örnek kullanımını `CException::ReportError`. Başka bir örnek için örneğin bakın [CATCH](exception-processing.md#catch).

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

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](cobject-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Özel Durum İşleme](exception-processing.md)<br/>
[Nasıl yapılır: verilerimi kendi özel durum sınıfları oluşturma](http://go.microsoft.com/fwlink/p/?linkid=128045)


