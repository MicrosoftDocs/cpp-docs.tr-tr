---
title: "Özel durum işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.exceptions
dev_langs: C++
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
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adad6183d15b378feb7ec96aedff6a0013a2dd24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-processing"></a>Özel Durum İşleme
Bir program yürütüldüğünde, bir dizi anormal koşullar ve "özel durumlar" adlı hataları oluşabilir. Bunlar, bellek, kaynak ayırma hatalarını ve dosyaları bulmak için hata tükenmesinden olabilir.  
  
 Microsoft Foundation Class Kitaplığı C++ için ANSI standartları komitesi tarafından önerilen sonra yakından Modellenen bir özel durum işleme düzenini kullanır. Bir işlevi çağıran bir anormal durumlar yaşayabilirsiniz önce bir özel durum işleyici ayarlanması gerekir. İşlev olağan dışı bir koşul karşılaşırsa bir özel durum oluşturur ve denetimi özel durum işleyicisine geçirilir.  
  
 Microsoft Foundation Class Kitaplığı ile dahil birkaç makroları özel durum işleyicilerini ayarlar. Gerekirse, özelleştirilmiş özel durumlar oluşturma ve programları sonlandırmak için diğer genel işlevleri yardımcı. Bu makrolar ve genel işlevler aşağıdaki kategorilere ayrılır:  
  
- Özel durum işleyici yapısı özel durum makroları.  
  
- İşlevler Exception-throwing), belirli türleri özel durumları oluşturur.  
  
- Program sonlandırma neden sonlandırma işlevleri.  
  
 Örnekler ve daha fazla ayrıntı için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Özel durum makroları  
  
