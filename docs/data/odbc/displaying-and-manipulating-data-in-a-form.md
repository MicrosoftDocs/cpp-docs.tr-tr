---
title: Formdaki Verileri Görüntüleme ve Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
ms.openlocfilehash: 1694d9cbc770e02c550891fc83c1cc0a9f64824a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517799"
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Formdaki Verileri Görüntüleme ve Düzenleme

Birçok veri erişimi uygulamaları verileri seçin ve form alanlarını görüntüler. Veritabanı sınıfı [CRecordView](../../mfc/reference/crecordview-class.md) size bir [Cformview'yu](../../mfc/reference/cformview-class.md) doğrudan bağlı bir kayıt kümesi nesnesi için nesne. Kayıt görünümü kullanır [iletişim kutusu veri değişimi (DDX)](../../mfc/dialog-data-exchange-and-validation.md) kayıt kümesinden geçerli kaydın alanlarının değerlerini form üzerinde denetimleri taşımak için ve güncelleştirilmiş bilgileri kayıt kümesine geri taşımak için. Kayıt kümesi kayıt alanı değişimi (RFX) veri kaynağını temel alan veri üyeleri ve karşılık gelen bir tabloda sütun arasında veri taşıma için sırasıyla kullanır.

MFC Uygulama Sihirbazı'nı kullanabilirsiniz veya **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) görünüm sınıfı ve onun ilişkili kayıt kümesi sınıfını oluşturmak için.

Kayıt görünümü ve onun kayıt kümesi belge kapattıktan sonra yok edilir. Kayıt görünümleri hakkında daha fazla bilgi için bkz: [kayıt görünümleri](../../data/record-views-mfc-data-access.md). RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)