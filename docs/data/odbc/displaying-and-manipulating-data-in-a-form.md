---
title: Formdaki verileri görüntüleme ve düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b86c58c8e5afb53cb02174beb3553378dd0efc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Formdaki Verileri Görüntüleme ve Düzenleme
Birçok veri erişimi uygulamaları verileri seçin ve bir form alanlarında görüntüleyin. Veritabanı sınıfı [CRecordView](../../mfc/reference/crecordview-class.md) size verir bir [Cformview'yu](../../mfc/reference/cformview-class.md) doğrudan bağlı bir kayıt kümesi nesnesi nesne. Kayıt görünümü kullanır [iletişim kutusu veri değişimi (DDX)](../../mfc/dialog-data-exchange-and-validation.md) geçerli kayıt alanların değerlerini form üzerinde denetimleri kayıt kümesinden taşımayı ve güncelleştirilmiş bilgileri kayıt kümesine geri taşımak için. Kayıt kümesi kayıt alanı değişimi (RFX) veri kaynağı üzerinde alan veri üyeleri ve karşılık gelen bir tablo sütunları arasında verileri taşımak için de kullanır.  
  
 MFC Uygulama Sihirbazı'nı kullanabilirsiniz veya **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) görünüm ve onun ilişkili kayıt kümesi sınıf oluşturmak için.  
  
 Kayıt görünümü ve onun kayıt kümeleri belgeyi kapattığınızda yok olur. Kayıt görünümleri hakkında daha fazla bilgi için bkz: [kayıt görünümleri](../../data/record-views-mfc-data-access.md). RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)