|||  
|-|-|  
|[DENEYİN](#try)|Özel durum işleme için kod bloğunu belirler.|  
|[YAKALAMA](#catch)|Önceki bir özel durum yakalama için kod bloğunu atar **deneyin** bloğu.|  
|[CATCH_ALL](#catch_all)|Önceki tüm özel durumları yakalama için kod bloğunu atar **deneyin** bloğu.|  
|[AND_CATCH](#and_catch)|Önceki ek özel durum türleri yakalama için kod bloğunu atar **deneyin** bloğu.|  
|[AND_CATCH_ALL](#and_catch_all)|Bir önceki oluşturulan diğer tüm ek özel durum türleri yakalama için kod bloğunu atar **deneyin** bloğu.|  
|[END_CATCH](#end_catch)|Son sona **CATCH** veya `AND_CATCH` kod bloğu.|  
|[END_CATCH_ALL](#end_catch_all)|Son sona `CATCH_ALL` kod bloğu.|  
|[THROW](#throw)|Belirtilen özel durum oluşturur.|  
|[THROW_LAST](#throw_last)|Sonraki dış işleyici şu anda işlenmiş özel durumu oluşturur.|  
  
### <a name="exception-throwing-functions"></a>Özel durum atma işlevleri  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Arşiv özel durum oluşturur.|  
|[AfxThrowFileException](#afxthrowfileexception)|Bir dosya özel durum oluşturur.|  
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Geçersiz bağımsız değişken özel durum oluşturur.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Bellek özel durum oluşturur.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Not desteklenen bir özel durum oluşturur.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Bir Windows Kaynak not found özel durum oluşturur.|  
|[AfxThrowUserException](#afxthrowuserexception)|Bir kullanıcı tarafından başlatılan program eylemde bir özel durum oluşturur.|  
  
 MFC özellikle OLE özel durumları için iki özel durum atma işlevleri sağlar:  
  
### <a name="ole-exception-functions"></a>OLE özel durum işlevleri  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE Otomasyon işlevinin içindeki bir özel durum oluşturur.|  
|[AfxThrowOleException](#afxthrowoleexception)|OLE özel durum oluşturur.|  
  
 Veritabanı özel durumları desteklemek için iki özel durum sınıfları, veritabanı sınıfları sağlar `CDBException` ve `CDaoException`ve özel durum türlerini desteklemek için genel işlevler:  
  
### <a name="dao-exception-functions"></a>DAO özel durum işlevleri  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Atan bir [CDaoException](../../mfc/reference/cdaoexception-class.md) kendi kodundan.|  
|[AfxThrowDBException](#afxthrowdbexception)|Atan bir [CDBException](../../mfc/reference/cdbexception-class.md) kendi kodundan.|  
  
 MFC aşağıdaki sonlandırma işlevi sağlar:  
  
### <a name="termination-functions"></a>Sonlandırma işlevleri  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Adlı bir uygulamayı önemli bir hata olduğunda meydana gelir.|  
  
##  <a name="try"></a>DENEYİN  
 Ayarlayan bir **deneyin** bloğu.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Açıklamalar  
 A **deneyin** blok özel durumlar oluşturma kod bloğunu tanımlar. Aşağıda, bu özel durumlar işlenir **CATCH** ve `AND_CATCH` engeller. Özyineleme izin verilir: özel durumlar bayraklarıdır bir dış **deneyin** bloğu, bunları yoksayılıyor veya kullanarak `THROW_LAST` makrosu. Son **deneyin** ile engelleme bir `END_CATCH` veya `END_CATCH_ALL` makrosu.  
  
 Daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CATCH](#catch).  

### <a name="requirements"></a>Gereksinimler
Başlık: afx.h

##  <a name="catch"></a>YAKALAMA  
 Önceki durum ilk özel durum türü yakalar kod bloğunu tanımlar **deneyin** bloğu.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Parametreler  
 *exception_class*  
 Sınamak için özel durum türünü belirtir. Standart özel durum sınıfları listesi için bkz [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad belirtir. İşaretçi adı özel durum nesnesi içinde erişmek için kullanabileceğiniz **CATCH** bloğu. Bu değişken, bildirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel durum işleme kodunda uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi, özel durum nesnesi sorgulayın. Çağırma `THROW_LAST` sonraki dış özel durum çerçeve işleme kaydırılacak makrosu. Son **deneyin** ile engelleme bir `END_CATCH` makrosu.  
  
 Varsa *exception_class* sınıfı `CException`, tüm özel durum türleri yakalanan sonra. Kullanabileceğiniz [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) hangi özel durum oluştu belirlemek için üye işlevi. Çeşitli türlerde özel durumları yakalamak için iyi bir yolu sıralı kullanmaktır `AND_CATCH` deyimleri, her biri farklı bir özel durum türü.  
  
 Özel durum nesne işaretçisi makro tarafından oluşturulur. Kendiniz bildirmeniz gerekmez.  
  
> [!NOTE]
>  **CATCH** blok kaşlı ayraç işaretleriyle C++ kapsam olarak tanımlanır. Bu kapsamdaki Değişkenler bildirirseniz, yalnızca bu kapsamda erişilebilir. Bu durum için de geçerlidir *exception_object_pointer_name*.  
  
 Özel durumlar hakkında daha fazla bilgi ve **CATCH** makrosu, makaleye bakın [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="catch_all"></a>CATCH_ALL  
 Önceki oluşturulan tüm özel durum türlerini yakalaması kod bloğunu tanımlar **deneyin** bloğu.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *exception_object_pointer_name*  
 Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad belirtir. İşaretçi adı özel durum nesnesi içinde erişmek için kullanabileceğiniz `CATCH_ALL` bloğu. Bu değişken, bildirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel durum işleme kodunda uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi, özel durum nesnesi sorgulayın. Çağırma `THROW_LAST` sonraki dış özel durum çerçeve işleme kaydırılacak makrosu. Kullanırsanız `CATCH_ALL`, son **deneyin** ile engelleme bir `END_CATCH_ALL` makrosu.  
  
> [!NOTE]
>  `CATCH_ALL` Blok kaşlı ayraç işaretleriyle C++ kapsam olarak tanımlanır. Bu kapsamdaki Değişkenler bildirirseniz, yalnızca bu kapsamda erişilebilir.  
  
 Özel durumlar hakkında daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  

##  <a name="and_catch"></a>AND_CATCH  
 Bir önceki oluşturulan ek özel durum türleri yakalama için kod bloğunu tanımlar **deneyin** bloğu.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *exception_class*  
 Sınamak için özel durum türünü belirtir. Standart özel durum sınıfları listesi için bkz [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad. İşaretçi adı özel durum nesnesi içinde erişmek için kullanabileceğiniz `AND_CATCH` bloğu. Bu değişken, bildirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım **CATCH** bir özel durum türü, catch makrosu sonra `AND_CATCH` makrosu catch sonraki her türü. Son **deneyin** ile engelleme bir `END_CATCH` makrosu.  
  
 Özel durum işleme kodunda uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi, özel durum nesnesi sorgulayın. Çağrı `THROW_LAST` makrosu içinde `AND_CATCH` engellemek için sonraki dış özel durum çerçeve işleme shift. `AND_CATCH`Yukarıdaki sonunu işaretler **CATCH** veya `AND_CATCH` bloğu.  
  
> [!NOTE]
>  `AND_CATCH` Blok (küme ayraçları işaretleriyle) C++ kapsam olarak tanımlanır. Bu kapsamdaki Değişkenler bildirirseniz, yalnızca bu kapsamda erişilebilir unutmayın. Bu durum için de geçerlidir *exception_object_pointer_name* değişkeni.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CATCH](#catch).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
##  <a name="and_catch_all"></a>AND_CATCH_ALL  
 Bir önceki oluşturulan ek özel durum türleri yakalama için kod bloğunu tanımlar **deneyin** bloğu.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Parametreler  
 *exception_object_pointer_name*  
 Makro tarafından oluşturulan bir özel durum nesnesi işaretçisi için bir ad. İşaretçi adı özel durum nesnesi içinde erişmek için kullanabileceğiniz `AND_CATCH_ALL` bloğu. Bu değişken, bildirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım **CATCH** bir özel durum türü, catch makrosu sonra `AND_CATCH_ALL` diğer tüm sonraki türleri catch makrosu. Kullanırsanız `AND_CATCH_ALL`, son **deneyin** ile engelleme bir `END_CATCH_ALL` makrosu.  
  
 Özel durum işleme kodunda uygunsa, özel durumun belirli nedeni hakkında daha fazla bilgi, özel durum nesnesi sorgulayın. Çağrı `THROW_LAST` makrosu içinde `AND_CATCH_ALL` engellemek için sonraki dış özel durum çerçeve işleme shift. `AND_CATCH_ALL`Yukarıdaki sonunu işaretler **CATCH** veya `AND_CATCH_ALL` bloğu.  
  
> [!NOTE]
>  `AND_CATCH_ALL` Blok (kaşlı ayraç işaretleriyle) C++ kapsam olarak tanımlanır. Bu kapsamdaki Değişkenler bildirirseniz, yalnızca bu kapsamda erişilebilir unutmayın.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="end_catch"></a>END_CATCH  
 Son sonunu işaretler **CATCH** veya `AND_CATCH` bloğu.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için `END_CATCH` makrosu, makaleye bakın [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="end_catch_all"></a>END_CATCH_ALL  
 Son sonunu işaretler `CATCH_ALL` veya `AND_CATCH_ALL` bloğu.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="throw"></a>THROW (MFC)  
 Belirtilen özel durum oluşturur.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Parametreler  
 *exception_object_pointer*  
 Bir özel durum nesnesi noktalarına türetilen `CException`.  
  
### <a name="remarks"></a>Açıklamalar  
 **THROW** kesmeler program yürütme, Denetim ilişkili geçirme **CATCH** programınıza engelleyin. Sağlanmadığında **CATCH** denetim baskı siparişi bir hata iletisi ve çıkar bir Microsoft Foundation Class Kitaplığı modülü için geçirilen sonra engelleyin.  
  
 Daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="throw_last"></a>THROW_LAST  
 Özel durum geri sonraki oluşturur dış **CATCH** bloğu.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu, yerel olarak oluşturulan bir özel durum olanak sağlar. Yakalanan bir özel durum çalışırsanız, kapsam dışındadır normalde geçilir ve silinmiş. İle `THROW_LAST`, özel durum doğru sonraki geçirilen **CATCH** işleyicisi.  
  
 Daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 Arşiv özel durum oluşturur.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Parametreler  
 `cause`  
 Özel durumun nedeni belirten bir tamsayı belirtir. Olası değerler listesi için bkz: [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 İşaret adını içeren bir dize `CArchive` (varsa) özel duruma neden nesnesi.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowfileexception"></a>AfxThrowFileException  
 Bir dosya özel durum oluşturur.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Parametreler  
 `cause`  
 Özel durumun nedeni belirten bir tamsayı belirtir. Olası değerler listesi için bkz: [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 İşletim sistemi hata sayısı (varsa) içeren özel durumun nedeni bildiren. Hata kodları listesi için işletim sistemi kılavuzuna bakın.  
  
 `lpszFileName`  
 Özel durum (varsa) neden olan dosya adını içeren bir dize noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 İşletim sistemi hata koduna göre nedenini belirlemek için sorumlu.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  

## <a name="afxthrowinvalidargexception"></a>AfxThrowInvalidArgException
Geçersiz bağımsız değişken özel durum oluşturur.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AfxThrowInvalidArgException( );  
```  
   
### <a name="remarks"></a>Açıklamalar  
 Geçersiz bağımsız değişkenler kullanıldığında bu işlev çağrılır.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [CInvalidArgException sınıfı](cinvalidargexception-class.md)   
 [THROW](#throw)
  
  
##  <a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 Bellek özel durum oluşturur.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi çağırır temel sistem bellek allocators çağrıları (gibi `malloc` ve [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows işlevi) başarısız. Bunun için çağrı gerekmez **yeni** çünkü **yeni** bellek ayırma başarısız olursa bir bellek özel durumu otomatik olarak atar.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 Desteklenmeyen bir özellik için bir istek sonucu bir özel durum oluşturur.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 Bir kaynak özel durum oluşturur.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Kaynak yüklendiğinde bu işlev normal olarak adlandırılır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowuserexception"></a>AfxThrowUserException  
 Bir son kullanıcı işlemi durdurmak için bir özel durum oluşturur.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev normalde hemen sonra çağrılır `AfxMessageBox` kullanıcıya bir hata bildirdi.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 OLE Otomasyon işlevinin içindeki bir özel durum için bu işlevi kullanın.  
  
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
 `wCode`  
 Uygulamanız için belirli bir hata kodu.  
  
 `lpszDescription`  
 Hata sözlü açıklaması.  
  
 `nDescriptionID`  
 Sözlü hata açıklaması için kaynak kimliği.  
  
 `nHelpID`  
 Uygulamanızın Yardım için Yardım bağlamı (. HLP) dosyası.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev için sağlanan bilgileri yönlendirmeli uygulama (Microsoft Visual Basic veya başka bir OLE Otomasyon istemci uygulaması) tarafından görüntülenebilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxthrowoleexception"></a>AfxThrowOleException  
 Türünde bir nesne oluşturur `COleException` ve bir özel durum oluşturur.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Parametreler  
 `sc`  
 Özel durumun nedeni gösteren bir OLE durum kodu.  
  
 `hr`  
 Özel durumun nedeni belirten bir sonuç kodu için işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Alan sürüm bir `HRESULT` karşılık gelen sonuç kodu bir bağımsız değişken dönüştürür gibi `SCODE`. Daha fazla bilgi için `HRESULT` ve `SCODE`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 Bu işlev türünde bir özel durum çağrı [CDaoException](../../mfc/reference/cdaoexception-class.md) kendi kodundan.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>Parametreler  
 `nAfxDaoError`  
 Genişletilmiş hata kodu DAO temsil eden bir tamsayı değeri olan değerlerden biri altında listelenebilir [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).  
  
 *SCODE*  
 OLE hata kodu türünde DAO `SCODE`. Bilgi için bkz: [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).  
  
### <a name="remarks"></a>Açıklamalar  
 Framework de çağırır `AfxThrowDaoException`. Aramanız parametrelerden biri veya her ikisi de geçirebilirsiniz. Aşağıdakilerden birini yükseltmek istiyorsanız, örneğin, hataları tanımlanan **CDaoException::nAfxDaoError** ancak önem verdiğiniz değil *scode* parametresi geçerli bir kod geçirmek `nAfxDaoError` parametresi ve kabul edin Varsayılan değeri *scode*.  
  
 MFC DAO sınıflarına ilgili özel durumlar hakkında daha fazla bilgi için bkz `CDaoException` bu kitap ve makale [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdb.h  
  
##  <a name="afxthrowdbexception"></a>AfxThrowDBException  
 Bu işlev türünde bir özel durum çağrı `CDBException` kendi kodundan.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nRetCode`  
 Türünde bir değer **RETCODE**, özel durum oluşturulmasına neden olan hata türünü tanımlayan.  
  
 `pdb`  
 Bir işaretçi `CDatabase` özel olduğu ilişkili veri kaynağı bağlantısını temsil eden nesne.  
  
 `hstmt`  
 Bir ODBC **HSTMT** özel olduğu ilişkili deyim tanıtıcısı belirtir tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework çağrıları `AfxThrowDBException` aldığı ne zaman bir ODBC **RETCODE** bir ODBC API çağrısından işlev ve Yorumlar **RETCODE** expectable hata yerine olağanüstü bir koşulu olarak. Örneğin, bir veri erişim işlemi bir disk okuma hatası nedeniyle başarısız olabilir.  
  
 Hakkında bilgi için **RETCODE** ODBC tarafından tanımlanan değerleri Windows SDK'ın bölüm 8, "Alma durumu ve hata bilgileri için" konusuna bakın. MFC uzantıları için bu kodları hakkında daha fazla bilgi için bkz [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h  
  
##  <a name="afxabort"></a>AfxAbort  
 MFC tarafından sağlanan varsayılan sonlandırma işlev.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AfxAbort`işlenemez yakalanmayan bir özel durum gibi önemli bir hata olduğunda MFC üye işlevleri tarafından dahili olarak adlandırılır. Çağırabilirsiniz `AfxAbort` , olamaz kurtarma işlemi yıkıcı hatayla karşılaştığında nadir durumda.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CATCH](#catch).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afx.h   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException Sınıfı](../../mfc/reference/cexception-class.md)
