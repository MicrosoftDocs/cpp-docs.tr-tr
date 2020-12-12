---
description: 'Daha fazla bilgi: kayıt kümesi: büyük veri öğeleri ile çalışma (ODBC)'
title: 'Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 7a4ca6de9c0b5be32626c8ca3c7c66cc516057e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204374"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)

Bu konu, hem MFC ODBC sınıfları hem de MFC DAO sınıfları için geçerlidir.

> [!NOTE]
> MFC DAO sınıflarını kullanıyorsanız, büyük veri öğelerinizi, [CLongBinary](../../mfc/reference/clongbinary-class.md)sınıfı yerine [CByteArray](../../mfc/reference/cbytearray-class.md) sınıfı ile yönetin. MFC ODBC sınıflarını toplu satır getirme ile kullanıyorsanız `CLongBinary` yerine kullanın `CByteArray` . Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Veritabanınızın bit eşlemler (çalışan fotoğrafları, Haritalar, ürünlerin resimleri, OLE nesneleri vb.) gibi büyük miktarda veriyi depolayabildiğini varsayalım. Bu tür veriler genellikle Ikili büyük nesne (veya BLOB) olarak adlandırılır, çünkü:

- Her alan değeri büyük.

- Sayıların ve diğer basit veri türlerinin aksine, tahmin edilebilir bir boyuta sahip değildir.

- Veri, programınızın perspektifinden formsuz.

Bu konu, veritabanı sınıflarının bu tür nesnelerle çalışma sağladığı desteği açıklar.

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a> Büyük nesneleri yönetme

Kayıt kümelerinin, ikili büyük nesneleri yönetmenin özel zorluğunu çözmenin iki yolu vardır. Sınıf [CByteArray](../../mfc/reference/cbytearray-class.md) ' i kullanabilir veya bir [CLongBinary](../../mfc/reference/clongbinary-class.md)sınıfı kullanabilirsiniz. Genel olarak, `CByteArray` büyük ikili verileri yönetmenin tercih edilen yoludur.

`CByteArray` , `CLongBinary` [CByteArray sınıfında](#_core_the_cbytearray_class)açıklandığı gibi daha fazla ek yük gerektirir, ancak daha yetenekli olur. `CLongBinary` , [CLongBinary sınıfında](#_core_the_clongbinary_class)kısaca açıklanmıştır.

`CByteArray`Büyük veri öğeleriyle çalışmak üzere kullanma hakkında ayrıntılı bilgi için bkz. [teknik notta 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a> CByteArray sınıfı

`CByteArray` MFC koleksiyon sınıflarından biridir. Bir `CByteArray` nesne, dinamik bir bayt dizisini depolar — dizi gerektiğinde büyüyebilir. Sınıfı, yerleşik C++ dizileri ile olduğu gibi, dizin tarafından hızlı erişim sağlar. `CByteArray` nesneler, tanılama amacıyla sıralanabilir ve dökülebilir. Sınıfı, belirtilen baytları alma ve ayarlama, bayt ekleme ve ekleme ve bir bayt ya da tüm baytları kaldırma için üye işlevleri sağlar. Bu tesisler, ikili verileri ayrıştırmayı daha kolay hale getirir. Örneğin, ikili nesne bir OLE nesneseniz, gerçek nesneye ulaşmak için bazı üst bilgi baytlarıyla çalışmanız gerekebilir.

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a> Kayıt kümelerinde CByteArray Kullanma

Kayıt kümenizin bir alan veri üyesini, `CByteArray` kayıt kümeniz ve veri kaynağı arasında bu nesnenin aktarımını yönetebileceği ve nesne [](../../data/odbc/record-field-exchange-rfx.md) içindeki verileri işleyebileceğiniz bir sabit taban sağlarsınız. RFX alınan veriler için belirli bir siteye ihtiyaç duyar ve temel alınan verilere erişmeniz için bir yol gerekir.

`CByteArray`Büyük veri öğeleriyle çalışmak üzere kullanma hakkında ayrıntılı bilgi için bkz. [teknik notta 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a> CLongBinary sınıfı

Bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi, `HGLOBAL` yığın üzerinde ayrılmış bir depolama bloğuna yönelik tanıtıcının etrafında basit bir kabuktur. İkili büyük nesne içeren bir tablo sütununu bağladığında, RFX, `HGLOBAL` verileri kayıt kümesine aktarması gerektiğinde tanıtıcıyı ayırır ve tanıtıcıyı `CLongBinary` kayıt kümesinin alanında depolar.

Sırasıyla, `HGLOBAL` Bu tanıtıcıyı, `m_hData` her türlü tanıtıcı veri üzerinde olduğu gibi üzerinde çalışan, verilerin kendisiyle çalışmak için kullanırsınız. Bu, [CByteArray](../../mfc/reference/cbytearray-class.md) 'nin Özellik eklediği yerdir.

> [!CAUTION]
> CLongBinary nesneleri işlev çağrılarında parametre olarak kullanılamaz. Bunlara ek olarak, çağrısı yapılan, `::SQLGetData` kaydırılabilir bir anlık görüntü için kaydırma performansını yavaşlatmış olması gerekir. Bu, `::SQLGetData` dinamik şema sütunlarını almak için bir çağrı kullandığınızda da doğru olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: toplamları ve diğer toplama sonuçlarını alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
