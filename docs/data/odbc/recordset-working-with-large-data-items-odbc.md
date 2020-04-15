---
title: 'Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 872fa7229738314b86b6ae6c0d5dc5a5562b27f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360611"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)

Bu konu hem MFC ODBC sınıfları hem de MFC DAO sınıfları için geçerlidir.

> [!NOTE]
> MFC DAO sınıflarını kullanıyorsanız, [cLongBinary](../../mfc/reference/clongbinary-class.md)sınıfı yerine [cbyteArray](../../mfc/reference/cbytearray-class.md) sınıfıyla büyük veri öğelerinizi yönetin. Toplu satır alma ile MFC ODBC sınıfları `CLongBinary` kullanıyorsanız, yerine `CByteArray`kullanın. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Veritabanınızın bit eşlemler (çalışan fotoğrafları, haritalar, ürün resimleri, OLE nesneleri vb.) gibi büyük veri parçalarını depolayabileni varsayalım. Bu tür veriler genellikle İkili Büyük Nesne (veya BLOB) olarak adlandırılır, çünkü:

- Her alan değeri büyüktür.

- Sayılar ve diğer basit veri türlerinin aksine, öngörülebilir bir boyutu yoktur.

- Veriler, programınızın perspektifinden biçimsizdir.

Bu konu, veritabanı sınıflarının bu tür nesnelerle çalışmak için sağladığı desteği açıklar.

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>Büyük Nesneleri Yönetme

Kayıt kümeleri ikili büyük nesneleri yönetmenin özel zorluk çözmek için iki yolu vardır. [CByteArray](../../mfc/reference/cbytearray-class.md) sınıflarını kullanabilirsiniz veya [CLongBinary](../../mfc/reference/clongbinary-class.md)sınıflarını kullanabilirsiniz. Genel olarak, `CByteArray` büyük ikili verileri yönetmek için tercih edilen yoldur.

`CByteArray`[cbyteArray](#_core_the_cbytearray_class) `CLongBinary` Sınıfında açıklandığı gibi, daha fazla genel para gerektirir, ancak daha yeteneklidir. `CLongBinary`[CLongBinary Sınıfı'nda](#_core_the_clongbinary_class)kısaca açıklanmıştır.

Büyük veri öğeleriyle çalışmak için kullanma `CByteArray` hakkında ayrıntılı bilgi için Teknik Not [45'e](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)bakın.

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>CByteArray Sınıfı

`CByteArray`MFC toplama sınıflarından biridir. Bir `CByteArray` nesne dinamik bir bayt dizisini depolar — gerekirse dizi büyüyebilir. Sınıf, yerleşik C++ dizilerinde olduğu gibi dizin tarafından hızlı erişim sağlar. `CByteArray`nesneler seri hale getirilebilir ve tanılama amacıyla atılabilir. Sınıf, belirtilen baytları almak ve ayarlamak, bayt eklemek ve eklemek ve bir bayt veya tüm baytları kaldırmak için üye işlevleri sağlar. Bu olanaklar ikili verileri ayrıştırma etmeyi kolaylaştırır. Örneğin, ikili nesne bir OLE nesnesiyse, gerçek nesneye ulaşmak için bazı üstbilgi baytları üzerinde çalışmanız gerekebilir.

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>Recordsets'te CByteArray kullanma

Kayıt setinizin bir alan veri `CByteArray`üyesine türünü vererek, [RFX'in](../../data/odbc/record-field-exchange-rfx.md) bu tür bir nesnenin kayıt setinizle veri kaynağı arasında aktarılmasını yönetebileceği ve nesneiçindeki verileri manipüle edebileceğiniz sabit bir taban sağlarsınız. RFX'in alınan veriler için belirli bir siteye ihtiyacı vardır ve temel verilere erişmek için bir yol gerekir.

Büyük veri öğeleriyle çalışmak için kullanma `CByteArray` hakkında ayrıntılı bilgi için Teknik Not [45'e](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)bakın.

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>CLongBinary Sınıfı

[CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi, yığında `HGLOBAL` ayrılan depolama bloğuna bir tutamacın etrafındaki basit bir kabuktür. İkili büyük bir nesne içeren bir tablo sütunu bağladığında, RFX verileri kaydedici sete aktarması gerektiğinde `HGLOBAL` tutamacı ayırır ve tutamacı kayıt kümesi `CLongBinary` alanında depolar.

Buna karşılık, `HGLOBAL` `m_hData`işlemi, veri kendisi ile çalışmak için, herhangi bir işleme verileri üzerinde olduğu gibi üzerinde çalışan kullanın. Burası [CByteArray'in](../../mfc/reference/cbytearray-class.md) yetenekleri eklediği yerdir.

> [!CAUTION]
> CLongBinary nesneleri işlev çağrılarında parametre olarak kullanılamaz. Buna ek olarak, kaydırma `::SQLGetData`özelliği için kaydırma performansını mutlaka yavaşlatan uygulama da vardır. Dinamik şema sütunlarını almak `::SQLGetData` için bir çağrıyı kendiniz kullandığınızda da bu doğru olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
