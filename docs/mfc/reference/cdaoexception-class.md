---
title: CDaoException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
dev_langs:
- C++
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4531d63ff7047881f20368cbeaf8e5de4136bb9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoexception-class"></a>CDaoException sınıfı
Veri erişim nesnesi (DAO) tabanlı MFC veritabanı sınıfları nedeniyle ortaya çıkan bir özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|Oluşturan bir `CDaoException` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoException::GetErrorCount](#geterrorcount)|Veritabanı altyapısının hataları koleksiyondaki hatalarının sayısını döndürür.|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|Belirli hata nesnesi hata bilgilerini hataları koleksiyondaki döndürür.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO sınıflarını herhangi bir hata genişletilmiş hata kodunu içerir.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Bir işaretçi bir [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) bir DAO hata nesnesi hakkında bilgi içeren nesne.|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) şu hata ile ilişkili değer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfı, özel durum nedenini belirlemek için kullanabileceğiniz genel veri üyelerini içerir. `CDaoException` nesneleri oluşturulan ve DAO veritabanı sınıfları üye işlevleri tarafından oluşturulur.  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala kullanabilirsiniz. Genel olarak, üzerinde DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıfları daha yetenekli; DAO tabanlı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri üzerinden de dahil olmak üzere, verilere erişebilir. DAO tabanlı sınıflar da tabloları sınıfları aracılığıyla doğrudan çağırmak zorunda kalmadan ekleme gibi veri tanımlama dili (DDL) işlemleri desteklemez. ODBC sınıfları tarafından oluşturulan özel durumları hakkında daha fazla bilgi için bkz: [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Özel durum nesneleri kapsamında erişim bir [CATCH](../../mfc/reference/exception-processing.md#catch) ifade. Ayrıca throw `CDaoException` kendi koduyla nesnelerden [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) genel işlevi.  
  
 MFC içinde tüm DAO hataların türü özel durumlar olarak ifade edilir `CDaoException`. Bu tür bir özel durum catch olduğunda kullanabileceğiniz `CDaoException` veritabanı altyapısının hataları koleksiyonda depolanan tüm DAO hata nesnelerinden bilgi almak için üye işlevleri. Her hata gerçekleştiği sırada bir veya daha fazla hata nesneleri hataları koleksiyonunda yerleştirilir. (Normalde koleksiyon yalnızca bir hata nesnesi içeriyor; ODBC veri kaynağını kullanıyorsanız, birden çok hata nesneleri alma olasılığı daha yüksektir.) Başka bir DAO işlemi bir hata oluşturduğunda, hatalar koleksiyonuna kaldırılır ve yeni hata nesnesi hataları koleksiyonunda yerleştirilir. Bir hata oluşturmaz DAO işlemleri hatalar koleksiyonuna üzerinde etkisi yoktur.  
  
 DAO hata kodları için DAOERR dosyasına bakın. H. İlgili bilgi için "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.  
  
 Özel durum genel veya hakkında işleme hakkında daha fazla bilgi için `CDaoException` nesneleri, makalelere bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İkinci makale DAO özel durum işleme gösterilmektedir örnek kodunu içerir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="cdaoexception"></a>  CDaoException::CDaoException  
 Oluşturan bir `CDaoException` nesnesi.  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde, kendi kod bir özel durum oluşturduğunda framework özel durum nesneleri oluşturur. Nadiren açıkça bir özel durum nesnesi oluşturmak gerekir. Throw istiyorsanız bir `CDaoException` genel işlevi, kendi kodundan çağıran [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Ancak, doğrudan DAO çağrıları MFC sınıfları Kapsüller DAO arabirim işaretçileri üzerinden yapıyorsanız açıkça bir özel durum nesnesi oluşturmak isteyebilirsiniz. Bu durumda, DAO hata bilgilerini almak gerekebilir. Çalışma alanı 's veritabanları koleksiyonuna DAODatabases arabirimi aracılığıyla DAO yöntemini çağırdığınızda DAO'da hata oluşur varsayalım.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>DAO hata bilgilerini almak için  
  
1.  Oluşturmak bir `CDaoException` nesnesi.  
  
2.  Özel durum nesnenin çağrısı [GetErrorCount](#geterrorcount) veritabanı altyapısının hataları koleksiyonda kaç hata nesneleri belirlemek için üye işlevi. (Normalde yalnızca bir ODBC veri kaynağını kullanmadığınız sürece.)  
  
3.  Özel durum nesnenin çağrısı [Geterrorınfo](#geterrorinfo) üye işlevi özel durum nesnesi aracılığıyla koleksiyonda dizin olarak bir kerede bir özel hata nesnesi alınamadı. Özel durum nesnesinin bir DAO hata nesnesi için proxy olarak düşünün.  
  
4.  Geçerli inceleyin [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) , yapı `GetErrorInfo` döndürür [m_pErrorInfo](#m_perrorinfo) veri üyesi. Üyeleri DAO hata hakkında bilgi sağlar.  
  
5.  ODBC veri kaynağını söz konusu olduğunda, adım 3 ve 4, daha fazla hata nesneleri için gerektiği şekilde yineleyin.  
  
6.  Özel durum nesnesi yığında oluşturulan, kendisiyle silin **silmek** tamamladığınızda, işleci.  
  
 MFC DAO sınıflarını hataları işleme hakkında daha fazla bilgi için bkz: [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="geterrorcount"></a>  CDaoException::GetErrorCount  
 DAO veritabanı altyapısının hataları koleksiyonundaki hata nesneleri sayısını almak üzere bu üye işlevini çağırın.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veritabanı altyapısının hatalar koleksiyonu DAO hata nesnelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bilgiler, koleksiyondaki bir veya daha fazla DAO hata nesnelerin her biri almak için hatalar koleksiyonuna döngü için yararlıdır. DAO hata numarası veya dizin tarafından bir hata nesnesi almak için arama [Geterrorınfo](#geterrorinfo) üye işlevi.  
  
> [!NOTE]
>  Normalde hataları koleksiyonunda tek bir hata nesnesi yok. ODBC veri kaynağı ile çalışıyorsanız, ancak olabilir birden fazla.  
  
##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo  
 Belirli hata nesnesi hata bilgilerini hataları koleksiyondaki döndürür.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dizine göre arama için veritabanı altyapısının hatalar koleksiyonuna hata bilgileri dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki türde bir özel durum hakkında bilgi edinmek için bu üye işlevini çağırın:  
  
-   Hata kodu  
  
-   Kaynak  
  
-   Açıklama  
  
-   Yardım dosyası  
  
-   Bağlam Yardımı  
  
 `GetErrorInfo` özel durum nesne bilgileri depolar `m_pErrorInfo` veri üyesi. Döndürülen bilgi kısa bir açıklaması için bkz: [m_pErrorInfo](#m_perrorinfo). Türünde bir özel durum catch `CDaoException` MFC tarafından oluşturulan `m_pErrorInfo` üye önceden doldurulur. Doğrudan çağırmak seçerseniz, özel durum nesnenin çağırmalısınız `GetErrorInfo` üye işlevi kendiniz doldurmak için `m_pErrorInfo`. Daha ayrıntılı bir açıklaması için bkz: [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısı.  
  
 DAO özel durumlar ve örnek kod hakkında daha fazla bilgi için bkz: [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError  
 Genişletilmiş hata kodu bir MFC içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu kod, MFC DAO sınıflarını, belirli bir bileşen erred olduğu durumlarda sağlanır.  
  
 Olası değerler şunlardır:  
  
- **NO_AFX_DAO_ERROR** en son işlemi genişletilmiş hata bir MFC neden değil. Denetlemeniz gerekir böylece ancak işlemi DAO veya OLE, diğer hataları ürettiğini [m_pErrorInfo](#m_perrorinfo) ve muhtemelen [m_scode](#m_scode).  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC Microsoft Jet veritabanı altyapısı başlatılamadı. OLE başlatma başarısız olabilir veya DAO veritabanı motoru nesne örneğini oluşturmak mümkün olabilir. Bu sorunları genellikle DAO veya OLE hatalı bir yüklemesini öneririz.  
  
- **AFX_DAO_ERROR_DFX_BIND** bir DAO kayıt alanı değişimi (DFX) işlev çağrısında kullanılan bir adresi yok veya geçersiz (adres veri bağlamak için kullanılan değil). DFX çağrısında hatalı adres geçirilen veya adres DFX işlemler arasında geçersiz duruma gelmiş.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** bir querydef açık durumda değildi tabledef nesnesi göre bir kayıt kümesi açılmaya çalışıldı.  
  
##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo  
 Bir işaretçi içeren bir `CDaoErrorInfo` çağırarak en son alınan DAO hata nesnesi hakkında bilgi verilmektedir yapısı [Geterrorınfo](#geterrorinfo).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nesne, aşağıdaki bilgileri içerir:  
  
|Cdaoerrorınfo üyesi|Bilgiler|Açıklama|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|Hata Kodu|DAO hata kodu|  
|`m_strSource`|Kaynak|Nesne veya başlangıçta hatayı oluşturan uygulama adı|  
|`m_strDescription`|Açıklama|Şu hata ile ilişkili açıklayıcı bir dize|  
|`m_strHelpFile`|Yardım dosyası|Bir kullanıcı sorun hakkında bilgi almak Windows Yardım dosyasının yolu|  
|**m_lHelpContext**|Bağlam Yardımı|DAO Yardım dosyasındaki bir konu için içerik kimliği|  
  
 İçinde yer alan bilgiler hakkında ayrıntılar için `CDaoErrorInfo` nesne için bkz: [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısı.  
  
##  <a name="m_scode"></a>  CDaoException::m_scode  
 Türünde bir değer içeren `SCODE` hata açıklar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir OLE koddur. Nadiren neredeyse her durumda, daha özel MFC veya DAO hata bilgileri diğer kullanılabilir olduğundan, bu değer kullanmanız gerekecektir `CDaoException` veri üyeleri.  
  
 Hakkında bilgi için `SCODE`, konusuna [yapısı, OLE hata kodları](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki. `SCODE` Veri türü eşlemeleri için `HRESULT` veri türü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CException Sınıfı](../../mfc/reference/cexception-class.md)
