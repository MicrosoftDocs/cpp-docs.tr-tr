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
ms.openlocfilehash: b84365461ce6d45fccdf1922974feff5af93f99f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212764"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)

Bu konu, hem MFC ODBC sınıfları hem de MFC DAO sınıfları için geçerlidir.

> [!NOTE]
>  MFC DAO sınıflarını kullanıyorsanız, büyük veri öğelerinizi, [CLongBinary](../../mfc/reference/clongbinary-class.md)sınıfı yerine [CByteArray](../../mfc/reference/cbytearray-class.md) sınıfı ile yönetin. Toplu satır getirme ile MFC ODBC sınıfları kullanıyorsanız, `CByteArray`yerine `CLongBinary` kullanın. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Veritabanınızın bit eşlemler (çalışan fotoğrafları, Haritalar, ürünlerin resimleri, OLE nesneleri vb.) gibi büyük miktarda veriyi depolayabildiğini varsayalım. Bu tür veriler genellikle Ikili büyük nesne (veya BLOB) olarak adlandırılır, çünkü:

- Her alan değeri büyük.

- Sayıların ve diğer basit veri türlerinin aksine, tahmin edilebilir bir boyuta sahip değildir.

- Veri, programınızın perspektifinden formsuz.

Bu konu, veritabanı sınıflarının bu tür nesnelerle çalışma sağladığı desteği açıklar.

##  <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>Büyük nesneleri yönetme

Kayıt kümelerinin, ikili büyük nesneleri yönetmenin özel zorluğunu çözmenin iki yolu vardır. Sınıf [CByteArray](../../mfc/reference/cbytearray-class.md) ' i kullanabilir veya bir [CLongBinary](../../mfc/reference/clongbinary-class.md)sınıfı kullanabilirsiniz. Genel olarak, büyük ikili verileri yönetmek için tercih edilen yol `CByteArray`.

`CByteArray`, `CLongBinary` daha fazla yük gerektirir ancak [CByteArray sınıfında](#_core_the_cbytearray_class)açıklandığı gibi daha yetenekli olur. `CLongBinary`, [CLongBinary sınıfında](#_core_the_clongbinary_class)kısaca açıklanmıştır.

Büyük veri öğeleriyle çalışmak üzere `CByteArray` kullanma hakkında ayrıntılı bilgi için bkz. [teknik notta 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

##  <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>CByteArray sınıfı

`CByteArray` MFC koleksiyon sınıflarından biridir. Bir `CByteArray` nesnesi dinamik bir bayt dizisini depolar — dizi gerektiğinde büyüyebilir. Sınıfı, yerleşik C++ diziler ile olduğu gibi, dizin tarafından hızlı erişim sağlar. `CByteArray` nesneler, tanılama amacıyla sıralanabilir ve dökülebilir. Sınıfı, belirtilen baytları alma ve ayarlama, bayt ekleme ve ekleme ve bir bayt ya da tüm baytları kaldırma için üye işlevleri sağlar. Bu tesisler, ikili verileri ayrıştırmayı daha kolay hale getirir. Örneğin, ikili nesne bir OLE nesneseniz, gerçek nesneye ulaşmak için bazı üst bilgi baytlarıyla çalışmanız gerekebilir.

##  <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>Kayıt kümelerinde CByteArray Kullanma

Kayıt kümenizin bir alan veri üyesini `CByteArray`türüne vererek, bu nesnenin kayıt kümeniz ile veri kaynağı arasında veya nesne içindeki verileri işleyebileceğiniz bir nesne aktarımını [yönetebileceği bir](../../data/odbc/record-field-exchange-rfx.md) sabit taban sağlarsınız. RFX alınan veriler için belirli bir siteye ihtiyaç duyar ve temel alınan verilere erişmeniz için bir yol gerekir.

Büyük veri öğeleriyle çalışmak üzere `CByteArray` kullanma hakkında ayrıntılı bilgi için bkz. [teknik notta 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

##  <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>CLongBinary sınıfı

Bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi, yığın üzerinde ayrılmış bir depolama bloğuna `HGLOBAL` tanıtıcısı etrafında basit bir kabuktur. İkili büyük nesne içeren bir tablo sütununu bağladığında, RFX, verileri kayıt kümesine aktarması gerektiğinde `HGLOBAL` tanıtıcıyı ayırır ve tanıtıcıyı kayıt kümesinin `CLongBinary` alanında depolar.

Sırasıyla, `m_hData`, verileri herhangi bir tanıtıcı veri üzerinde olduğu gibi çalıştırmak için `HGLOBAL` tanıtıcısını kullanırsınız. Bu, [CByteArray](../../mfc/reference/cbytearray-class.md) 'nin Özellik eklediği yerdir.

> [!CAUTION]
>  CLongBinary nesneleri işlev çağrılarında parametre olarak kullanılamaz. Ayrıca, `::SQLGetData`çağıran uygulama, kaydırılabilir bir anlık görüntü için kaydırma performansını yavaşlatır. Bu, dinamik şema sütunlarını almak için bir `::SQLGetData` çağrısı kullandığınızda da doğru olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
