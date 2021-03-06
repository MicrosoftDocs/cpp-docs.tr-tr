---
description: 'Daha fazla bilgi edinin: CDaoException sınıfı'
title: CDaoException sınıfı
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
ms.openlocfilehash: eb7da6746d2ce539a2ee7b0b28a9a4e9c6c6de64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250900"
---
# <a name="cdaoexception-class"></a>CDaoException sınıfı

Veri erişim nesnelerine (DAO) göre MFC veritabanı sınıflarından kaynaklanan bir özel durum koşulunu temsil eder. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Syntax

```
class CDaoException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException:: CDaoException](#cdaoexception)|Bir `CDaoException` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException:: GetErrorCount](#geterrorcount)|Veritabanı altyapısının hata koleksiyonundaki hata sayısını döndürür.|
|[CDaoException:: GetErrorInfo](#geterrorinfo)|Hatalar koleksiyonundaki belirli bir hata nesnesi hakkında hata bilgilerini döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoException:: m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO sınıflarında herhangi bir hata için genişletilmiş bir hata kodu içerir.|
|[CDaoException:: m_pErrorInfo](#m_perrorinfo)|Bir DAO hata nesnesi hakkında bilgi içeren bir [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) nesnesine yönelik bir işaretçi.|
|[CDaoException:: m_scode](#m_scode)|Hatayla ilişkili [SCODE](#m_scode) değeri.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, özel durumun nedenini belirlemede kullanabileceğiniz ortak veri üyelerini içerir. `CDaoException` nesneler, DAO veritabanı sınıflarının üye işlevleri tarafından oluşturulur ve oluşturulur.

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına, DAO sınıflarıyla erişmeye devam edebilirsiniz. Genel olarak, DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıflarından daha sahiptir; DAO tabanlı sınıflar, ODBC sürücüleri dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. DAO tabanlı sınıflar, DAO 'YU doğrudan çağırmak zorunda kalmadan, sınıflar aracılığıyla tablo ekleme gibi veri tanımlama dili (DDL) işlemlerini de destekler. ODBC sınıfları tarafından oluşturulan özel durumlar hakkında daha fazla bilgi için bkz. [CDBException](../../mfc/reference/cdbexception-class.md).

Özel durum nesnelerine bir [catch](../../mfc/reference/exception-processing.md#catch) ifadesinin kapsamı içinde erişebilirsiniz. Ayrıca `CDaoException` , [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) global işlevi ile kendi kodunuzla nesneler de oluşturabilirsiniz.

MFC 'de, tüm DAO hataları, türünde özel durumlar olarak ifade edilir `CDaoException` . Bu türde bir özel durumu yakalarsanız, `CDaoException` veritabanı altyapısının hata koleksiyonunda depolanan herhangi BIR dao hata nesnesinden bilgi almak için üye işlevlerini kullanabilirsiniz. Her hata oluştuğunda, bir veya daha fazla hata nesnesi hatalar koleksiyonuna yerleştirilir. (Normalde koleksiyon yalnızca bir hata nesnesi içerir; ODBC veri kaynağı kullanıyorsanız, birden çok hata nesnesi almanız daha olasıdır.) Başka bir DAO işlemi hata oluşturduğunda, hatalar koleksiyonu temizlenir ve yeni hata nesnesi hatalar koleksiyonuna yerleştirilir. Hata üretmesiz DAO işlemlerinin, hatalar koleksiyonu üzerinde hiçbir etkisi yoktur.

DAO hata kodları için, DAOERR. H dosyasına bakın. İlgili bilgiler için, DAO yardımı 'nda "Yakalanabilir veri erişim hataları" konusuna bakın.

Genel veya nesneler hakkında özel durum işleme hakkında daha fazla bilgi için `CDaoException` bkz. Makaleler [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İkinci makale, DAO 'da özel durum işlemeyi gösteren örnek kodu içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a> CDaoException:: CDaoException

Bir `CDaoException` nesnesi oluşturur.

```
CDaoException();
```

### <a name="remarks"></a>Açıklamalar

Normalde, Framework kendi kodu bir özel durum oluşturduğunda özel durum nesneleri oluşturur. Nadiren özel bir durum nesnesi oluşturmanız gerekir. Kendi kodınızdan bir oluşturmak istiyorsanız `CDaoException` , [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)genel işlevini çağırın.

Ancak, MFC sınıflarının kapsülleyip sarmaladığı DAO arabirimi işaretçileri aracılığıyla DAO 'ya doğrudan çağrılar yapıyorsanız, açıkça bir özel durum nesnesi oluşturmak isteyebilirsiniz. Bu durumda, DAO 'dan hata bilgilerini almanız gerekebilir. Bir çalışma alanının veritabanları koleksiyonuna DAODatabases arabirimi aracılığıyla bir DAO yöntemi çağırdığınızda, DAO 'da bir hata oluştuğunu varsayalım.

##### <a name="to-retrieve-the-dao-error-information"></a>DAO hata bilgilerini almak için

1. Bir `CDaoException` nesne oluşturun.

1. Veritabanı altyapısının hata koleksiyonunda kaç hata nesnesi olduğunu öğrenmek için özel durum nesnesinin [GetErrorCount](#geterrorcount) üye işlevini çağırın. (Normalde, bir ODBC veri kaynağı kullanmadığınız durumlar dışında yalnızca bir tane.)

1. Özel durum nesnesi yoluyla, koleksiyondaki dizine göre belirli bir hata nesnesini tek seferde almak için, özel durum nesnesinin [GetErrorInfo](#geterrorinfo) üye işlevini çağırın. Özel durum nesnesini bir DAO hata nesnesi için proxy olarak düşünün.

1. M_pErrorInfo veri üyesinde döndüren geçerli [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısını inceleyin `GetErrorInfo` . [](#m_perrorinfo) Üyeleri, DAO hatası hakkında bilgi sağlar.

1. ODBC veri kaynağı söz konusu olduğunda, daha fazla hata nesnesi için gerektiğinde 3 ve 4 numaralı adımları tekrarlayın.

1. Özel durum nesnesini yığında oluşturduysanız, bunu **`delete`** bitirdiğinizde işleci ile silin.

MFC DAO sınıflarında hataları işleme hakkında daha fazla bilgi için bkz. [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

## <a name="cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a> CDaoException:: GetErrorCount

Veritabanı altyapısının hata koleksiyonundaki DAO hata nesnelerinin sayısını almak için bu üye işlevi çağırın.

```
short GetErrorCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı altyapısının hata koleksiyonundaki DAO hata nesnelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu bilgiler, koleksiyondaki bir veya daha fazla DAO hata nesnesini almak için hatalar koleksiyonu aracılığıyla döngü için yararlıdır. Bir hata nesnesini dizine veya DAO hata numarasına göre almak için [GetErrorInfo](#geterrorinfo) üye işlevini çağırın.

> [!NOTE]
> Normalde hatalar koleksiyonunda yalnızca bir hata nesnesi vardır. Ancak bir ODBC veri kaynağıyla çalışıyorsanız, birden fazla olabilir.

## <a name="cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a> CDaoException:: GetErrorInfo

Hatalar koleksiyonundaki belirli bir hata nesnesi hakkında hata bilgilerini döndürür.

```cpp
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Dizine göre arama için veritabanı altyapısının hatalar koleksiyonundaki hata bilgilerinin dizini.

### <a name="remarks"></a>Açıklamalar

Özel durumla ilgili aşağıdaki tür bilgileri elde etmek için bu üye işlevi çağırın:

- Hata kodu

- Kaynak

- Açıklama

- Yardım dosyası

- Yardım bağlamı

`GetErrorInfo` bilgileri özel durum nesnesinin `m_pErrorInfo` veri üyesinde depolar. Döndürülen bilgilerin kısa bir açıklaması için bkz. [m_pErrorInfo](#m_perrorinfo). MFC tarafından oluşturulan türdeki bir özel durumu yakalarsanız `CDaoException` `m_pErrorInfo` üye zaten doldurulur. Doğrudan DAO çağrısını seçerseniz, doldurmanız için özel durum nesnesinin `GetErrorInfo` üye işlevini çağırmanız gerekir `m_pErrorInfo` . Daha ayrıntılı bir açıklama için, [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısına bakın.

DAO özel durumları ve örnek kod hakkında daha fazla bilgi için bkz. [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

## <a name="cdaoexceptionm_nafxdaoerror"></a><a name="m_nafxdaoerror"></a> CDaoException:: m_nAfxDaoError

MFC genişletilmiş hata kodu içerir.

### <a name="remarks"></a>Açıklamalar

Bu kod, MFC DAO sınıflarının belirli bir bileşeninin erred olduğu durumlarda sağlanır.

Olası değerler şunlardır:

- NO_AFX_DAO_ERROR en son işlem, MFC genişletilmiş hatası ile sonuçlanmadı. Ancak, işlem DAO veya OLE 'den başka hatalar üretti, bu nedenle [m_pErrorInfo](#m_perrorinfo) ve muhtemelen [m_scode](#m_scode)denetlemeniz gerekir.

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC, Microsoft Jet veritabanı altyapısını başlatamıyor. OLE başlatılamadı veya DAO veritabanı altyapısı nesnesinin bir örneğini oluşturmak imkansız olabilir. Bu sorunlar genellikle, DAO veya OLE 'nin hatalı bir yüklemesini önerir.

- AFX_DAO_ERROR_DFX_BIND bir DAO Kayıt alanı değişimi (DFX) işlev çağrısında kullanılan bir adres yok veya geçersiz (adres veri bağlamak için kullanılmadı). Bir DFX çağrısında hatalı bir adres geçirtiniz veya adres, DFX işlemleri arasında geçersiz olmuş olabilir.

- Bir QueryDef veya açık durumda olmayan bir TableDef nesnesine dayalı bir kayıt kümesi açmaya çalıştınız AFX_DAO_ERROR_OBJECT_NOT_OPEN.

## <a name="cdaoexceptionm_perrorinfo"></a><a name="m_perrorinfo"></a> CDaoException:: m_pErrorInfo

`CDaoErrorInfo` [GetErrorInfo](#geterrorinfo)ÇAĞıRARAK son aldığınız dao hata nesnesi hakkında bilgi sağlayan bir yapıya yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu nesne aşağıdaki bilgileri içerir:

|CDaoErrorInfo üyesi|Bilgi|Anlamı|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|Hata Kodu|DAO hata kodu|
|`m_strSource`|Kaynak|İlk olarak hatayı oluşturan nesnenin veya uygulamanın adı|
|`m_strDescription`|Açıklama|Hatayla ilişkili açıklayıcı bir dize|
|`m_strHelpFile`|Yardım dosyası|Kullanıcının sorun hakkında bilgi alabileceğiniz bir Windows Yardım dosyasının yolu|
|`m_lHelpContext`|Yardım bağlamı|DAO Yardım dosyasındaki bir konunun bağlam KIMLIĞI|

Nesnesinde yer alan bilgiler hakkında tam Ayrıntılar için `CDaoErrorInfo` , [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) yapısına bakın.

## <a name="cdaoexceptionm_scode"></a><a name="m_scode"></a> CDaoException:: m_scode

Hatayı açıklayan bir tür değeri içerir `SCODE` .

### <a name="remarks"></a>Açıklamalar

Bu bir OLE kodudur. Bu değeri nadiren kullanmanız gerekir çünkü neredeyse tüm durumlarda, diğer veri üyelerinde daha belirli MFC veya DAO hata bilgileri kullanılabilir `CDaoException` .

SCODE hakkında daha fazla bilgi için Windows SDK [OLE hata kodlarının konu yapısına](/windows/win32/com/structure-of-com-error-codes) bakın. SCODE Veri türü HRESULT veri türüyle eşlenir.

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)
