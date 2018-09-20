---
title: Cdaoquerydefınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 930626a2c28009f8f0174069a88a59a12c9059af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418547"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo Yapısı

`CDaoQueryDefInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan QueryDefs hakkında bilgiler içerir.

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
QueryDefs adlandıran. Daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın. Çağrı [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) doğrudan bu özelliği alınamadı.

*m_nType*<br/>
QueryDefs işletimsel türünü belirten bir değer. Değerin aşağıdakilerden biri olabilir:

- `dbQSelect` Seçin — sorgu kayıtları seçer.

- `dbQAction` Eylem — sorgu taşır veya veriler değiştiğinde, ancak kayıt döndürmez.

- `dbQCrosstab` Çapraz — sorgu bir elektronik tablo benzer biçimde veri döndürür.

- `dbQDelete` Sil: Belirtilen satır kümesi sorgu siler.

- `dbQUpdate` Güncelleştirme — sorgu kayıt kümesini değiştirir.

- `dbQAppend` Ekleme — sorgu yeni kayıtlar tabloyu veya sorguyu sonuna ekler.

- `dbQMakeTable` Tablo oluşturma — sorgu kayıt kümesinden yeni bir tablo oluşturur.

- `dbQDDL` Veri tanımı — sorgu tablolar veya kendi bölümleri yapısını etkiler.

- `dbQSQLPassThrough` Doğrudan — SQL deyimini doğrudan Ara işlem veritabanı arka ucu geçirilir.

- `dbQSetOperation` Birleşim — sorgu belirtilen tüm kayıtlarda bulunan iki veri içeren bir anlık görüntü türü kayıt kümesi nesnesi oluşturur. veya daha fazla yinelenen kayıtları tablolarla kaldırıldı. Yinelemeleri dahil etmek için anahtar sözcüğü ekleme **tüm** querydef'ın SQL deyiminde.

- `dbQSPTBulk` İle kullanılan `dbQSQLPassThrough` kayıtları döndürmeyen bir sorgu belirtmek için.

> [!NOTE]
>  SQL doğrudan sorgu oluşturmak için ayarlamayın `dbQSQLPassThrough` sabit. QueryDefs oluştururken ve Connect özelliğini ayarlayın. Bu Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

Daha fazla bilgi için DAO Yardımı'nda "Type özelliği" konusuna bakın.

*m_dateCreated*<br/>
Tarih ve saat querydef oluşturuldu. Doğrudan querydef oluşturulduğu tarih almak için arama [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevinin `CDaoTableDef` tabloyla ilişkili nesne. Açıklamaları aşağıda daha fazla bilgi için bkz. Ayrıca DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

*m_dateLastUpdated*<br/>
Tarih ve saat querydef yapılan en son değişikliği. Doğrudan tablonun son güncelleme tarihi almak için arama [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) querydef üye işlevi. Açıklamaları aşağıda daha fazla bilgi için bkz. Ve DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

*m_bUpdatable*<br/>
QueryDefs için değişiklik yapılamaz olup olmadığını gösterir. Bu özellik TRUE ise, querydef güncelleştirilebilir; Aksi takdirde, bu değildir. Güncelleştirilebilir querydef nesnesinin sorgu tanımı değiştirilebilir anlamına gelir. Sorgu tanımı güncelleştirilebilir, sonuçta elde edilen kayıt güncelleştirilebilir olmasa bile QueryDefs güncelleştirilebilir özelliği TRUE olarak ayarlandığında. Bu özellik doğrudan almak için querydef ait arama [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) üye işlevi. Daha fazla bilgi için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.

*m_bReturnsRecords*<br/>
Harici bir veritabanına doğrudan geçirilen bir SQL sorgu kayıt döndürüp döndürmediğini gösterir. Bu özellik TRUE ise, sorgu kayıtları döndürür. Bu özellik doğrudan almak için arama [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Dış veritabanları için tüm SQL geçiş sorguları, kayıtları döndürür. Örneğin, bir SQL **güncelleştirme** deyimi, kayıt sırasında bir SQL dönmeden kayıtları güncelleştirir **seçin** deyimi kayıtları döndürür. Daha fazla bilgi için DAO Yardımı'nda "ReturnsRecords özelliğini" konusuna bakın.

*m_strSQL*<br/>
QueryDefs tarafından çalıştırılan bir sorguyu tanımlayan bir SQL deyimi. Sorgu yürütülürken nasıl kayıtları, gruplandırılmış ve sıralı seçileceğini belirleyen SQL deyimi SQL özelliğini içerir. Sorgu, bir dinamik veya anlık görüntü türü kayıt kümesi nesnesi eklemek için kayıtları seçmek için kullanabilirsiniz. Toplu sorgular kayıt döndürdüğünü olmadan verileri değiştirmek için de tanımlayabilirsiniz. Doğrudan querydef's çağırarak bu özelliğin değerini alabilir [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) üye işlevi.

*m_strConnect*<br/>
Doğrudan bir sorguda kullanılan bir veritabanının kaynak hakkında bilgi sağlar. Bu bilgiler bir bağlantı dizesi alır. Daha fazla bilgi için ilgili bağlantı dizesi ve doğrudan bu özelliğin değerini alma hakkında daha fazla bilgi için bkz: [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevi.

*m_nODBCTimeout*<br/>
Microsoft Jet veritabanı altyapısı bir zaman aşımı hatası önce bekleyeceği saniye sayısını bir ODBC veritabanı üzerinde bir sorgu çalıştırıldığında gerçekleşir. Microsoft SQL Server gibi bir ODBC veritabanı kullanılırken ağ trafiği veya ODBC sunucu kullanımının nedeniyle gecikmeler olabilir. Sonsuza kadar beklemek yerine, bir hata oluşturur önce Microsoft Jet motoru bekleyeceği süreyi belirtebilirsiniz. Varsayılan zaman aşımı değer 60 saniyedir. Doğrudan querydef's çağırarak bu özelliğin değerini alabilir [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) üye işlevi. Daha fazla bilgi için DAO Yardımı'nda "ODBCTimeout özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi querydef olan [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) sınıf üyesi işlevinde `CDaoDatabase`.

Tarafından alınan bilgileri [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi depolanan bir `CDaoQueryDefInfo` yapısı. Çağrı `GetQueryDefInfo` QueryDefs olan QueryDefs koleksiyonu içinde depolanan veritabanı nesnesi için. `CDaoQueryDefInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoQueryDefInfo` nesne. Sınıf `CDaoDatabase` döndürülen tüm özellikler doğrudan erişmek için üye işlevlerini de sağlayan bir `CDaoQueryDefInfo` nesne muhtemelen seyrek çağırmak ihtiyacınız olacak şekilde `GetQueryDefInfo`.

QueryDefs alanlar veya parametre koleksiyonuna yeni bir alan veya parametre nesne ekleme, temel alınan veritabanına yeni nesne için belirtilen veri türü desteklemiyorsa bir özel durum oluşturulur.

Tarih ve saat ayarları üzerinde querydef oluşturulduğu veya en son güncelleştirilen bilgisayardan türetilir. Çok kullanıcılı bir ortamda kullanıcılar bu ayarları dosya sunucusu kullanarak doğrudan gelen almalısınız **net zaman** Notes ve LastUpdated özelliği ayarlarında Tutarsızlıklardan kaçınmak için komutu.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
