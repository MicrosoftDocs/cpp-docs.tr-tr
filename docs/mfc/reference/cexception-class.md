---
title: "CException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72272630dc475f2c40b8f249e969822a872015e0
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
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
|[CException::CException](#cexception)|Oluşturan bir `CException` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CException::Delete](#delete)|Siler bir `CException` nesnesi.|  
|[CException::ReportError](#reporterror)|Hata iletisinde bir ileti kutusu kullanıcıya bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çünkü `CException` , oluşturamıyor bir Özet temel sınıf `CException` nesneleri doğrudan; türetilen sınıfların nesnelerini oluşturmanız gerekir. Kendi oluşturmanız gerekiyorsa `CException`-stil sınıf, model olarak yukarıda listelenen türetilmiş sınıflarından birini kullanın. Türetilmiş sınıf ayrıca kullandığından emin olun `IMPLEMENT_DYNAMIC`.  
  
 Türetilen sınıflar ve onların açıklamaları aşağıda listelenmiştir:  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Kaynak kritik MFC özel durumlar için temel sınıf|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken özel durumu|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|İstek desteklenmeyen bir işlem için|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Arşiv özel durum|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Dosya özgü özel durumu|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows kaynak bulunamadı veya yok creatable|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE özel durumu|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Veritabanı özel durumu (açık veritabanı bağlantısı üzerinde tabanlı MFC veritabanı sınıfları için doğan diğer bir deyişle, özel durumları)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE gönderme (Otomasyonu) özel durumu|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Bir kaynak bulunamadı gösteren özel durumu|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Veri erişim nesnesi özel durumu (DAO sınıfları için doğan diğer bir deyişle, özel durumları)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Internet özel durumu (Internet sınıfları için doğan diğer bir deyişle, özel durumları).|  
  
 Bu özel durumları ile kullanılmak üzere tasarlanmıştır [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [deneyin](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), ve [end_catch](exception-processing.md#end_catch) makroları. Özel durumlar hakkında daha fazla bilgi için bkz: [özel durum işleme](exception-processing.md), veya makalesine bakın [özel durum işleme (MFC)](../exception-handling-in-mfc.md).  
  
 Belirli bir özel durum yakalamak için uygun türetilen sınıfı kullanın. Özel durumları yakalama tüm türleri için kullanmak `CException`ve ardından [CObject::IsKindOf](cobject-class.md#iskindof) arasında ayırt etmek için `CException`-türetilmiş sınıfları. Unutmayın `CObject::IsKindOf` yalnızca sınıfları çalışır bildirilen ile [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic) dinamik tür denetlemesi avantajlarından yararlanmak için makrosu. Tüm `CException`-oluşturduğunuz türetilmiş bir sınıf kullanması gereken `IMPLEMENT_DYNAMIC` makro çok.  
  
 Çağırarak kullanıcıya özel durumlar hakkında ayrıntılar raporlayabilirsiniz [GetErrorMessage](cfileexception-class.md#geterrormessage) veya [ReportError](#reporterror), iki üye işlevlerini herhangi biri ile çalışan `CException`türetilmiş sınıfları.  
  
 Bir özel durum makroları biri tarafından yakalanmışsa `CException` nesne otomatik olarak silinir; kendiniz silmeyin. Kullanarak bir özel durum yakalandı varsa bir **catch** anahtar sözcüğü, otomatik olarak silinmez. Makalesine bakın [özel durum işleme (MFC)](../exception-handling-in-mfc.md) ne zaman bir exeption nesnesini silme hakkında daha fazla bilgi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](cobject-class.md)  
  
 `CException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cexception">CException::CException</a>  
 Bu üye işlevi oluşturan bir `CException` nesnesi.  
  
```  
explicit CException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 *b_AutoDelete*  
 Belirtin **TRUE** varsa için bellek `CException` nesne öbek üzerinde ayrıldı. Bu neden olacak `CException` zaman Silinecek nesnenin **silmek** üye işlevi, özel durum silmek için çağrılır. Belirtin **FALSE** varsa `CException` nesne yığında veya genel bir nesnedir. Bu durumda, `CException` nesne olmayacak ne zaman silinmiş **silmek** üye işlevi çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde hiçbir zaman bu oluşturucu doğrudan çağırmanız gerekir. Bir özel durum oluşturur işlevi bir örneğini oluşturmanız gerekir bir `CException`-türetilmiş sınıf ve MFC'nin kullanım throw işlevleri gibi kurucusu veya çağrı [AfxThrowFileException](exception-processing.md#afxthrowfileexception), önceden tanımlanmış bir türü atmak için. Bu belge, yalnızca bütünlük açısından sağlanır.  
  
##  <a name="delete">CException::Delete</a>  
 Bu işlev olup olmadığını denetler. **CException** nesne öbek üzerinde oluşturuldu ve bu durumda, çağırır **silmek** nesne üzerinde işleci.  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Silerken bir **CException** nesne, kullanın **silmek** özel silmek için üye işlevi. Kullanmayın **silmek** doğrudan işleci çünkü `CException` nesne yığında oluşturulan veya genel bir nesne olabilir.  
  
 Nesne nesnesi oluşturulduğunda silineceğini belirtebilirsiniz. Daha fazla bilgi için bkz: [CException::CException](#cexception).  
  
 Yalnızca çağırmanız gerekir **silmek** C++ kullanıyorsanız **deneyin**- **catch** mekanizması. MFC makroları kullanıyorsanız **deneyin** ve **CATCH**, sonra da bu makroları otomatik olarak bu işlevi çağırır.  
  
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
  
##  <a name="reporterror">CException::ReportError</a>  
 Kullanıcıya bir ileti kutusunda rapor hata metni için bu üye işlevini çağırın.  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nType`  
 İleti kutusu stilini belirtir. Herhangi bir bileşimini uygulamak [ileti kutusu stilleri](styles-used-by-mfc.md#message-box-styles) kutusuna. Bu parametre belirtmezseniz, varsayılan değer **MB_OK**.  
  
 *nMessageID*  
 Özel durum nesnesi bir hata mesajı yoksa, görüntülenecek bir ileti kaynak kimliği (dizesi tablo girişi) belirtir. 0 ise iletisi "hata iletisi yok" görüntülenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `AfxMessageBox` değeri; Aksi takdirde 0 ileti kutusu görüntülemek için yeterli bellek varsa. Bkz: [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) olası dönüş değerleri.  
  
### <a name="example"></a>Örnek  
 Kullanım örneği `CException::ReportError`. Örneğin başka bir örnek için bkz [CATCH](exception-processing.md#catch).  
  
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
 [CObject sınıfı](cobject-class.md)   
 [Hiyerarşi grafiği](../hierarchy-chart.md)   
 [Özel durum işleme](exception-processing.md)   
 [I: kendi özel durum sınıfları nasıl oluşturulur](http://go.microsoft.com/fwlink/p/?linkid=128045)


