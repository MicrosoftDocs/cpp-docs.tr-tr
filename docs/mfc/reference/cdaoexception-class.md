---
title: CDaoException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
ms.openlocfilehash: 8d49291c51f66ee837f9b31a2ade390cec48c51a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289006"
---
# <a name="cdaoexception-class"></a>CDaoException sınıfı

Veri erişim nesnelerine (DAO) göre MFC veritabanı sınıflarından kaynaklanan bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException::CDaoException](#cdaoexception)|Oluşturur bir `CDaoException` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|Veritabanı altyapısının hataları koleksiyondaki hatalarının sayısını döndürür.|
|[CDaoException::GetErrorInfo](#geterrorinfo)|Hataları koleksiyonda hata bilgilerini belirli hata nesnesi döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO sınıflarına herhangi bir hata için bir genişletilmiş hata kodunu içerir.|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Bir işaretçi bir [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) bir DAO hata nesnesi hakkında bilgi içeren nesne.|
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) hatayla ilişkili değer.|

## <a name="remarks"></a>Açıklamalar

Sınıfı özel durumun nedenini belirlemek için kullanabileceğiniz ortak veri üyeleri içerir. `CDaoException` nesneleri oluşturulur ve DAO veritabanı sınıfları üye işlevleri tarafından oluşturulur.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile ODBC veri kaynaklarına erişim yine de kullanabilirsiniz. Genel olarak, üzerinde DAO göre MFC sınıflarını ODBC tabanlı MFC sınıfları daha yetenekli; DAO dayalı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri dahil olmak üzere, verilere erişebilir. DAO dayalı sınıflar da DAO doğrudan çağırmak zorunda kalmadan tablo sınıfları aracılığıyla ekleme gibi veri tanımlama dili (DDL) işlemleri destekler. ODBC sınıfları tarafından oluşturulan özel durumları hakkında daha fazla bilgi için bkz: [CDBException](../../mfc/reference/cdbexception-class.md).

Özel durum nesneleri kapsamında erişebileceğiniz bir [CATCH](../../mfc/reference/exception-processing.md#catch) ifade. Ayrıca oluşturabilecek `CDaoException` kendi kodunuzla nesnelerden [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) genel işlev.

MFC içinde DAO ile ilgili tüm hataların tür özel durumlar olarak ifade edilir `CDaoException`. Bu tür bir özel durum yakalamak, kullanabileceğiniz `CDaoException` üye işlevleri, veritabanı altyapısının hataları bir koleksiyonda depolanan tüm DAO hata nesnelerden bilgileri alınamıyor. Her hata gerçekleştiği sırada hataları koleksiyonda bir veya daha fazla hata nesneleri yerleştirilir. (Normalde yalnızca bir hata nesnesi koleksiyonu içerir; ODBC veri kaynağı kullanıyorsanız büyük olasılıkla birden çok hata nesnesi Al.) DAO başka bir işlem bir hata oluşturduğunda, hatalar koleksiyonuna temizlenir ve yeni bir hata nesnesi içinde hatalar koleksiyonuna yerleştirilir. Bir hata oluşturmaz DAO operations hatalar koleksiyonuna üzerinde etkisi yoktur.

DAO hata kodları için ' % s'dosyasına DAOERR bakın. H İlgili bilgiler için "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.

Özel durum genel veya hakkında işleme hakkında daha fazla bilgi için `CDaoException` nesneleri makalelere bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: Veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İkinci makale DAO özel durum işlemesini gösteren kod örneği içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="cdaoexception"></a>  CDaoException::CDaoException

Oluşturur bir `CDaoException` nesne.

```
CDaoException();
```

### <a name="remarks"></a>Açıklamalar

Normalde, kendi kod bir özel durum oluşturduğunda framework özel durum nesneleri oluşturur. Nadiren açıkça bir özel durum nesnesi oluşturmak gerekir. Throw istiyorsanız bir `CDaoException` kendi koddan genel işlev çağrısı [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).

Ancak, MFC sınıfları kapsülleyen DAO arabirim işaretçilerini aracılığıyla DAO doğrudan çağrıları yapıyorsanız açıkça bir özel durum nesnesi oluşturmak isteyebilirsiniz. Bu durumda, DAO hata bilgilerini alması gerekebilir. Bir çalışma alanının veritabanları koleksiyonuna DAODatabases arabirimi üzerinden DAO yöntemini çağırdığınızda DAO'da bir hata meydana varsayalım.

##### <a name="to-retrieve-the-dao-error-information"></a>DAO hata bilgilerini almak için

1. Oluşturmak bir `CDaoException` nesne.

1. Özel durum nesnenin [GetErrorCount](#geterrorcount) veritabanı altyapısının hataları koleksiyonda kaç hata nesneleri belirlemek için üye işlevi. (Normalde tek tek bir ODBC veri kaynağı kullandığınız sürece.)

1. Özel durum nesnenin [Geterrorınfo](#geterrorinfo) koleksiyondaki özel durum nesnesi aracılığıyla bir dizine göre bir kerede bir özel hata nesnesini almak için üye işlevi. Özel durum nesnesi bir DAO hata nesnesi için proxy olarak düşünün.

1. Geçerli inceleyin [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) , yapı `GetErrorInfo` döndürür [m_pErrorInfo](#m_perrorinfo) veri üyesi. Üyeleri DAO hata bilgileri sağlayın.

1. ODBC veri kaynağında söz konusu olduğunda, 3 ve gerektiğinde daha fazla hata nesneler için 4. adımları tekrarlayın.

1. Yığın üzerinde özel durum nesnesi oluşturulur, kendisiyle silin **Sil** bitirdiğinizde işleci.

MFC DAO sınıflarına hataları işleme hakkında daha fazla bilgi için bkz [özel durumlar: Veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

##  <a name="geterrorcount"></a>  CDaoException::GetErrorCount

DAO veritabanı altyapısının hataları koleksiyondaki hata nesne sayısını almak için bu üye işlevini çağırın.

```
short GetErrorCount();
```

### <a name="return-value"></a>Dönüş Değeri

DAO veritabanı altyapısının hataları koleksiyonundaki hata nesneleri sayısı.

### <a name="remarks"></a>Açıklamalar

Bu bilgiler, koleksiyondaki bir veya daha fazla DAO hata nesnelerin her biri almak için hatalar koleksiyonuna döngü için yararlıdır. DAO hata numarasını veya dizin tarafından bir hata nesnesi almak için arama [Geterrorınfo](#geterrorinfo) üye işlevi.

> [!NOTE]
>  Normalde hataları koleksiyonunda tek bir hata nesnesi yok. ODBC veri kaynağı ile çalışıyorsanız, ancak olabilir birden fazla.

##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo

Hataları koleksiyonda hata bilgilerini belirli hata nesnesi döndürür.

```
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Veritabanı altyapısının dizine göre arama için hatalar koleksiyonuna hata bilgileri dizini.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki türde özel durum hakkında bilgi edinmek için bu üye işlevini çağırın:

- Hata kodu

- Kaynak

- Açıklama

- Yardım dosyası

- Yardım içeriği

`GetErrorInfo` özel durum nesnesine ait bilgileri depolar `m_pErrorInfo` veri üyesi. Döndürülen bilgileri kısa bir açıklaması için bkz. [m_pErrorInfo](#m_perrorinfo). Türünde bir özel durum yakalarsanız `CDaoException` MFC tarafından oluşturulan `m_pErrorInfo` üye önceden doldurulur. DAO doğrudan çağırmak tercih ederseniz özel durum nesnenin çağırmalıdır `GetErrorInfo` üye işlevi doldurmak için kendiniz `m_pErrorInfo`. Daha ayrıntılı bir açıklama için bkz. [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısı.

DAO özel durumlar ve örnek kod hakkında daha fazla bilgi için bkz [özel durumlar: Veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError

Hata kodu genişletilmiş bir MFC içerir.

### <a name="remarks"></a>Açıklamalar

Bu kodu, MFC DAO sınıflarını, belirli bir bileşen burada erred durumlarda sağlanır.

Olası değerler şunlardır:

- Genişletilmiş hata NO_AFX_DAO_ERROR en son işlem bir MFC neden değil. Denetlemeniz gereken şekilde ancak işlemi DAO ya da OLE, diğer hataları oluşturmuş [m_pErrorInfo](#m_perrorinfo) ve büyük olasılıkla [m_scode](#m_scode).

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC Microsoft Jet veritabanı altyapısı başlatılamadı. OLE başlatma başarısız olabilir veya DAO veritabanı motoru nesne örneğini oluşturmak mümkün olabilir. Bu sorunlar genellikle DAO ya da OLE hatalı bir yüklemesini öneririz.

- DAO kayıt alanı değişimi (DFX) işlev çağrısında kullanılan bir adresi yok veya geçersiz AFX_DAO_ERROR_DFX_BIND (adres veri bağlamak için kullanılan değil). DFX çağrısında hatalı bir adres geçirilen veya adres DFX işlemleri arasında geçersiz olmayabilir.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN, bir querydef veya açık bir durumda değildi tabledef nesnesi göre bir kayıt kümesi açılmaya çalışıldı.

##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo

Bir işaretçi içeren bir `CDaoErrorInfo` çağırarak aldığınız son DAO hata nesnesi hakkında bilgi verilmektedir yapısı [Geterrorınfo](#geterrorinfo).

### <a name="remarks"></a>Açıklamalar

Bu nesne, aşağıdaki bilgileri içerir:

|Cdaoerrorınfo üyesi|Bilgiler|Açıklama|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|Hata Kodu|DAO hata kodu|
|`m_strSource`|Kaynak|Nesne veya ilk olarak hatayı oluşturan uygulama adı|
|`m_strDescription`|Açıklama|Hatayla ilişkili açıklayıcı bir dize|
|`m_strHelpFile`|Yardım dosyası|Bir kullanıcıyı sorun hakkında bilgi alabilirsiniz Windows Yardım dosyasının yolu|
|`m_lHelpContext`|Yardım içeriği|DAO Yardım dosyasındaki bir konuyu içerik kimliği|

İçindeki bilgiler hakkında tam Ayrıntılar için `CDaoErrorInfo` nesne, bkz: [Cdaoerrorınfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısı.

##  <a name="m_scode"></a>  CDaoException::m_scode

Türünde bir değer içeren `SCODE` hatayı açıklayan.

### <a name="remarks"></a>Açıklamalar

Bu bir OLE koddur. Nadiren hemen hemen tüm durumlarda daha belirli MFC DAO ya da hata bilgilerini diğer kullanılabilir olduğundan, bu değer kullanmanız gerekir `CDaoException` veri üyeleri.

SCODE hakkında daha fazla bilgi için Ek Yardım konusuna [yapısı, OLE hata kodları](/windows/desktop/com/structure-of-com-error-codes) Windows SDK. SCODE veri türü için HRESULT veri türü eşlemeleri.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
