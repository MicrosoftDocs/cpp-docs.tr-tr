---
title: "Formdaki verileri görüntüleme ve düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a7960780f1f83833e25c9a094a36314a299a042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Formdaki Verileri Görüntüleme ve Düzenleme
Birçok veri erişimi uygulamaları verileri seçin ve bir form alanlarında görüntüleyin. Veritabanı sınıfı [CRecordView](../../mfc/reference/crecordview-class.md) size verir bir [Cformview'yu](../../mfc/reference/cformview-class.md) doğrudan bağlı bir kayıt kümesi nesnesi nesne. Kayıt görünümü kullanır [iletişim kutusu veri değişimi (DDX)](../../mfc/dialog-data-exchange-and-validation.md) geçerli kayıt alanların değerlerini form üzerinde denetimleri kayıt kümesinden taşımayı ve güncelleştirilmiş bilgileri kayıt kümesine geri taşımak için. Kayıt kümesi kayıt alanı değişimi (RFX) veri kaynağı üzerinde alan veri üyeleri ve karşılık gelen bir tablo sütunları arasında verileri taşımak için de kullanır.  
  
 MFC Uygulama Sihirbazı'nı kullanabilirsiniz veya **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) görünüm ve onun ilişkili kayıt kümesi sınıf oluşturmak için.  
  
 Kayıt görünümü ve onun kayıt kümeleri belgeyi kapattığınızda yok olur. Kayıt görünümleri hakkında daha fazla bilgi için bkz: [kayıt görünümleri](../../data/record-views-mfc-data-access.md). RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)