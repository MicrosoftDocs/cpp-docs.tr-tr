---
title: CDaoQueryDefInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: e2f0325237a30989637821464c63a4d8b8000b1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368944"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo Yapısı

Yapı, `CDaoQueryDefInfo` veri erişim nesneleri (DAO) için tanımlanan bir querydef nesnesi hakkında bilgi içerir.

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
Querydef nesnesini benzersiz bir şekilde adlandırır. Daha fazla bilgi için DAO Yardım'daki "Ad Özelliği" konusuna bakın. [CDaoQueryDef'i arayın::Bu](../../mfc/reference/cdaoquerydef-class.md#getname) özelliği doğrudan almak için GetName' yi arayın.

*m_nType*<br/>
Querydef nesnesinin çalışma türünü gösteren bir değer. Değer aşağıdakilerden biri olabilir:

- `dbQSelect`Seçin — sorgu kayıtları seçer.

- `dbQAction`Eylem — sorgu verileri taşır veya değiştirir, ancak kayıtları döndürmez.

- `dbQCrosstab`Çapraz sekme — sorgu verileri elektronik tablo benzeri bir biçimde döndürür.

- `dbQDelete`Sil — sorgu belirtilen satırlar kümesini siler.

- `dbQUpdate`Güncelleştirme — sorgu bir kayıt kümesini değiştirir.

- `dbQAppend`Ek — sorgu, tablo nun veya sorgunun sonuna yeni kayıtlar ekler.

- `dbQMakeTable`Make-table — sorgu bir kayıt kümesinden yeni bir tablo oluşturur.

- `dbQDDL`Veri tanımı — sorgu tabloların yapısını veya parçalarını etkiler.

- `dbQSQLPassThrough`Geçiş — SQL deyimi, ara işlem yapılmadan doğrudan veritabanı arka ucuna aktarılır.

- `dbQSetOperation`Birleştirme — sorgu, yinelenen kayıtların kaldırıldığı iki veya daha fazla tabloda belirtilen tüm kayıtlardan veri içeren anlık görüntü türünde bir kayıt kümesi nesnesi oluşturur. Yinelenenleri eklemek için, querydef'in SQL deyimine **ALL** anahtar sözcüklerini ekleyin.

- `dbQSPTBulk`Kayıtları `dbQSQLPassThrough` döndürmeyen bir sorgu belirtmek için kullanılır.

> [!NOTE]
> Bir SQL geçiş sorgusu oluşturmak için, sabiti `dbQSQLPassThrough` ayarlamazsınız. Bu, bir querydef nesnesi oluşturduğunuzda ve Connect özelliğini ayarladığınızda Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

Daha fazla bilgi için DAO Yardım'daki "Özellik Yazın" konusuna bakın.

*m_dateCreated*<br/>
Querydef'in oluşturulduğu tarih ve saat. Querydef'in oluşturulduğu tarihi doğrudan almak için, tabloyla `CDaoTableDef` ilişkili nesnenin [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevini arayın. Daha fazla bilgi için aşağıdaki Yorumlara bakın. Ayrıca DAO Yardım'da "DateCreated, LastUpdated Properties" konusuna bakın.

*m_dateLastUpdated*<br/>
Querydef'te yapılan en son değişikliğin tarihi ve saati. Tablonun en son güncelleştirilen tarihi doğrudan almak için querydef'in [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) üye işlevini arayın. Daha fazla bilgi için aşağıdaki Yorumlara bakın. DAO Yardım'da "DateCreated, LastUpdated Properties" konusuna bakın.

*m_bUpdatable*<br/>
Querydef nesnesi üzerinde değişiklik yapılıp yapılamayacağını gösterir. Bu özellik TRUE ise, querydef güncellenir; aksi takdirde, öyle değildir. Güncellenebilir, querydef nesnesinin sorgu tanımının değiştirilebildiği anlamına gelir. Sorgu tanımı güncelleştirilebiliyorsa, ortaya çıkan kayıt kümesi güncelleştirilmese bile, sorgu nesnesinin güncellenebilir özelliği TRUE olarak ayarlanır. Bu özelliği doğrudan almak için querydef'in [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) üye işlevini arayın. Daha fazla bilgi için DAO Yardım'daki "Güncelilebilir Özellik" konusuna bakın.

*m_bReturnsRecords*<br/>
Harici bir veritabanına bir SQL geçiş sorgusunun kayıtları döndürüp döndürmediğini gösterir. Bu özellik TRUE ise, sorgu kayıtları döndürür. Doğrudan bu özelliği almak için [CDaoQueryDef'i arayın::GetReturnsRecords.](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords) Dış veritabanlarına tüm SQL geçiş sorguları kayıtları döndürmez. Örneğin, bir SQL **UPDATE** deyimi kayıtları döndürmeden güncelleştirirken, BIR SQL **SELECT** deyimi kayıtları döndürmektedir. Daha fazla bilgi için DAO Yardım'daki "ReturnsRecords Property" konusuna bakın.

*m_strSQL*<br/>
Querydef nesnesi tarafından yürütülen sorguyu tanımlayan SQL deyimi. SQL özelliği, sorguyu çalıştırdığınızda kayıtların nasıl seçiliş, gruplandırılmak ve sıralanır olduğunu belirleyen SQL deyimini içerir. Sorguyu, dynaset veya anlık görüntü türü kayıt kümesi nesnesine eklemek için kayıtları seçmek için kullanabilirsiniz. Ayrıca, kayıtları döndürmeden verileri değiştirmek için toplu sorgular da tanımlayabilirsiniz. Querydef'in [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) üye işlevini arayarak bu özelliğin değerini doğrudan alabilirsiniz.

*m_strConnect*<br/>
Geçiş sorgusunda kullanılan veritabanının kaynağı hakkında bilgi sağlar. Bu bilgiler bir bağlantı dizesi şeklini alır. Bağlantı dizeleri hakkında daha fazla bilgi ve bu özelliğin değerini doğrudan alma hakkında bilgi için [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevine bakın.

*m_nODBCTimeout*<br/>
Bir sorgu ODBC veritabanında çalıştırıldığında, zaman sonu hatası oluşmadan önce Microsoft Jet veritabanı altyapısının beklediği saniye sayısı. Microsoft SQL Server gibi bir ODBC veritabanı kullanıyorsanız, ağ trafiği veya ODBC sunucusunun yoğun kullanımı nedeniyle gecikmeler olabilir. Süresiz beklemek yerine, Microsoft Jet altyapısının hata üretmeden önce ne kadar bekleyeceğini belirtebilirsiniz. Varsayılan zaman kaybı değeri 60 saniyedir. Querydef'in [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) üye işlevini arayarak bu özelliğin değerini doğrudan alabilirsiniz. Daha fazla bilgi için DAO Yardım'daki "ODBCTimeout Özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Querydef sınıfı [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)bir nesnedir. Birincil, İkincil ve Tüm yukarıda başvurular nasıl bilgi sınıfta `CDaoDatabase` [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi tarafından döndürülür gösterir.

CDaoDatabase tarafından alınan [bilgiler::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi bir `CDaoQueryDefInfo` yapıda depolanır. QueryDefs'in querydef nesnesini toplaması veritabanı nesnesini arayın. `GetQueryDefInfo` `CDaoQueryDefInfo`ayrıca hata `Dump` ayıklama yapılarında bir üye işlev tanımlar. Bir `Dump` `CDaoQueryDefInfo` nesnenin içeriğini dökümü için kullanabilirsiniz. Sınıf `CDaoDatabase` ayrıca, bir `CDaoQueryDefInfo` nesnede döndürülen tüm özelliklere doğrudan erişmek için üye işlevleri `GetQueryDefInfo`de sağlar, bu nedenle büyük olasılıkla nadiren aramanız gerekir.

Bir querydef nesnesinin Alanlar veya Parametreler koleksiyonuna yeni bir alan veya parametre nesnesi eklediğinizde, alt veritabanı yeni nesne için belirtilen veri türünü desteklemiyorsa bir özel durum atılır.

Tarih ve saat ayarları, querydef'in oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcılar DateCreated ve LastUpdated özellik ayarlarındaki tutarsızlıkları önlemek için **net zaman** komutunu kullanarak bu ayarları doğrudan dosya sunucusundan almalıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
