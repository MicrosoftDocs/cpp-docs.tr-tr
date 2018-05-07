---
title: Sağlayıcınızdaki Özellikleri ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5d43e452d0fffcb4dc6eddcae722f8056dbd39dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="setting-properties-in-your-provider"></a>Sağlayıcınızdaki Özellikleri Ayarlama
Özellik grubu ve özellik kimliği özelliği için bulun. Daha fazla bilgi için bkz: [OLE DB özellikleri](https://msdn.microsoft.com/en-us/library/ms722734.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Sihirbaz tarafından oluşturulan sağlayıcı kodunda özellik grubuna karşılık gelen özellik eşlemesi bulunamadı. Özellik grubunun adı, genellikle nesne adına karşılık gelir. Komut ve satır kümesi özellikleri komut veya satır kümesi bulunabilir; veri kaynağı ve başlatma özellikleri veri kaynağı nesnesi içinde bulunabilir.  
  
 Özellik Eşlemesi Ekle bir [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) makrosu. PROPERTY_INFO_ENTRY_EX dört parametreleri alır:  
  
-   Özelliğine karşılık gelen özellik kimliği. Özellik ad Önden ilk yedi karakterler ("DBPROP_") kaldırmanız gerekir. Örneğin, eklemek istediğiniz **DBPROP_MAXROWS**, geçirmek `MAXROWS` ilk öğe olarak. Özel bir özellik varsa GUID tam adını geçirin (örneğin, `DBMYPROP_MYPROPERTY`).  
  
-   Özelliğin değişken türü (içinde [OLE DB özellikleri](https://msdn.microsoft.com/en-us/library/ms722734.aspx) içinde *OLE DB Programcının Başvurusu*). Girin **VT_** türü (gibi `VT_BOOL` veya `VT_I2`) veri türüne karşılık gelen.  
  
-   Özellik okunabilir ve yazılabilir olup olmadığını ve ait olduğu grubu göstermek için işaretler. Örneğin, aşağıdaki kod satır kümesi grubuna ait bir okuma/yazma özelliği gösterir:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Özelliğin taban değeri. Bu olabilir **VARIANT_FALSE** için bir Boole değeri yazın veya bir tamsayı türü için örneğin sıfır. Değişmediği sürece özelliği bu değere sahip.  
  
    > [!NOTE]
    >  Bazı özellikler bağlı veya yer işaretleri veya güncelleştirme gibi diğer özelliklere zincirleme. Bir tüketici bir özelliği true olarak ayarlanır, başka bir özellik de ayarlanması gerekir. OLE DB sağlayıcı şablonları bu yöntemle destekleyen [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB sağlayıcıları tarafından göz ardı özellikleri  
 Microsoft OLE DB sağlayıcıları aşağıdaki OLE DB özelliklerini yoksayar:  
  
-   **DBPROP_MAXROWS** yalnızca salt okunur sağlayıcılar için çalışır (diğer bir deyişle, burada DBPROP_IRowsetChange ve DBPROP_IRowsetUpdate hatalı false); Aksi takdirde bu özelliği desteklenmiyor.  
  
-   **DBPROP_MAXPENDINGROWS** göz ardı edilir; sağlayıcı kendi üst sınırını belirtir.  
  
-   **DBPROP_MAXOPENROWS** göz ardı edilir; sağlayıcı kendi üst sınırını belirtir.  
  
-   **DBPROP_CANHOLDROWS** göz ardı edilir; sağlayıcı kendi üst sınırını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)