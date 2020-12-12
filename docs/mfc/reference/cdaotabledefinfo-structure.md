---
description: 'Daha fazla bilgi edinin: Cdaotabledefinınfo yapısı'
title: CDaoTableDefInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 953a255b35860dcce0ac8d3ef5081951dd15c344
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247982"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo Yapısı

`CDaoTableDefInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir TableDef nesnesi hakkındaki bilgileri içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Tabledef nesnesini benzersiz olarak adlandırır. Bu özelliğin değerini doğrudan almak için TableDef nesnesinin [GetName](../../mfc/reference/cdaotabledef-class.md#getname) üye işlevini çağırın. Daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_bUpdatable*<br/>
Tabloda değişikliklerin yapılıp yapılmayacağını belirtir. Bir tablonun güncelleştirilebilir olup olmadığını belirlemenin hızlı yolu, `CDaoTableDef` tablo için bir nesne açıp nesnenin [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) üye işlevini çağırmaktadır. `CanUpdate` Yeni oluşturulan bir TableDef nesnesi için her zaman sıfır olmayan (TRUE) ve ekli bir TableDef nesnesi için 0 (FALSE) döndürür. Yeni bir TableDef nesnesi yalnızca geçerli kullanıcının yazma iznine sahip olduğu bir veritabanına eklenebilir. Tablo yalnızca güncelleştirilemez alanlar içeriyorsa `CanUpdate` 0 değerini döndürür. Bir veya daha fazla alan güncelleştiribir zaman, `CanUpdate` sıfır dışında bir değer döndürür. Yalnızca güncelleştirilebilir alanları düzenleyebilirsiniz. Daha fazla bilgi için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

*m_lAttributes*<br/>
TableDef nesnesi tarafından temsil edilen tablonun özelliklerini belirtir. Bir TableDef öğesinin geçerli özniteliklerini almak için, [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) üye işlevini çağırın. Döndürülen değer bu uzun sabitlerin bir birleşimi olabilir (bit düzeyinde OR (**&#124;**) işleci kullanılarak):

- `dbAttachExclusive` Microsoft Jet veritabanı altyapısını kullanan veritabanları için, tablonun özel kullanım için açılmış bir eklenmiş tablo olduğunu gösterir.

- `dbAttachSavePWD` Microsoft Jet veritabanı altyapısını kullanan veritabanları için, ekli tablo için Kullanıcı KIMLIĞI ve parolanın bağlantı bilgileriyle kaydedildiğini belirtir.

- `dbSystemObject` Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan bir sistem tablosu olduğunu gösterir. (Salt okunur.)

- `dbHiddenObject` Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan gizli bir tablo olduğunu gösterir (geçici kullanım için). (Salt okunur.)

- `dbAttachedTable` Tablonun, Paradox veritabanı gibi ODBC olmayan bir veritabanından ekli tablo olduğunu gösterir.

- `dbAttachedODBC` Tablonun, Microsoft SQL Server gibi bir ODBC veritabanından ekli tablo olduğunu gösterir.

*m_dateCreated*<br/>
Tablonun oluşturulduğu tarih ve saat. Tablonun oluşturulduğu tarihi doğrudan almak için, tabloyla ilişkili nesnenin [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevini çağırın `CDaoTableDef` . Daha fazla bilgi için aşağıdaki açıklamalara bakın. İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

*m_dateLastUpdated*<br/>
Tablonun tasarımında yapılan en son değişikliğin tarih ve saati. Tablonun son güncelleştirilme tarihini doğrudan almak için tabloyla ilişkili nesnenin [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) üye işlevini çağırın `CDaoTableDef` . Daha fazla bilgi için aşağıdaki açıklamalara bakın. İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

*m_strSrcTableName*<br/>
Varsa, eklenen tablonun adını belirtir. Kaynak tablo adını doğrudan almak için tabloyla ilişkili nesnenin [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) üye işlevini çağırın `CDaoTableDef` .

*m_strConnect*<br/>
Açık bir veritabanının kaynağı hakkında bilgi sağlar. Nesnenizin [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevini çağırarak bu özelliği kontrol edebilirsiniz `CDaoTableDef` . Bağlantı dizeleri hakkında daha fazla bilgi için bkz `GetConnect` ..

*m_strValidationRule*<br/>
TableDef alanlarındaki verileri, değiştirilmiş veya bir tabloya eklendikçe doğrulayan bir değer. Doğrulama yalnızca Microsoft Jet veritabanı altyapısını kullanan veritabanları için desteklenir. Doğrulama kuralını doğrudan almak için, tabloyla ilişkili nesnenin [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) üye işlevini çağırın `CDaoTableDef` . İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

*m_strValidationText*<br/>
ValidationRule özelliği tarafından belirtilen doğrulama kuralı karşılanmıyorsa uygulamanızın görüntülemesi gereken iletinin metnini belirten bir değer. İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

*m_lRecordCount*<br/>
Bir tabledef nesnesinde erişilen kayıt sayısı. Bu özellik ayarı salt okunurdur. Kayıt sayısını doğrudan almak için nesnesinin [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) üye işlevini çağırın `CDaoTableDef` . İçin belgeler, `GetRecordCount` daha fazla kayıt sayısını açıklar. Tablo çok sayıda kayıt içeriyorsa, bu sayıyı almanın zaman alan bir işlem olabileceğini unutmayın.

## <a name="remarks"></a>Açıklamalar

TableDef, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)sınıfının bir nesnesidir. Yukarıdaki birincil, Ikincil ve tüm başvurular, bilgilerin sınıfında [Gettabledefinınfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir `CDaoDatabase` .

[CDaoDatabase:: Gettabledefinınfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) üye işlevi tarafından alınan bilgiler bir `CDaoTableDefInfo` yapıda depolanıyor. `GetTableDefInfo` `CDaoDatabase` TableDefs koleksiyonu TableDef nesnesinin depolandığı nesnenin üye işlevini çağırın. `CDaoTableDefInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoTableDefInfo` .

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcılar bu ayarları, DateCreated ve LastUpdated Özellik ayarlarındaki tutarsızlıkları önlemek için doğrudan dosya sunucusundan alırlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)
