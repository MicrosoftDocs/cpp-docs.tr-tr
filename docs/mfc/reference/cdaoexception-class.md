---
title: CDaoException Sınıfı
ms.date: 09/17/2019
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
ms.openlocfilehash: a8a789f4dba06ffe376d8a8e955b026bb23af924
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369007"
---
# <a name="cdaoexception-class"></a>CDaoException Sınıfı

Veri erişim nesnelerine (DAO) dayalı MFC veritabanı sınıflarından kaynaklanan bir özel durum koşulunu temsil eder. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoException::CDaoException](#cdaoexception)|Bir `CDaoException` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|Veritabanı altyapısının Hatalar koleksiyonundaki hata sayısını verir.|
|[CDaoException::GetErrorInfo](#geterrorinfo)|Hatalar koleksiyonunda belirli bir hata nesnesi hakkında hata bilgileri verir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoİst::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO sınıflarında herhangi bir hata için genişletilmiş bir hata kodu içerir.|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Bir DAO hata nesnesi hakkında bilgi içeren bir [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) nesnesine işaretçi.|
|[CDaoException::m_scode](#m_scode)|Hatayla ilişkili [SCODE](#m_scode) değeri.|

## <a name="remarks"></a>Açıklamalar

Sınıf, özel durum nedenini belirlemek için kullanabileceğiniz ortak veri üyelerini içerir. `CDaoException`nesneler DAO veritabanı sınıflarının üye işlevleri tarafından oluşturulur ve atılır.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DAO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz. Genel olarak, DAO'ya dayalı MFC sınıfları ODBC'ye dayalı MFC sınıfları kadar yeteneklidir; DAO tabanlı sınıflar, ODBC sürücüleri aracılığıyla da dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. DAO tabanlı sınıflar, doğrudan DAO'yu aramak zorunda kalmadan sınıflar üzerinden tablo eklemek gibi Veri Tanım Dili (DDL) işlemlerini de destekler. ODBC sınıfları tarafından atılan özel durumlar hakkında bilgi için [CDBException'a](../../mfc/reference/cdbexception-class.md)bakın.

[Catch](../../mfc/reference/exception-processing.md#catch) ifadesi kapsamında özel durum nesnelerine erişebilirsiniz. Ayrıca `CDaoException` [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) global işlevi ile kendi kodunuzdan nesneleri atabilirsiniz.

MFC'de, tüm DAO hataları türde `CDaoException`özel durumlar olarak ifade edilir. Bu tür bir özel durum yakaladığınızda, veritabanı altyapısının Hatalar koleksiyonunda depolanan herhangi bir DAO hata nesnelerinden bilgi almak için üye işlevleri kullanabilirsiniz. `CDaoException` Her hata oluştuğunda, Hatalar koleksiyonuna bir veya daha fazla hata nesnesi yerleştirilir. (Normalde koleksiyon yalnızca bir hata nesnesi içerir; bir ODBC veri kaynağı kullanıyorsanız, birden çok hata nesnesi alma olasılığınız daha yüksektir.) Başka bir DAO işlemi hata oluşturduğunda, Hatalar koleksiyonu temizlenir ve yeni hata nesnesi Hatalar koleksiyonuna yerleştirilir. Hata oluşturmayan DAO işlemlerinin Hatalar koleksiyonu üzerinde hiçbir etkisi yoktur.

DAO hata kodları için DAOERR dosyasına bakın. H. İlgili bilgiler için DAO Yardım'daki "Trappable Data Access Errors" konusuna bakın.

Genel olarak özel durum işleme veya `CDaoException` nesneler hakkında daha fazla bilgi için, [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [Özel Durumlar: Veritabanı Özel Durumlar](../../mfc/exceptions-database-exceptions.md)makalelerine bakın. İkinci makale, DAO'da özel durum işlemeyi gösteren örnek kod içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDaoException::CDaoException

Bir `CDaoException` nesne inşa eder.

```
CDaoException();
```

### <a name="remarks"></a>Açıklamalar

Normalde, kodu bir özel durum attığında çerçeve özel durum nesneleri oluşturur. Nadiren bir özel durum nesnesi açıkça oluşturmanız gerekir. Kendi kodunuzdan `CDaoException` bir atmak istiyorsanız, global fonksiyon [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)arayın.

Ancak, MFC sınıflarının kapsülletiyi içeren DAO arabirim işaretçileri aracılığıyla DAO'ya doğrudan çağrı yapıyorsanız, açıkça bir özel durum nesnesi oluşturmak isteyebilirsiniz. Bu durumda, DAO'dan hata bilgileri almanız gerekebilir. DAODatabases arabirimi üzerinden bir DAO yöntemini çalışma alanının Veritabanları koleksiyonuna çağırdığınızda DAO'da bir hata oluştuğunu varsayalım.

##### <a name="to-retrieve-the-dao-error-information"></a>DAO hata bilgilerini almak için

1. Bir `CDaoException` nesne oluştur.

1. Veritabanı altyapısının Hatalar koleksiyonunda kaç hata nesnesi olduğunu belirlemek için özel durum nesnesinin [GetErrorCount](#geterrorcount) üye işlevini arayın. (Normalde sadece bir tane, bir ODBC veri kaynağı kullanmıyorsanız.)

1. Özel durum nesnesinin [GetErrorInfo](#geterrorinfo) üye işlevini çağırarak, bir defada, koleksiyondaki dizinle, özel durum nesnesi aracılığıyla belirli bir hata nesnesini almak için arayın. Özel durum nesnesini bir DAO hata nesnesi için bir proxy olarak düşünün.

1. [m_pErrorInfo](#m_perrorinfo) veri üyesinde `GetErrorInfo` dönen geçerli [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısını inceleyin. Üyeleri DAO hatası hakkında bilgi sağlar.

1. Bir ODBC veri kaynağı söz konusu olduğunda, daha fazla hata nesnesi için gerektiğinde 3 ve 4 adımlarını yineleyin.

1. Özel durum nesnesini yığında inşa ettiyseniz, bitirdiğinizde **silme** işleciyle silin.

MFC DAO sınıflarında işleme hataları hakkında daha fazla bilgi için, makale [Özel Durumlar bakın: Veritabanı Özel Durumlar](../../mfc/exceptions-database-exceptions.md).

## <a name="cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>CDaoException::GetErrorCount

Veritabanı altyapısının Hatalar koleksiyonundaki DAO hata nesnelerinin sayısını almak için bu üye işlevi arayın.

```
short GetErrorCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı altyapısının Hatalar koleksiyonundaki DAO hata nesnelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu bilgiler, koleksiyondaki bir veya daha fazla DAO hata nesnesinin her birini almak için Hatalar koleksiyonunda döngü yapmak için yararlıdır. Bir hata nesnesini dizin veya DAO hata numarası yla almak için [GetErrorInfo](#geterrorinfo) üye işlevini arayın.

> [!NOTE]
> Normalde Hatalar koleksiyonunda yalnızca bir hata nesnesi vardır. Ancak, bir ODBC veri kaynağıyla çalışıyorsanız, birden fazla olabilir.

## <a name="cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDaoException::GetErrorInfo

Hatalar koleksiyonunda belirli bir hata nesnesi hakkında hata bilgileri verir.

```
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dizin tarafından arama için veritabanı altyapısının Hatalar koleksiyonundaki hata bilgilerinin dizin.

### <a name="remarks"></a>Açıklamalar

Özel durum hakkında aşağıdaki tür bilgileri elde etmek için bu üye işlevini arayın:

- Hata kodu

- Kaynak

- Açıklama

- Yardım dosyası

- Yardım bağlamı

`GetErrorInfo`bilgileri özel durum nesnesinin `m_pErrorInfo` veri üyesinde depolar. Döndürülen bilgilerin kısa bir açıklaması için [m_pErrorInfo](#m_perrorinfo)bakın. MFC tarafından atılan `CDaoException` tür bir özel `m_pErrorInfo` durum yakalarsanız, üye zaten doldurulacaktır. DAO'yu doğrudan aramayı seçerseniz, doldurmak `GetErrorInfo` `m_pErrorInfo`için özel durum nesnesinin üye işlevini kendiniz aramanız gerekir. Daha ayrıntılı bir açıklama için [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısına bakın.

DAO özel durumları ve örnek kod hakkında bilgi için, [özel durumlar makalesine bakın: Veritabanı Özel Durumları.](../../mfc/exceptions-database-exceptions.md)

## <a name="cdaoexceptionm_nafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDaoİst::m_nAfxDaoError

MFC genişletilmiş hata kodu içerir.

### <a name="remarks"></a>Açıklamalar

Bu kod, MFC DAO sınıflarının belirli bir bileşeninin hatalı olduğu durumlarda sağlanır.

Olası değerler şunlardır:

- NO_AFX_DAO_ERROR En son işlem Bir MFC genişletilmiş hata neden olmadı. Ancak, işlem DAO veya OLE diğer hatalar alabilirsiniz, bu yüzden [m_pErrorInfo](#m_perrorinfo) ve muhtemelen [m_scode](#m_scode)kontrol etmelisiniz.

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC, Microsoft Jet veritabanı altyapısını öngöremedi. OLE başlatmayı başaramamış olabilir veya DAO veritabanı altyapısı nesnesinin bir örneğini oluşturmak imkansız olabilir. Bu sorunlar genellikle DAO veya OLE kötü bir yükleme öneririz.

- AFX_DAO_ERROR_DFX_BIND DAO kayıt alanı değişimi (DFX) işlev çağrısında kullanılan bir adres yok veya geçersiz (adres verileri bağlamak için kullanılmadı). Bir DFX aramasında kötü bir adres geçmiş olabilirsiniz veya adres DFX işlemleri arasında geçersiz olmuş olabilir.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN Bir querydef veya açık durumda olmayan bir tablo nesnesine dayalı bir kayıt kümesi ni açmayı denediniz.

## <a name="cdaoexceptionm_perrorinfo"></a><a name="m_perrorinfo"></a>CDaoException::m_pErrorInfo

`CDaoErrorInfo` [GetErrorInfo'yu](#geterrorinfo)arayarak en son aldığınız DAO hata nesnesi hakkında bilgi sağlayan bir yapıiçin işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu nesne aşağıdaki bilgileri içerir:

|CDaoErrorInfo üyesi|Bilgi|Anlamı|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|Hata Kodu|DAO hata kodu|
|`m_strSource`|Kaynak|Hatayı ilk olarak oluşturan nesnenin veya uygulamanın adı|
|`m_strDescription`|Açıklama|Hatayla ilişkili açıklayıcı bir dize|
|`m_strHelpFile`|Yardım Dosyası|Kullanıcının sorun hakkında bilgi alabileceği bir Windows Yardım dosyasına giden yol|
|`m_lHelpContext`|Yardım Bağlamı|DAO Yardım dosyasındaki bir konunun bağlam kimliği|

`CDaoErrorInfo` Nesnede bulunan bilgiler hakkında tüm ayrıntılar için [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısına bakın.

## <a name="cdaoexceptionm_scode"></a><a name="m_scode"></a>CDaoException::m_scode

Hatayı açıklayan bir `SCODE` tür değeri içerir.

### <a name="remarks"></a>Açıklamalar

Bu bir OLE kodu. Hemen hemen her durumda, diğer `CDaoException` veri üyelerinde daha spesifik MFC veya DAO hata bilgileri bulunduğundan, bu değeri nadiren kullanmanız gerekir.

SCODE hakkında daha fazla bilgi için Windows SDK'daki [OLE Hata Kodlarının](/windows/win32/com/structure-of-com-error-codes) konu Yapısı'na bakın. SCODE veri türü, HRESULT veri türüne eşler.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
