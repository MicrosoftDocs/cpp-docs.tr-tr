---
description: 'Şu konuda daha fazla bilgi edinin: Cdaoquerydefinınfo yapısı'
title: CDaoQueryDefInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: 46b9b49d91d3d005d941eb585663c205fe30b2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271817"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo Yapısı

`CDaoQueryDefInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir QueryDef nesnesi hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
QueryDef nesnesini benzersiz olarak adlandırır. Daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın. Bu özelliği doğrudan almak için [CDaoQueryDef:: GetName](../../mfc/reference/cdaoquerydef-class.md#getname) çağrısı yapın.

*m_nType*<br/>
Bir QueryDef nesnesinin işletimsel türünü gösteren bir değer. Değer aşağıdakilerden biri olabilir:

- `dbQSelect` Seç — sorgu kayıtları seçer.

- `dbQAction` Eylem — sorgu verileri hareket ettirir veya değiştirir ancak kayıt döndürmez.

- `dbQCrosstab` Çapraz — sorgu verileri elektronik tablo benzeri biçimde döndürür.

- `dbQDelete` Sil — sorgu belirtilen satırların bir kümesini siler.

- `dbQUpdate` Güncelleştirme — sorgu bir kayıt kümesini değiştirir.

- `dbQAppend` Ekleme — sorgu, bir tablonun veya sorgunun sonuna yeni kayıtlar ekler.

- `dbQMakeTable` Make tablosu — sorgu bir kayıt kümesinden yeni bir tablo oluşturur.

- `dbQDDL` Veri tanımı — sorgu tabloların veya parçalarının yapısını etkiler.

- `dbQSQLPassThrough` Doğrudan geçiş — SQL deyimleri, ara işlem olmadan doğrudan veritabanı arka ucuna geçirilir.

- `dbQSetOperation` Birleşim — sorgu, yinelenen kayıtları kaldırılmış iki veya daha fazla tabloda belirtilen tüm kayıtlardan verileri içeren bir anlık görüntü türü kayıt kümesi nesnesi oluşturur. Yinelemeleri dahil etmek için, QueryDef 'in SQL **deyimindeki anahtar sözcüğünü** ekleyin.

- `dbQSPTBulk``dbQSQLPassThrough`Kayıt döndürmeyen bir sorgu belirtmek için ile birlikte kullanılır.

> [!NOTE]
> Bir SQL geçişli sorgu oluşturmak için, `dbQSQLPassThrough` sabiti ayarlamayın. Bu, bir QueryDef nesnesi oluşturup Connect özelliğini ayarladıktan sonra Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

Daha fazla bilgi için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

*m_dateCreated*<br/>
QueryDef 'in oluşturulduğu tarih ve saat. QueryDef 'in oluşturulduğu tarihi doğrudan almak için tabloyla ilişkili nesnenin [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevini çağırın `CDaoTableDef` . Daha fazla bilgi için aşağıdaki açıklamalara bakın. Ayrıca, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

*m_dateLastUpdated*<br/>
QueryDef ' te yapılan en son değişikliğin tarih ve saati. Tablonun son güncelleştirilme tarihini doğrudan almak için, QueryDef 'in [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) üye işlevini çağırın. Daha fazla bilgi için aşağıdaki açıklamalara bakın. Ve DAO yardımı 'nda "DateCreated, LastUpdated Özellikler" konusuna bakın.

*m_bUpdatable*<br/>
Bir QueryDef nesnesine değişiklik yapılıp yapılmadığını belirtir. Bu özellik TRUE ise, QueryDef güncelleştirilebilir; Aksi takdirde, değildir. Güncelleştirilebilir, QueryDef nesnesinin sorgu tanımının değiştirilebileceği anlamına gelir. Sorgu tanımı güncelleştirilüyorsa, sonuçta elde edilen kayıt kümesi güncelleştirilebilir olmasa bile, bir QueryDef nesnesinin güncelleştirilebilir özelliği TRUE olarak ayarlanır. Bu özelliği doğrudan almak için, QueryDef 'in [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) üye işlevini çağırın. Daha fazla bilgi için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

*m_bReturnsRecords*<br/>
Dış veritabanına yönelik bir SQL geçişli sorgunun kayıt döndürüp döndürmeyeceğini belirtir. Bu özellik TRUE ise sorgu kayıtları döndürür. Bu özelliği doğrudan almak için, [CDaoQueryDef:: GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)çağırın. Dış veritabanlarına yönelik tüm SQL geçiş sorguları kayıt döndürmez. Örneğin, SQL **Update** deyimleri kayıtları döndürmeden kayıtları güncelleştirir, ancak SQL **Select** deyimleri kayıt döndürür. Daha fazla bilgi için, DAO yardımı 'nda "ReturnsRecords özelliği" konusuna bakın.

*m_strSQL*<br/>
Bir QueryDef nesnesi tarafından yürütülen sorguyu tanımlayan SQL deyimidir. SQL özelliği, sorguyu yürüttüğünüzde kayıtların nasıl seçili, gruplanmış ve sıralı olduğunu belirleyen SQL ifadesini içerir. Sorgu kümesini, dynaset veya anlık görüntü türünde bir Recordset nesnesine eklenecek kayıtları seçmek için kullanabilirsiniz. Ayrıca, kayıtları döndürmeden verileri değiştirmek için toplu sorgular tanımlayabilirsiniz. Bu özelliğin değerini, QueryDef 'in [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) üye işlevini çağırarak doğrudan alabilirsiniz.

*m_strConnect*<br/>
Doğrudan sorgu içinde kullanılan bir veritabanının kaynağı hakkında bilgi sağlar. Bu bilgiler bir bağlantı dizesi biçimini alır. Bağlantı dizeleri hakkında daha fazla bilgi edinmek ve bu özelliğin değerini doğrudan alma hakkında daha fazla bilgi için, bkz. [CDaoDatabase:: GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) member işlevi.

*m_nODBCTimeout*<br/>
ODBC veritabanında bir sorgu çalıştırıldığında, bir zaman aşımı hatası oluştuktan önce Microsoft Jet veritabanı altyapısının bekleyeceği saniye sayısı. Microsoft SQL Server gibi bir ODBC veritabanı kullanırken, ağ trafiği veya ODBC sunucusunun yoğun kullanımı nedeniyle gecikme olabilir. Süresiz olarak beklemek yerine, Microsoft Jet altyapısının bir hata üretmeden önce ne kadar bekleyeceğini belirtebilirsiniz. Varsayılan zaman aşımı değeri 60 saniyedir. Bu özelliğin değerini, QueryDef ' in [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) üye işlevini çağırarak doğrudan elde edebilirsiniz. Daha fazla bilgi için, DAO yardımı 'nda "ODBCTimeout Özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

QueryDef, [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)sınıfının bir nesnesidir. Yukarıdaki birincil, Ikincil ve tüm başvurular, bilgilerin sınıfında [Getquerydefinınfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir `CDaoDatabase` .

[CDaoDatabase:: Getquerydefinınfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi tarafından alınan bilgiler bir `CDaoQueryDefInfo` yapıda depolanıyor. `GetQueryDefInfo`QueryDefs koleksiyonunda QueryDef nesnesi depolanan veritabanı nesnesi için çağrı. `CDaoQueryDefInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoQueryDefInfo` . Sınıf `CDaoDatabase` Ayrıca bir nesnede döndürülen tüm özelliklere doğrudan erişim için üye işlevleri sağlar `CDaoQueryDefInfo` , bu sayede nadiren çağrı yapmanız gerekir `GetQueryDefInfo` .

Bir QueryDef nesnesinin Fields veya Parameters koleksiyonuna yeni bir alan veya parametre nesnesi eklediğinizde, temel alınan veritabanı yeni nesne için belirtilen veri türünü desteklemiyorsa bir özel durum oluşturulur.

Tarih ve saat ayarları, QueryDef 'in oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, Kullanıcı bu ayarları, DateCreated ve LastUpdated Özellik ayarlarındaki tutarsızlıkları önlemek için **net time** komutunu kullanarak doğrudan dosya sunucusundan alırlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)
